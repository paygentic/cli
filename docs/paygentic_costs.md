## paygentic costs

A Cost represents the operational or infrastructure expense of serving customers for a given product

### Synopsis

A Cost represents the operational or infrastructure expense of serving customers for a given product. Costs are metered (driven by event-based usage) and are tracked in parallel with billable metrics to give merchants visibility into both revenue and cost per customer.

```
paygentic costs [flags]
```

### Options

```
  -h, --help   help for costs
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
* [paygentic costs create](paygentic_costs_create.md)	 - Create
* [paygentic costs delete](paygentic_costs_delete.md)	 - Delete
* [paygentic costs get](paygentic_costs_get.md)	 - Get
* [paygentic costs get-cost-summary](paygentic_costs_get-cost-summary.md)	 - Query Summary
* [paygentic costs list](paygentic_costs_list.md)	 - List
* [paygentic costs update](paygentic_costs_update.md)	 - Update
