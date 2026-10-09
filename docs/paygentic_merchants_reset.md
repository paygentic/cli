## paygentic merchants reset

Reset a merchant's data

### Synopsis

With `scope: merchant`, deletes the merchant's customers and everything attached to them: subscriptions, invoices, line items, payments, entitlements, grants, orders, test clocks, usage events, invoice documents and, when tax is enabled, the documents in the merchant's Quaderno sandbox account. `keepCatalog: true` keeps the catalog (products, plans, prices, fees, features, billable metrics), and `keepCatalog: false` deletes it too; the merchant's configuration is always kept. With `scope: customer`, deletes one customer and what is attached to it; test clocks and the Quaderno account's documents are kept, since they belong to no single customer.

A `204` means every delete is done or scheduled: usage events and Quaderno documents finish in the background, and usage events still being ingested while it runs can survive it. A `502` means a store outside Postgres failed; the customers are already out of the API, and calling again with the same body finishes the reset. Calling again is always safe. While a customer waits for that, its external id is free for a new customer to take; a retry then deletes usage events by customer id only.

Not available in production.

```
paygentic merchants reset [flags]
```

### Examples

```
  paygentic merchants reset --merchant-id <id>
```

### Options

```
      --body string                              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -b, --body-param string                        JSON value (variants: merchant: { keepCatalog: boolean }, customer: { customerId: string })
      --body-param.customer string               CustomerScope variant as JSON
      --body-param.customer.customer-id string   Unique identifier for a customer [required]
      --body-param.merchant string               MerchantScope variant as JSON
      --body-param.merchant.keep-catalog false   false also deletes the catalog: products, plans, plan versions, prices, fees, features, billable metrics, pricing units, items, costs and sources, back to an empty account. [required]
  -h, --help                                     help for reset
  -m, --merchant-id string                       [required]
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

* [paygentic merchants](paygentic_merchants.md)	 - Operations for merchants
