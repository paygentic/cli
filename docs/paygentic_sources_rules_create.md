## paygentic sources rules create

Create Rule

### Synopsis

Create a rule for automatically approving source events. When a pending source event matches ALL conditions in a rule, it will be automatically approved and converted to a usage event. Rules are evaluated in order (lowest order number first), and the first matching rule triggers auto-approval. Maximum 10 rules per source.

```
paygentic sources rules create [flags]
```

### Examples

```
  paygentic rules create --conditions '[]' --name <value> --source-id <id>
```

### Options

```
      --body string          Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --conditions string    Conditions that must ALL be met (AND logic) for auto-acceptance. Sample values: customerEmail domain='@trusted.com' AND amount lessThan=1000, customerId equals='org_abc123' AND billableMetricId equals='bm_tokens', subscriptionId equals='sub_xyz789' AND quantity greaterThan=100 [required]
      --description string   Detailed description of what this source rule does
  -e, --enabled              Whether this rule should be active immediately (default true)
  -h, --help                 help for create
  -n, --name string          Human-readable name for the source rule [required]
      --order int            Evaluation priority (0-999). Lower numbers are evaluated first. First matching rule triggers auto-acceptance.
  -s, --source-id string     Unique identifier for a source [required]
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

* [paygentic sources rules](paygentic_sources_rules.md)	 - Operations for rules
