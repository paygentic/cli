## paygentic revenue get

Get revenue summary

### Synopsis

Returns revenue summary with invoice and payment breakdowns (outstanding/paid/writtenOff), plus a time-series trend. Revenue is sourced from all issued invoices (v0 + v1) and completed payments.

```
paygentic revenue get [flags]
```

### Examples

```
  paygentic revenue get --start-time 2024-07-23T16:05:39.311Z --end-time 2026-04-29T18:43:05.586Z
```

### Options

```
  -b, --bucket-width string            Time bucket granularity for trend data (options: hour, day, week) (default "day")
  -c, --customer-id string             Filter by customer ID. At least one of merchantId, subscriptionIds, or customerId must be provided.
  -e, --end-time string                End of the time range (ISO 8601 format) [required]
  -g, --group-by string                Group invoice data by dimension. Max 5 groups (top 4 + 'other' when exceeding). (options: plan)
  -h, --help                           help for get
  -m, --merchant-id string             Filter by merchant ID. At least one of merchantId, subscriptionIds, or customerId must be provided.
      --start-time string              Start of the time range (ISO 8601 format) [required]
      --subscription-ids stringArray   Filter by subscription IDs. At least one of merchantId, subscriptionIds, or customerId must be provided.
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
