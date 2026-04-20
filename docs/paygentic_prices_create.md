## paygentic prices create

Create

### Synopsis

Create

```
paygentic prices create [flags]
```

### Examples

```
  paygentic prices create --invoice-display-name <value> --payment-term instant --properties '{"default":"<value>","parameters":{"function":"linear","gradient":"<value>","max":"<value>","min":"<value>"} }'
```

### Options

```
      --billable-metric-id string     Unique identifier for a billable metric
      --billing-cadence string        ISO 8601 duration for recurring charges (e.g., 'P1M' for monthly, 'P1Y' for yearly) or 'P0D' for one-time charges. Required for fees, optional for billable metrics. Sample values: 'P0D' for one-time, 'P1M' for monthly recurring, 'P1Y' for yearly recurring
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --feature string                JSON object
      --fee-id string                 The unique identifier for the fee referred to by this price. Either billableMetricId or feeId must be provided.
  -g, --grant-discount-enabled        When true, grants applied to a subscription will discount usage charged by this price. Only supported for standard metered prices.
  -h, --help                          help for create
  -i, --invoice-display-name string   Line item label shown on customer invoices. Sample values: 'Claude Token Consumption', 'Storage Usage (GB)', 'Inference API Calls', 'Image Generation Count', 'Training Compute Hours', 'Data Transfer (TB)' [required]
  -m, --model string                  Pricing calculation model. Required for billable metrics, optional for fees (defaults to 'standard'). (options: standard, dynamic, volume, percentage)
      --payment-term string           Billing timing preference. For billable metrics: 'instant' (charges immediately) or 'in_arrears' (charges at period end). For fees: 'in_advance' (charges upfront) or 'in_arrears' (charges at period end). (options: instant, in_arrears, in_advance) [required]
      --properties string             JSON value (one of: { unitPrice: string } | { maxPrice: string, minPrice: string } | { default: string, parameters: object } | { maxCharge: string, minCharge: string, percentage: string })
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

* [paygentic prices](paygentic_prices.md)	 - A `Price` determines the monetary value for a single unit of a `Billable Metric`
