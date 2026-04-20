## paygentic billable-metrics create

Create

### Synopsis

Create a new billable metric for a merchant organization. A `Billable Metric` represents a metric that can be used to measure the usage of a `Product`. It contains information about the metric, such as its name, description, and units.

```
paygentic billable-metrics create [flags]
```

### Examples

```
  paygentic billable-metrics create --aggregation SUM --description Tracks total tokens consumed per API call. --merchant-id org_YS8jkP59V71TdUvj --name Token Counter --product-id prod_abc123
```

### Options

```
  -a, --aggregation string      Aggregation calculation method for metric values. (options: SUM, COUNT, AVG, MIN, MAX, UNIQUE_COUNT, LATEST) [required]
      --body string             Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --description string      Explanatory text describing what the metric tracks and how it's used for billing. Sample values: 'Total tokens consumed by Claude language model interactions', 'Gigabytes of cloud storage utilized', 'Count of machine learning inference requests processed', 'Quantity of AI-generated images created', 'Compute hours spent training neural networks', 'Terabytes of data transferred' [required]
      --event-from string       Only count events after this timestamp. Used for meter versioning.
      --event-type string       CloudEvents type for meter routing. Links this billable metric to the metering service.
  -g, --group-by string         Map of dimension name to JSONPath for group-by queries.
  -h, --help                    help for create
  -m, --merchant-id string      Unique identifier for an organization [required]
  -n, --name string             Human-readable label identifying what this metric measures. Sample values: 'Claude Tokens', 'Storage Capacity', 'Model Inference Calls', 'Generated Images', 'Training Compute Hours', 'Data Transfer Volume' [required]
  -p, --product-id string       Unique identifier for a product [required]
  -u, --unit string             Measurement unit used when aggregating this metric's values. Common examples: 'tokens', 'GB', 'calls', 'images', 'hours', 'TB', 'queries', 'requests' [required]
  -v, --value-property string   JSONPath to extract numeric value from event data. Required for SUM/AVG/MIN/MAX/LATEST aggregations.
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
