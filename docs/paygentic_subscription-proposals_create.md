## paygentic subscription-proposals create

Create

### Synopsis

Creates a pending subscription proposal from the values of a subscription create. The customer must already exist. A plan or customer of another merchant answers 404, as an unknown one does. The values are checked as subscription create checks them, at the moment of the request, but no subscription, invoice or entitlement exists until a person approves the proposal.

With an `externalReference`, the create first finds the proposal that record already has: its pending or approved proposal, else its most recent rejected one. Sends of one record are handled one at a time. Values are compared after normalization: key order does not count, a field sent with its default equals the field left out, and two forms of one instant, such as `Z` and `+00:00`, are equal.

- None found: a new proposal, 201.
- Values equal to that proposal's `requested`: the proposal, 200. Nothing is checked. A stored `refusedResync` is cleared, which raises `lockVersion` and changes `hash`; without one, nothing is written.
- A pending proposal, values changed: the values become the next revision and `requested`. `current` takes each changed field except a field in `amendedFields`, which keeps the person's value, and a field left out returns to its default. The result is checked as an amend is, and answered 200.
- A pending proposal whose change conflicts with an amendment: 409 `SUBSCRIPTION_PROPOSAL_RESYNC_CONFLICT`, and `current` and `requested` do not change. `details.fields` names each conflicting field. A field conflicts when the client changed it, a person amended it, and the new value differs from `current`. Leaving out a field the previous send set changes it to its default, so leaving out an amended field conflicts too. A change also conflicts when it would leave price fields (`planVersionId`, `overridePrices`, `addPrices`, `removePrices`, `adjustments`) naming another plan's prices, and when it would change `versionPolicy` while `planVersionId` is amended.
- An approved proposal, values changed: 409 `SUBSCRIPTION_PROPOSAL_ALREADY_APPROVED`, with the subscription's id in `details.subscriptionId`. Changes to an active subscription are not supported yet.
- A rejected proposal, values changed: a new proposal, 201. The rejected one is unchanged.

A refused send is kept on the proposal as `refusedResync`, so a reviewer sees it. A send that repeats the stored refusal changes nothing.

```
paygentic subscription-proposals create [flags]
```

### Examples

```
  paygentic subscription-proposals create --customer-id <id> --name <value> --plan-id <id> --started-at 2024-06-17T10:38:54.507Z
```

### Options

