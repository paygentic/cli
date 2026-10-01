## paygentic profitability get

Get profitability summary

### Synopsis

Returns a per-customer profitability summary for a merchant over a date range. Each row aggregates revenue (from issued + paid invoices), cost (from metered cost discovery), profit, and margin. Customers are ranked by profit descending and capped at topN; the remainder is rolled into a single self-consistent 'Other' row whose revenue, cost, and profit reflect the same set of customers. Rows are inner-joined against the merchant's customer list, so orphaned meter subjects from deleted or unknown customers are dropped.

```
paygentic profitability get [flags]
```

### Examples

```
  paygentic profitability get --merchant-id <id> --from 2026-09-10T15:32:06.535Z --to 2026-10-20T08:45:45.521Z
```

### Options

```
  -c, --currency string                ISO 4217 currency code to scope the summary. Defaults to the merchant's primary currency.
  -e, --exclude-empty rows             When true, leave customers with neither revenue nor cost in the period out of rows. They are dropped before ranking, so they take no top-N slot and are not folded into the 'Other' row. `emptyCustomerCount` says how many there are either way.
  -f, --from string                    Start of the time range (ISO 8601 format) [required]
  -h, --help                           help for get
  -i, --include-empty emptyCustomers   When true, also return in emptyCustomers the customers counted in `emptyCustomerCount` that `rows` does not carry, so a caller can show the complete customer list.
  -m, --merchant-id string             Merchant whose customers to summarize [required]
      --to string                      End of the time range (ISO 8601 format) [required]
      --top-n int                      Number of top customers (by profit) to return individually. The rest are rolled into a single 'Other' row. (default 10)
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

* [paygentic profitability](paygentic_profitability.md)	 - Per-customer profitability summaries
