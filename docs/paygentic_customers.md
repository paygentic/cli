## paygentic customers

A `Customer` is an entity connected to a `Merchant` via a `Subscription`

### Synopsis

A `Customer` is an entity connected to a `Merchant` via a `Subscription`. This represents the merchant-facing perspective of `Consumers` who purchase their `Products`.

```
paygentic customers [flags]
```

### Options

```
  -h, --help   help for customers
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

* [paygentic](paygentic.md)	 - Paygentic API: The Paygentic API provides billing infrastructure for usage-based and subscription monetization — customers, subscriptions, usage metering, invoicing, entitlements, and payments
* [paygentic customers create](paygentic_customers_create.md)	 - Create
* [paygentic customers delete](paygentic_customers_delete.md)	 - Delete
* [paygentic customers get](paygentic_customers_get.md)	 - Get
* [paygentic customers list](paygentic_customers_list.md)	 - List by Merchant
* [paygentic customers update](paygentic_customers_update.md)	 - Update
