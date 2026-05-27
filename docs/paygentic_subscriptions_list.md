## paygentic subscriptions list

List

### Synopsis

List

```
paygentic subscriptions list [flags]
```

### Examples

```
  paygentic subscriptions list
```

### Options

```
      --consumer-id merchantId   Return subscriptions for this consumer organization. May be combined with merchantId to scope to a single consumer/merchant pair. Cannot be combined with `customerId`.
      --customer-id consumerId   Return subscriptions for this customer. Cannot be combined with consumerId or `merchantId`.
  -h, --help                     help for list
  -i, --include string           Include related resources. When 'customer' is specified, each subscription includes merchant and consumer details. (options: customer)
  -l, --limit string             Number of subscriptions to return (default "10")
  -m, --merchant-id consumerId   Return subscriptions for this merchant organization. May be combined with consumerId to scope to a single consumer/merchant pair. Cannot be combined with `customerId`.
      --offset string            Number of subscriptions to skip (default "0")
      --started-before string    Filter subscriptions started at or before this ISO 8601 date-time
      --status string            options: active, terminated, pending_payment
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

* [paygentic subscriptions](paygentic_subscriptions.md)	 - A `Subscription` is a customer's commitment to purchase a `Product` following the terms of a `Plan` and its linked `Prices`
