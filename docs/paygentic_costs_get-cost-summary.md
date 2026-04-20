## paygentic costs get-cost-summary

Query Summary

### Synopsis

Query usage data and compute cost for a specific cost configuration. To retrieve summaries for all costs belonging to a merchant, first call listCosts to obtain cost IDs, then call this endpoint in parallel for each ID.

```
paygentic costs get-cost-summary [flags]
```

### Examples

```
  paygentic costs get-cost-summary --id <id> --from 2024-06-26T21:12:15.723Z --to 2026-01-05T23:33:29.000Z
```

### Options

```
      --filter-group-by string   JSON-encoded dimension filter (e.g. {"model":"gpt-4","region":"us-east"}). Keys must match those defined in the cost's groupBy configuration. Retrieve the cost first to determine valid keys.
      --from string              Start of the query window (ISO 8601). Required together with 'to'. [required]
  -g, --group-by string          Comma-separated dimension keys to group results by.
  -h, --help                     help for get-cost-summary
  -i, --id string                The unique identifier of the cost [required]
  -s, --subject string           Filter usage to a specific subject (billing entity). When provided, only cost events matching this subject are included. When omitted, usage is aggregated across all subjects for the merchant.
  -t, --to string                End of the query window (ISO 8601). Required together with 'from'. [required]
  -w, --window string            Time window granularity for time-series breakdown. (options: MINUTE, HOUR, DAY)
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
