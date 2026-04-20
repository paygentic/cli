## paygentic plans list-available

List Available Plans

### Synopsis

Retrieves all plans for a merchant that the customer does not have an active or pending subscription for. When a customer has a subscription for any plan within a product, all plans from that product are excluded.

```
paygentic plans list-available [flags]
```

### Examples

```
  paygentic plans list-available --customer-id <id>
```

### Options

```
  -c, --customer-id string   The customer to check subscriptions for. The merchant is derived from the customer record. [required]
  -h, --help                 help for list-available
  -l, --limit int            Number of plans to return (default 10)
      --offset int           Number of plans to skip
  -p, --product-id string    Optional filter by product ID
  -s, --search string        Optional search text to filter plan names (case-insensitive)
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

* [paygentic plans](paygentic_plans.md)	 - A `Plan` links a collection of `Prices` to a `Product`
