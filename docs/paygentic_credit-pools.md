## paygentic credit-pools

A `CreditPool` is the `(customer, pricingUnit)` identity that credit-denominated prices draw down

### Synopsis

A `CreditPool` is the `(customer, pricingUnit)` identity that credit-denominated prices draw down. The balance itself lives on grants, not on the pool; the pool survives subscription changes. There is one pool per `(customer, pricingUnit)`.

```
paygentic credit-pools [flags]
```

### Options

```
  -h, --help   help for credit-pools
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
* [paygentic credit-pools create](paygentic_credit-pools_create.md)	 - Create or resolve
* [paygentic credit-pools create-credit-pool-grant](paygentic_credit-pools_create-credit-pool-grant.md)	 - Grant credits
* [paygentic credit-pools create-credit-pool-purchase](paygentic_credit-pools_create-credit-pool-purchase.md)	 - Purchase credits
* [paygentic credit-pools get](paygentic_credit-pools_get.md)	 - Get
* [paygentic credit-pools get-credit-pool-ledger](paygentic_credit-pools_get-credit-pool-ledger.md)	 - Get ledger
* [paygentic credit-pools list](paygentic_credit-pools_list.md)	 - List
* [paygentic credit-pools list-credit-pool-grants](paygentic_credit-pools_list-credit-pool-grants.md)	 - List grants
