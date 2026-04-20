## paygentic entitlements list

List Entitlements

### Synopsis

Retrieve all entitlements for a customer, optionally filtered by feature or product.

```
paygentic entitlements list [flags]
```

### Examples

```
  paygentic entitlements list --customer-id cus_q3r4s5t6u7v8w9x0
```

### Options

```
  -a, --at string                Evaluate balance and access at this point in time (RFC 3339 datetime with any UTC offset, e.g. 2024-01-15T10:30:00Z or 2024-01-15T15:30:00+05:30). Defaults to current time.
  -c, --customer-id string       The unique identifier of the customer to retrieve entitlements for. [required]
  -f, --feature-key productId    Filter results to a specific feature by its key. When specified, productId is also required. Use this to check access to a single feature.
  -h, --help                     help for list
  -l, --limit offset             Maximum number of entitlements to return per page. Use with offset for pagination. (default 10)
      --offset limit             Number of entitlements to skip. Use with limit for pagination through large result sets.
  -p, --product-id featureKey    Filter results to entitlements for a specific product. Required when featureKey is specified since feature keys are scoped to products.
  -s, --subscription-id string   Filter results to entitlements for a specific subscription.
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

* [paygentic entitlements](paygentic_entitlements.md)	 - An `Entitlement` grants a customer the right to access and use a specific product feature
