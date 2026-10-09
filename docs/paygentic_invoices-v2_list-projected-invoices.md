## paygentic invoices-v2 list-projected-invoices

List projected

### Synopsis

List the invoices a subscription will issue in a range of invoice moments, one projected invoice for each distinct invoice moment. Projected invoices are derived on each read and never stored. Each has status PROJECTED, and its id is stable between reads, but GET /v2/invoices/{id} returns 404 for it. Totals EXCLUDE usage: metered charges are not projected, and an invoice moment that has only metered charges is omitted. Tax and sequenceNumber are estimates. The range filters on the invoice moment (invoiceAt) in [from, to). A from before now is treated as now. to must be after from and at most one year after now; now is the subscription's test-clock time when it has a test clock. A terminated subscription returns an empty list. Each invoice carries its lines in lineItems. Authorization is the same as listing invoices.

```
paygentic invoices-v2 list-projected-invoices [flags]
```

### Examples

```
  paygentic invoices-v2 list-projected-invoices --subscription-id <id>
```

### Options

```
  -f, --from string              Start of the range of invoice moments, inclusive. Defaults to now. A value before now is treated as now.
  -h, --help                     help for list-projected-invoices
  -l, --limit int                Maximum number of invoices to return (default 10)
      --offset int               Number of invoices to skip for pagination
  -s, --subscription-id string   The subscription to project invoices for [required]
  -t, --to string                End of the range of invoice moments, exclusive. Defaults to one month after from. Must be after from and at most one year after now.
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
