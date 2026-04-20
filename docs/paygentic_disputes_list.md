## paygentic disputes list

List

### Synopsis

List disputes for a merchant, customer, or consumer. At least one of merchantId, customerId, or consumerId must be provided.

```
paygentic disputes list [flags]
```

### Examples

```
  paygentic disputes list
```

### Options

```
      --consumer-id string   Filter disputes for a specific consumer. At least one of merchantId, customerId, or consumerId must be provided.
      --customer-id string   Filter disputes for a specific customer. At least one of merchantId, customerId, or consumerId must be provided.
  -h, --help                 help for list
  -l, --limit int            Number of disputes to return (default 10)
  -m, --merchant-id string   Filter disputes for a specific merchant. At least one of merchantId, customerId, or consumerId must be provided.
      --offset int           Number of disputes to skip
  -s, --status string        Filter by dispute status (options: pending, accepted, declined)
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

* [paygentic disputes](paygentic_disputes.md)	 - A `Dispute` enables customers to contest usage events that they consider to be inaccurately recorded or billed
