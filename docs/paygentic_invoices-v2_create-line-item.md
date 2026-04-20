## paygentic invoices-v2 create-line-item

Create Manual Line Item

### Synopsis

Create a manual line item for a billing v1 subscription. Manual line items are ad-hoc charges or credits that flow through the same collection pipeline as auto-generated items. Exactly one of subscriptionId or invoiceId must be provided.

```
paygentic invoices-v2 create-line-item [flags]
```

### Examples

```
  paygentic invoices-v2 create-line-item --body-param.display-name Nathan54 --body-param.currency Rwanda Franc --body-param.quantity 6214.31 --body-param.unit-price 7408.13
```

### Options

```
      --body string                         Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --body-param.currency string          ISO 4217 currency code (e.g., USD). Must match the subscription or invoice currency. [required]
      --body-param.description string       Optional longer description shown on the invoice.
      --body-param.display-name string      Human-readable label shown on the invoice. [required]
      --body-param.idempotency-key string   Optional caller-provided idempotency key. Auto-generated if not provided.
      --body-param.invoice-at string        When to collect this item into an invoice. Defaults to now. Ignored when invoiceId is provided.
      --body-param.invoice-id string        The invoice ID to attach this item directly to. Exactly one of subscriptionId or invoiceId must be provided. The invoice must be in ACTIVE or CLOSING state.
      --body-param.period-end string        End of the billing period for display purposes. Defaults to now.
      --body-param.period-start string      Start of the billing period for display purposes. Defaults to now.
      --body-param.quantity float           Number of units. [required]
      --body-param.subscription-id string   The subscription ID. Exactly one of subscriptionId or invoiceId must be provided.
      --body-param.unit-price float         Price per unit as a decimal amount (e.g., 29.99 for $29.99). Can be negative for credits or adjustments. [required]
  -h, --help                                help for create-line-item
  -i, --idempotency-key string              Optional idempotency key. If provided, duplicate requests with the same key return the previously created item.
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

* [paygentic invoices-v2](paygentic_invoices-v2.md)	 - Invoice V2 operations supporting billing cycles organized by time periods
