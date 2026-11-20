## paygentic subscription-proposals update

Amend

### Synopsis

Changes the values of a pending subscription proposal before it is decided. Send only the fields to change. `requested`, the values the source sent, stays as it is, and `current` takes the changes. A field sent with a value other than its `requested` value joins `amendedFields`, a field sent with its `requested` value leaves it, and a field not sent keeps its state. Only a pinned proposal names a version. Its `planVersionId` compares with the version a `pinned` `requested` names, else with the plan's default version; on a proposal the source sent floating, a pinned version is amended.

Set a nullable field to null to clear it: the field leaves `current`, and the default a create applies takes its place. On a pinned proposal, `planVersionId: null`, or a new `planId` without a `planVersionId`, pins the plan's default version. Setting `versionPolicy` to `floating` drops the version: the proposal then follows the plan's default. `elapsedPeriodBilling`, `versionPolicy`, `metadata`, `changeReason` and `changeMetadata` take no null: to reset one, send its default value (`none`, `floating`, `{}`, `unspecified` and `{}`).

The result is checked as a subscription create checks its values, at the moment of the request, and a request that fails a check changes nothing. A request that changes neither `current` nor `amendedFields` is not checked: it writes nothing and answers the proposal as it is, even when the proposal has become invalid since its last change, for example past the twelve-month limit of `per_period`. A plan or plan version that no longer exists still answers 404. A proposal that is no longer pending answers 409 with the code `SUBSCRIPTION_PROPOSAL_NOT_PENDING`. With `basedOnHash`, a proposal whose `hash` changed since it was read answers 409 `SUBSCRIPTION_PROPOSAL_CHANGED`, after the pending check, so two reviewers cannot overwrite each other's amends. A proposal of another merchant answers 404, as an unknown one does.

```
paygentic subscription-proposals update [flags]
```

### Examples

```
  paygentic subscription-proposals update --id <id>
```

### Options

```
      --add-prices string                        Catalog prices to bill on this subscription that its plan version does not carry. Each must be owned by the same merchant and use the standard price model.
      --adjustments string                       Adjustments the subscription gets when the proposal is approved. Each is checked as subscription adjustment create checks it, against the prices the proposal bills and the other adjustments in this list.
      --auto-charge string                       Enable automatic charging of invoices using stored payment methods. When true, invoices will be automatically paid using off-session payment. Defaults to false.
      --based-on-hash hash                       The proposal's hash as the person read it. When sent and the proposal has changed since, the amend is refused with 409 `SUBSCRIPTION_PROPOSAL_CHANGED` and nothing is written: read the proposal again and amend what it holds now. Leave it out to amend whatever the proposal holds.
      --billing-anchor startedAt                 A billing anchor for this subscription, in place of the plan's. Any instant, past or future. The subscription's billing anchor is its first recurrence on or after startedAt, stepping back or forward by whole billing cadences. Example: on a monthly plan, an anchor of '2027-01-31T00:00:00Z' with a start of '2026-10-10T00:00:00Z' gives '2026-10-31T00:00:00Z'. A create is refused with 400 when the resolved anchor does not line up with the usage period anchor of a feature that credits unused balance. Omit it to use the plan's billing anchor. A repeated create that names an anchor resolving to a different instant than the existing subscription's gets 409.
      --body string                              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --change-description string                A free-text note on why these intervals are changing.
      --change-metadata string                   Your own key-value data about the change, such as a CRM deal ID.
      --change-reason correction                 Why a change was made. correction repairs data that was entered wrong; `migration` moves a contract from another system; `commercial` is a real change to the deal; `contractual` applies a step the original contract scheduled, such as an annual uplift. Defaults to `unspecified`. (options: commercial, correction, migration, unspecified, contractual)
      --customer-id string                       Unique identifier for a customer
      --elapsed-period-billing startedAt         Whether a backdated start bills its elapsed periods. A start is backdated when startedAt is more than 24 hours before the subscription is created. `none` bills only charges that fall due from the moment of creation, for a customer whose earlier periods another system already billed. `per_period` bills every charge that fell due from `startedAt`, on one first invoice; it refuses a `startedAt` more than 12 months back, with the code `PER_PERIOD_LOOKBACK_EXCEEDED`. Has no effect on a start that is not backdated. Defaults to `none`. (options: none, per_period)
      --ending-at string                         Subscription expiration timestamp in ISO 8601 format. Sample values: '2024-12-31T23:59:59Z', '2025-01-15T10:30:00Z'. Omit for indefinite subscriptions. Must be after startedAt: a value at or before it is rejected with 400.
  -h, --help                                     help for update
  -i, --id string                                [required]
      --metadata string                          Free-form merchant metadata to attach to the subscription. Values must be strings, numbers, or booleans.
      --minimum-account-balance string           Deprecated. This field is ignored and has no effect.
  -n, --name string                              Subscription identifier combining customer and service details. Sample values: 'TechCorp - LLM API Access', 'Analytics Co - Data Platform Enterprise', 'StartupXYZ - Image Generation Service', 'Enterprise Inc - ML Training Platform'
      --override-prices string                   Rate or quantity overrides for prices the plan version does carry.
      --payment-term-days sessionExpiryMinutes   Payment term in days ("Net X") applied to every invoice the subscription generates: invoice dueAt = invoice issue date + paymentTermDays. Defaults to 0 ("due on issue"). Valid on any subscription, whatever its payment method. With a non-zero value Invoice 0's payment session expires at its due date, and sending sessionExpiryMinutes with it answers 400 `SESSION_EXPIRY_NOT_ALLOWED_WITH_PAYMENT_TERM`.
      --plan-id string                           Unique identifier for a plan
      --plan-version-id planId                   A published version of planId to pin the proposal to. Only a pinned proposal (`versionPolicy: "pinned"`) names a version. One that names none, or `null`, pins the plan's default version, as a change of `planId` without a version does. A floating proposal follows the plan's default version, and one that names a version is refused with 400.
      --prefund-amount string                    Deprecated. This field is ignored and has no effect.
      --redirect-urls string                     Optional redirect URLs after payment completion or failure. If not provided, uses default platform behavior.
      --remove-prices string                     Plan prices this subscription does not bill.
      --renewal-reminder-days string             Override plan setting for number of days before renewal to send the reminder. Only used if renewalReminderEnabled is true (or inherited from plan). Set to null to use plan default.
      --renewal-reminder-enabled string          Override plan setting for renewal reminder emails. When set, this subscription's setting takes precedence over the plan default. Set to true to enable reminders, false to disable, or null/omit to use plan default.
      --session-expiry-minutes paymentTermDays   Number of minutes until the payment session expires. Defaults to 240 minutes (4 hours) if not provided. Not accepted with a non-zero paymentTermDays: the session then expires at the invoice due date.
      --started-at string                        Subscription activation timestamp in ISO 8601 format. Sample values: '2024-01-15T10:30:00Z', '2024-02-01T00:00:00Z'
      --tax-exempt string                        When true, forces tax rate to 0%. Use for customers with verified tax-exempt status.
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
