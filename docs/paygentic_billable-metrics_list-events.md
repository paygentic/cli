## paygentic billable-metrics list-events

List Meter Events

### Synopsis

List raw underlying events for a billable metric from the metering service. Returns events ordered by time descending.

```
paygentic billable-metrics list-events [flags]
```

### Examples

```
  paygentic billable-metrics list-events --id <id> --from 2024-09-28T08:04:20.478Z --to 2025-07-03T05:08:35.498Z
```

### Options

```
  -f, --from string      Start of query window (ISO 8601) [required]
  -h, --help             help for list-events
  -i, --id string        [required]
  -l, --limit int        Maximum number of events to return (default 20)
      --offset int       Number of events to skip
  -s, --subject string   Filter by subject (typically the customer/user ID)
  -t, --to string        End of query window (ISO 8601) [required]
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

* [paygentic billable-metrics](paygentic_billable-metrics.md)	 - Operations for billable-metrics