```
      --add-prices string                        Catalog prices to bill on this subscription that its plan version does not carry. Each must be owned by the same merchant and use the standard price model.
      --adjustments string                       Adjustments the subscription gets when the proposal is approved. Each is checked as subscription adjustment create checks it, against the prices the proposal bills and the other adjustments in this list.
      --auto-charge                              Enable automatic charging of invoices using stored payment methods. When true, invoices will be automatically paid using off-session payment. Defaults to false.
  -b, --billing-anchor startedAt                 A billing anchor for this subscription, in place of the plan's. Any instant, past or future. The subscription's billing anchor is its first recurrence on or after startedAt, stepping back or forward by whole billing cadences. Example: on a monthly plan, an anchor of '2027-01-31T00:00:00Z' with a start of '2026-10-10T00:00:00Z' gives '2026-10-31T00:00:00Z'. A create is refused with 400 when the resolved anchor does not line up with the usage period anchor of a feature that credits unused balance. Omit it to use the plan's billing anchor. A repeated create that names an anchor resolving to a different instant than the existing subscription's gets 409.
      --body string                              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --change-description string                A free-text note on why these intervals are changing.
      --change-metadata string                   Your own key-value data about the change, such as a CRM deal ID.
      --change-reason correction                 Why a change was made. correction repairs data that was entered wrong; `migration` moves a contract from another system; `commercial` is a real change to the deal; `contractual` applies a step the original contract scheduled, such as an annual uplift. Defaults to `unspecified`. (options: commercial, correction, migration, unspecified, contractual)
      --customer-id string                       Unique identifier for a customer [required]
      --elapsed-period-billing startedAt         Whether a backdated start bills its elapsed periods. A start is backdated when startedAt is more than 24 hours before the subscription is created. `none` bills only charges that fall due from the moment of creation, for a customer whose earlier periods another system already billed. `per_period` bills every charge that fell due from `startedAt`, on one first invoice; it refuses a `startedAt` more than 12 months back, with the code `PER_PERIOD_LOOKBACK_EXCEEDED`. Has no effect on a start that is not backdated. Defaults to `none`. (options: none, per_period) (default "none")
      --ending-at string                         Subscription expiration timestamp in ISO 8601 format. Sample values: '2024-12-31T23:59:59Z', '2025-01-15T10:30:00Z'. Omit for indefinite subscriptions. Must be after startedAt: a value at or before it is rejected with 400.
      --external-reference string                The record in another system, such as a CRM deal, that the proposal comes from. A create naming a record that already has a proposal acts on that proposal, as the create operation describes.
  -h, --help                                     help for create
      --metadata string                          Free-form merchant metadata to attach to the subscription. Values must be strings, numbers, or booleans.
      --minimum-account-balance string           Deprecated. This field is ignored and has no effect.
  -n, --name string                              Subscription identifier combining customer and service details. Sample values: 'TechCorp - LLM API Access', 'Analytics Co - Data Platform Enterprise', 'StartupXYZ - Image Generation Service', 'Enterprise Inc - ML Training Platform' [required]
      --override-prices string                   Rate or quantity overrides for prices the plan version does carry.
      --payment-term-days sessionExpiryMinutes   Payment term in days ("Net X") applied to every invoice the subscription generates: invoice dueAt = invoice issue date + paymentTermDays. Defaults to 0 ("due on issue"). Valid on any subscription, whatever its payment method. With a non-zero value Invoice 0's payment session expires at its due date, and sending sessionExpiryMinutes with it answers 400 `SESSION_EXPIRY_NOT_ALLOWED_WITH_PAYMENT_TERM`.
      --plan-id string                           Unique identifier for a plan [required]
      --plan-version-id planId                   A published version of planId to pin the proposal to. Only a pinned proposal (`versionPolicy: "pinned"`) names a version. One that names none, or `null`, pins the plan's default version, as a change of `planId` without a version does. A floating proposal follows the plan's default version, and one that names a version is refused with 400.
      --prefund-amount string                    Deprecated. This field is ignored and has no effect.
      --redirect-urls string                     Optional redirect URLs after payment completion or failure. If not provided, uses default platform behavior.
      --remove-prices string                     Plan prices this subscription does not bill.
      --renewal-reminder-days string             Override plan setting for number of days before renewal to send the reminder. Only used if renewalReminderEnabled is true (or inherited from plan). Set to null to use plan default.
      --renewal-reminder-enabled string          Override plan setting for renewal reminder emails. When set, this subscription's setting takes precedence over the plan default. Set to true to enable reminders, false to disable, or null/omit to use plan default.
      --session-expiry-minutes paymentTermDays   Number of minutes until the payment session expires. Defaults to 240 minutes (4 hours) if not provided. Not accepted with a non-zero paymentTermDays: the session then expires at the invoice due date.
      --started-at string                        Subscription activation timestamp in ISO 8601 format. Sample values: '2024-01-15T10:30:00Z', '2024-02-01T00:00:00Z' [required]
      --tax-exempt                               When true, forces tax rate to 0%. Use for customers with verified tax-exempt status.
      --test-clock-id string                     Test clock identifier for simulating time-based billing scenarios. Sample values: 'tc_abc123xyz', 'tc_789def456'. Restricted to non-production environments (local, dev, sandbox). Must belong to the same merchant organization.
  -v, --version-policy floating                  How the subscription follows new versions of its plan. floating follows the plan's default version: when the default changes, the subscription bills from the new default from its next billing period. `pinned` keeps the plan version that the subscription holds. A subscription created without a value is `floating`. A change to this value does not change a billing period that has already started. (options: floating, pinned)
```

### Options inherited from parent commands

```
      --agent-mode             Enable structured errors and default TOON output for AI coding agents. Automatically enabled when a known agent environment is detected (CLAUDE_CODE, CURSOR_AGENT, etc.). Use --agent-mode=false to disable.
      --bearer-auth string     API key authentication
      --color string           Control colored output: auto (color when output is a TTY), always, or never. Respects NO_COLOR and FORCE_COLOR env vars. (default "auto")
  -d, --debug                  Log request and response diagnostics to stderr
      --dry-run                Preview the request that would be sent without executing it (output to stderr)
  -H, --header stringArray     Set a custom HTTP request header (format: "Key: Value"). Can be specified multiple times.
      --include-headers        Include HTTP response headers in the output
  -q, --jq string              Filter and transform output using a jq expression (e.g., '.name', '.items[] | .id')
      --no-interactive         Disable all interactive features (auto-prompting, explorer auto-launch, TUI forms)
  -o, --output-format string   Specify the output format. Options: pretty, json, yaml, table, toon. (default "pretty")
      --server string          Select a server by index (for indexed servers) or name (for named servers)
      --server-url string      Override the default server URL
      --timeout string         HTTP request timeout (e.g., 30s, 5m, 100ms)
      --usage                  Print the CLI Usage schema in KDL format
```

### SEE ALSO

* [paygentic subscription-proposals](paygentic_subscription-proposals.md)	 - A `SubscriptionProposal` holds the values of a subscription until a person on your team approves or rejects it
