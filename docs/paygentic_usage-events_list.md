## paygentic usage-events list

List

### Synopsis

List

```
paygentic usage-events list [flags]
```

### Examples

```
  paygentic usage-events list --end-time 2026-03-29T00:23:32.822Z --start-time 2024-02-04T03:47:15.138Z
```

### Options

```
      --consumer-id string       Filter by consumer ID. This is only available if the caller is member of the consumer organization.
      --customer-id string       Filter by customer ID. This is only available if the caller is member of the merchant organization owning this customer.
  -e, --end-time string          ISO 8601 date-time string filtering events up to this timestamp. Sample values: '2024-01-31T23:59:59Z', '2024-02-28T12:00:00Z' [required]
  -h, --help                     help for list
  -l, --limit int                Number of usage events to return (default 10)
  -m, --merchant-id string       Filter by merchant ID. This is only available if the caller is member of the merchant organization.
      --offset int               Number of usage events to skip
      --start-time string        ISO 8601 date-time string filtering events from this timestamp onward. Sample values: '2024-01-15T00:00:00Z', '2024-02-01T10:30:00Z' [required]
      --subscription-id string   Filter by subscription ID. This is only available if the caller is member of the consumer or merchant organization owning this subscription.
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

* [paygentic usage-events](paygentic_usage-events.md)	 - Operations for usage-events
