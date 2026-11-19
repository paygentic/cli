## paygentic subscription-proposals list-subscription-proposal-projected-invoices

List projected

### Synopsis

Returns the invoices that approving this pending subscription proposal now would raise, as a list of `Invoice` in the envelope `GET /v2/invoices/projected` answers. It is not that endpoint: it takes no `from` or `to`, and it prices an elapsed metered period as described below. Today `data` holds the first invoice only, with the lines and amounts approve would bill at the moment of this read, and it is empty when approving now would raise no invoice. `pagination.total` says whether anything is owed: 1 when it is and 0 when it is not, whatever the offset. Nothing is stored, and the content is as of this read: the clock, the plan, its prices and the customer can change it before approval. The tax and the total are estimates from stored tax rates, not the tax provider's calculation. Grant discounts are not applied. A metered period that has already elapsed shows at zero usage, or at a minimum quantity in force for that period. `subscriptionId` holds the proposal id, because no subscription exists yet, so `GET /v0/subscriptions/{id}` answers 404 for it. The invoice has status `PROJECTED` and an id that is the same on every read, but `GET /v2/invoices/{id}` answers 404 for it. Needs the `subscriptionProposals:read` permission. The preview refuses what approve would refuse, with approve's answer. A plan, plan version or customer that no longer exists answers 404. A pending proposal blocks deleting its plan and its customer, so this happens only when a delete runs at the same time. A proposal of another merchant answers 404, as an unknown one does. 409 carries a `code`: `SUBSCRIPTION_PROPOSAL_NOT_PENDING` for a proposal that is not `pending`; `SUBSCRIPTION_PROPOSAL_INVALID` when the proposal fails a check subscription create makes, with `details.code` the failed check's own code and `details.details` its details, each only when the check has one; `SUBSCRIPTION_PROPOSAL_DUPLICATE` when the customer already has a live subscription for the plan's product, with its id in `details.subscriptionId`.

```
paygentic subscription-proposals list-subscription-proposal-projected-invoices [flags]
```

### Examples

```
  paygentic subscription-proposals list-subscription-proposal-projected-invoices --id <id>
```

### Options

```
  -h, --help         help for list-subscription-proposal-projected-invoices
  -i, --id string    The subscription proposal ID [required]
  -l, --limit int    Maximum number of invoices to return (default 10)
      --offset int   Number of invoices to skip for pagination
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
