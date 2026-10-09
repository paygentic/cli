## paygentic invoices-v2 record-invoice-payment

Settle Invoice Payment

### Synopsis

Settle an unpaid invoice in status `ISSUED` or `PAYMENT_FAILED`. The `method` field selects how.

- `hosted_link`: create a new hosted payment link and email it to the customer. The invoice stays unpaid until the customer pays on the link. Each call replaces the previous link. A payment link expires after 30 days; to collect an invoice whose link has expired, call this method again.
- `out_of_band`: record a payment that you collected outside Paygentic. The invoice changes to `PAID` immediately. A second call returns 409.

For `hosted_link`, an invoice that does not exist returns 403, the same as an invoice of another merchant.

Paygentic selects the payment provider from your connected payment account. The response reports the provider.

**Warning:** each `hosted_link` call creates a new link and sends the customer a new email. Do not retry a `hosted_link` call after a timeout: first read the invoice to see if a new link exists.

```
paygentic invoices-v2 record-invoice-payment [flags]
```

### Examples

```
  paygentic invoices-v2 record-invoice-payment --id <id> --method hosted_link
```

### Options

```
      --body string          Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help                 help for record-invoice-payment
  -i, --id string            The invoice ID [required]
  -m, --method string        How an invoice payment is settled. (options: out_of_band, hosted_link) [required]
  -r, --reason out_of_band   Optional note for out_of_band that describes how you received the payment (for example, 'Wire transfer received 2026-03-25'). Ignored for `hosted_link`.
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
