## paygentic payments list

List Payments

### Synopsis

List payments for the authenticated merchant with optional filters.

```
paygentic payments list [flags]
```

### Examples

```
  paygentic payments list
```

### Options

```
  -c, --customer-id string   Filter by customer ID.
  -h, --help                 help for list
  -l, --limit int            Number of payments to return. (default 10)
  -m, --merchant-id string   Merchant organization ID. Required when using an API key that is not scoped to a single merchant.
      --offset int           Number of payments to skip.
  -s, --status string        Filter by payment status. (options: pending, processing, completed, expired, cancelled)
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

* [paygentic payments](paygentic_payments.md)	 - Create and manage one-off payments
