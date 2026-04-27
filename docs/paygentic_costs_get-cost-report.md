## paygentic costs get-cost-report

Report

### Synopsis

Aggregate cost data across costs and customers with grouping, filtering, and time-series breakdown.

```
paygentic costs get-cost-report [flags]
```

### Examples

```
  paygentic costs get-cost-report --from 2025-03-21T13:37:39.948Z --to 2024-04-29T10:02:17.490Z --group-by cost
```

### Options

```
      --compare-prior-period     When true, include prior-period comparison data in each group.
      --cost-id stringArray      Filter to specific cost(s). Enables dynamic dimension grouping.
      --currency string          Filter costs to a single ISO 4217 currency code (e.g. 'USD'). When omitted, defaults to the merchant's primary currency.
      --filter-group-by string   JSON-encoded dimension filters (e.g. {"region":"us-east-1"}). Max 4KB, max 5 keys.
      --from string              Start of the query window (ISO 8601). [required]
  -g, --group-by string          Dimension to group results by. Valid values: 'cost' (group by cost ID), 'customer' (group by customer ID), or any dimension key from a filtered cost's groupBy schema for dynamic dimension grouping. Dynamic dimension values require exactly one costId filter. [required]
  -h, --help                     help for get-cost-report
  -l, --limit int                Maximum number of groups to return. (default 25)
  -m, --merchant-id string       The merchant organization ID. If omitted, defaults to the merchant associated with the authenticated API key.
      --offset int               Number of groups to skip for pagination.
      --sort string              Field to sort groups by. (options: totalCost, totalQuantity) (default "totalCost")
      --sort-dir string          Sort direction. (options: asc, desc) (default "desc")
      --subject string           Filter to a specific subject (customer/event subject ID).
      --to string                End of the query window (ISO 8601). [required]
      --top-n int                Number of top groups to return. An 'Other' bucket aggregates remaining groups. (default 9)
  -w, --window-size string       Time window granularity for the time-series breakdown. (options: HOUR, DAY, MONTH)
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

* [paygentic costs](paygentic_costs.md)	 - A Cost represents the operational or infrastructure expense of serving customers for a given product
