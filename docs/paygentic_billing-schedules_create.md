## paygentic billing-schedules create

Create a billing schedule

### Synopsis

Create a billing schedule

```
paygentic billing-schedules create [flags]
```

### Examples

```
  paygentic billing-schedules create --start-date 2025-12-16T18:30:43.578Z --end-date 2024-09-07T07:24:23.517Z --billing-anchor 2025-10-01T16:17:23.367Z
```

### Options

```
  -a, --alignment-policy string        options: anchor, calendar, coterm
  -b, --billing-anchor string          [required]
      --body string                    Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --custom-period-windows string   list of values
  -e, --end-date string                [required]
  -h, --help                           help for create
  -m, --metadata string                value
      --order-id string                string value
      --payment-term-days string       integer value
      --period-preset string           options: single, P1M, P3M, P6M, P1Y, custom
      --proration-policy string        options: none, daily
      --start-date string              [required]
      --subscription-id string         string value
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

* [paygentic billing-schedules](paygentic_billing-schedules.md)	 - Owner-polymorphic billing schedules with intervals and staged invoice projections
