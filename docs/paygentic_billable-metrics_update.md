## paygentic billable-metrics update

Update

### Synopsis

Update

```
paygentic billable-metrics update [flags]
```

### Examples

```
  paygentic billable-metrics update --id <id>
```

### Options

```
      --body string             Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --description string      Revised explanation of what the metric represents. Sample values: 'Language model token consumption', 'Database storage capacity used', 'Machine learning prediction API calls', 'AI-generated content items'
      --event-from string       Only count events after this timestamp.
      --event-type string       CloudEvents type for meter routing.
  -g, --group-by string         Map of dimension name to JSONPath for group-by queries.
  -h, --help                    help for update
  -i, --id string               [required]
  -n, --name string             Updated label for the metric. Sample values: 'LLM Tokens', 'Database Storage', 'Prediction Requests', 'Content Generations'
  -u, --unit string             Updated measurement unit. Common examples: 'tokens', 'GB', 'requests', 'items', 'hours'
  -v, --value-property string   JSONPath to extract numeric value from event data.
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
