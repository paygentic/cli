## paygentic costs create

Create

### Synopsis

Create a new metered cost for a product.

```
paygentic costs create [flags]
```

### Examples

```
  paygentic costs create --type metered --name <value> --unit-cost 6810 --currency Swedish Krona --product-id <id>
```

### Options

```
  -a, --aggregation string      Aggregation method for the metered event. (options: SUM, COUNT, AVG, MIN, MAX, UNIQUE_COUNT, LATEST) [required]
      --body string             Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --currency string         ISO 4217 currency code (e.g. USD, EUR). [required]
  -e, --event-type string       CloudEvents type that identifies the metered event. [required]
  -g, --group-by string         Map of dimension name to JSONPath for group-by queries. Only valid for metered costs.
  -h, --help                    help for create
  -m, --merchant-id string      Unique identifier for an organization
  -n, --name string             Human-readable name for the cost. [required]
  -p, --product-id string       Unique identifier for a product [required]
  -t, --type metered            The cost type. Only metered costs are supported; they track usage via events. (options: metered) [required]
      --unit string             Unit label for metered costs (e.g. 'token', 'request'). Only valid for metered costs.
      --unit-cost float         Cost per unit, multiplied by measured quantity to compute total cost. Must be non-negative. [required]
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

* [paygentic costs](paygentic_costs.md)	 - A Cost represents the operational or infrastructure expense of serving customers for a given product
