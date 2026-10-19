## paygentic revenue get-revenue-accounts

List customer accounts

### Synopsis

Returns each customer's account as at today, one row per customer and currency, with a total per currency. Every figure covers all dates: there is no date window.

`outstanding` is what customers owe: every invoice with status `ISSUED` or `PAYMENT_FAILED`, at the amount due printed on the invoice (subtotal and tax, each rounded to the currency's minor unit), so it is gross of tax. Revenue (`GET /v0/revenue`) is net of tax. `outstanding` splits into `awaitingPayment` (status `ISSUED`) and `paymentFailed` (status `PAYMENT_FAILED`, collection has ended); the two always add up to it, in count and amount. A credit invoice (a negative amount due) nets against what is owed and is counted in no `count`; nor is an invoice whose amount due rounds to zero. A customer with nothing counted and nothing owed has no row.

Amounts are grouped by currency and never combined or converted. `totals` covers every row in the filter, not only the returned page, so the rows on one page add up to `totals` only when the page holds every row. Pages fetched in separate requests are separate reads.

```
paygentic revenue get-revenue-accounts [flags]
```

### Examples

```
  paygentic revenue get-revenue-accounts --merchant-id <id>
```

### Options

```
  -c, --customer-ids limit   Limit the rows and the totals to these customers of the merchant. A customer of another merchant, or one that does not exist, returns 404. A customer billed in several currencies has a row for each, so set limit to cover them.
  -h, --help                 help for get-revenue-accounts
  -l, --limit int            Number of rows to return (default 50)
  -m, --merchant-id string   Merchant whose customer accounts to report [required]
      --offset int           Number of rows to skip
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

* [paygentic revenue](paygentic_revenue.md)	 - Revenue data from invoices and payments
