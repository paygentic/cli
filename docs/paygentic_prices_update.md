## paygentic prices update

Update

### Synopsis

Update

```
paygentic prices update [flags]
```

### Examples

```
  paygentic prices update --id <id>
```

### Options

```
      --billable-metric-id string     Unique identifier for a billable metric
      --billing-cadence string        ISO 8601 duration for recurring fees (e.g., 'P1M' for monthly, 'P1Y' for yearly, or 'P0D' for one-time)
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -f, --feature string                Feature to associate. Set to null to remove existing feature. Omit to leave unchanged.
  -g, --grant-discount-enabled        When true, grants applied to a subscription will discount usage charged by this price. Only supported for standard metered prices.
  -h, --help                          help for update
      --id string                     The unique identifier of the price [required]
      --invoice-display-name string   Updated invoice line item label. Sample values: 'LLM Token Usage', 'Storage Charges', 'API Call Fees'
  -m, --model string                  The pricing model to be used, which can be standard, dynamic, volume-based, or percentage-based. (options: standard, dynamic, volume, percentage)
      --payment-term string           Billing timing preference. For billable metrics: 'instant' (charges immediately) or 'in_arrears' (charges at period end). For fees: 'in_advance' (charges upfront) or 'in_arrears' (charges at period end). (options: instant, in_arrears, in_advance)
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
