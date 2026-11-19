## paygentic subscription-proposals decide

Approve or reject

### Synopsis

Approves or rejects a pending subscription proposal. The body is flat like `PATCH /v0/approvals/{id}`'s, but takes the verbs `approve` and `reject`, a `reason` from a fixed list with optional `text`, and no `cancelled`. Needs the `subscriptionProposals:approve` permission, whoever created the proposal. Send the proposal's `hash` as `basedOnHash`. `approve` creates the subscription that `POST /v0/subscriptions` would create from the proposal's values at the moment of approval, read from the proposal's test clock when it has one, on its pinned version or, for a floating proposal, on the plan's default at that moment. The proposal becomes `approved` with the new `subscriptionId` in the same transaction. The answer comes once the first invoice is raised, as subscription create's does; read the subscription, with its payment state, from `GET /v0/subscriptions/{id}`. An approval takes no `reason` or `text`. An `approve` of an `approved` proposal whose `strandedAt` is set resumes the subscription its approval left waiting for its first invoice, and answers `SUBSCRIPTION_PROPOSAL_CHANGED` when another approve claimed it after this one read it. `reject` records the reason, the text, who decided and when. The proposal becomes `rejected`, which is final. No subscription is created, and nothing is sent to the system the proposal came from. 409 carries a `code`: `SUBSCRIPTION_PROPOSAL_NOT_PENDING` for a proposal that is not `pending`; `SUBSCRIPTION_PROPOSAL_CHANGED` when its `hash` changed since it was read, by an amend or a new default of a floating proposal's plan, or when it changed while the approval ran, with `details` `{ field: 'lockVersion', expected, actual }`; `SUBSCRIPTION_PROPOSAL_INVALID` when approving finds the proposal fails a check subscription create makes, with `details.code` the failed check's own code and `details.details` its details, each only when the check has one; `SUBSCRIPTION_PROPOSAL_DUPLICATE` when the customer already has a live subscription for the plan's product; `SUBSCRIPTION_PROPOSAL_ALREADY_APPROVED` when that subscription is the one a concurrent approval of this proposal created. Both put the subscription's id in `details.subscriptionId`. On any 409 the proposal is left as it is, except that an `approve` of a proposal whose `strandedAt` is set, when its subscription is no longer waiting for its first invoice, clears `strandedAt` and answers `SUBSCRIPTION_PROPOSAL_NOT_PENDING`. A plan, plan version or customer that no longer exists answers 404. A pending proposal blocks deleting its plan and its customer, so this happens only when a delete runs at the same time. A proposal of another merchant answers 404, as an unknown one does.

```
paygentic subscription-proposals decide [flags]
```

### Examples

```
  paygentic subscription-proposals decide --id <id> --decision approve --based-on-hash <value>
```

### Options

```
  -b, --based-on-hash hash      The proposal's hash as the person read it. When the proposal has changed since, the decision is refused with 409 `SUBSCRIPTION_PROPOSAL_CHANGED`: read the proposal again and decide on what it holds now. [required]
      --body string             Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --decision approve        approve creates the subscription and makes the proposal `approved`. `reject` rejects the proposal. Either is final: the proposal never becomes `pending` again. (options: approve, reject) [required]
  -h, --help                    help for decide
  -i, --id string               The subscription proposal ID [required]
  -r, --reason price_mismatch   Why a person rejected the proposal. price_mismatch: a price or discount is not the one agreed. `wrong_plan`: the proposal names the wrong plan. `wrong_start_date`: the start date is wrong. `wrong_customer`: the proposal names the wrong customer. `duplicate`: the customer already has this subscription, or another proposal holds it. `other`: another reason, explained in `text`. (options: price_mismatch, wrong_plan, wrong_start_date, wrong_customer, duplicate, other)
  -t, --text reason             Notes on the rejection, at most 2000 characters. Required when reason is `other`. Whitespace around it is trimmed, and a blank value is stored as null. An approval refuses it.
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
