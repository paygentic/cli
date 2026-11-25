## paygentic credit-pools create-credit-pool-purchase

Purchase credits

### Synopsis

Create a grant-purchase invoice for the pool's customer and advance it to a payment session. Price is server-derived from the pricing unit's conversion rate — the caller never supplies a price. On successful payment, the existing billing-worker settlement path mints the purchased credits as a grant on the pool; this endpoint does not mint the grant itself.

```
paygentic credit-pools create-credit-pool-purchase [flags]
```

### Examples

```
  paygentic credit-pools create-credit-pool-purchase --id <id> --grant-amount 5185.68 --idempotency-key <value>
```

### Options

```
      --body string                 Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --cancel-url string           URL to redirect the customer to if payment is cancelled.
      --effective-at string         When the grant becomes effective. Defaults to now.
      --expires-at string           When the grant expires. If omitted, the grant does not expire.
  -g, --grant-amount float          The number of credits to grant upon payment completion. [required]
  -h, --help                        help for create-credit-pool-purchase
      --id string                   [required]
      --idempotency-key string      Caller-provided deduplication key. Retrying with the same key returns the existing invoice. [required]
  -p, --payment-expires-at string   When the payment session expires. If omitted, uses the default expiry.
      --subscription-id string      The subscription to anchor the invoice to. Required to disambiguate when the pool's customer has more than one active subscription.
      --success-url string          URL to redirect the customer to after successful payment.
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

* [paygentic credit-pools](paygentic_credit-pools.md)	 - A `CreditPool` is the `(customer, pricingUnit)` identity that credit-denominated prices draw down
