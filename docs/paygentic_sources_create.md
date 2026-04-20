## paygentic sources create

Create

### Synopsis

Create a new source for automated usage event generation from external data sources.

```
paygentic sources create [flags]
```

### Examples

```
  paygentic sources create --name <value> --plan-id <id> --type stripe_revenue
```

### Options

```
      --body string              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --config-param string      Configuration specific to the source type. For stripe_revenue, must include ampersandProjectId.
      --description string       Optional explanation of the source's purpose. Sample values: 'Automated usage tracking from Stripe revenue data', 'Language model token consumption monitoring', 'Data warehouse query tracking', 'Machine learning inference usage collection'
  -e, --enabled                  Whether the source is enabled (default true)
  -h, --help                     help for create
  -m, --metadata string          Metadata for the source. For stripe_revenue, must include billableMetricMapping with revenue (billable metric ID).
  -n, --name string              Display label for the external data source. Sample values: 'Stripe Revenue Integration', 'LLM Usage Tracker', 'Data Processing Monitor', 'ML Compute Usage Source' [required]
      --plan-id string           Unique identifier for a plan [required]
      --processing-mode string   How events are processed - automatic (immediate) or manual (requires approval) (options: automatic, manual) (default "automatic")
  -t, --type string              The type of source. Currently only 'stripe_revenue' is supported. (options: stripe_revenue) [required]
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

* [paygentic sources](paygentic_sources.md)	 - A `Source` is an external data provider capable of automatically creating usage events
