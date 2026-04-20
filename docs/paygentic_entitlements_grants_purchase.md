## paygentic entitlements grants purchase

Purchase Grant

### Synopsis

Create an ad-hoc invoice with a payment session for a grant purchase. The customer pays via the returned payment URL; the grant is created automatically on payment completion. If payment expires, the invoice is cancelled and no grant is created.

After the consumer completes payment, the grant is created automatically. To confirm payment completion, poll `GET /v2/invoices/{invoiceId}` using the `invoiceId` from the response and check for `status === "PAID"`. Recommended polling interval: 2 seconds, timeout: 60 seconds.

```
paygentic entitlements grants purchase [flags]
```

### Examples

```
  paygentic grants purchase --entitlement-id <id> --amount 1000 --price 5.00 --idempotency-key purchase-march-2026-topup
```

### Options

```
  -a, --amount float                The number of credits to grant upon payment completion. [required]
      --body string                 Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --cancel-url string           URL to redirect the customer to if payment is cancelled.
      --effective-at string         When the grant becomes effective. Defaults to now.
      --entitlement-id string       The unique identifier of the entitlement to purchase credits for. [required]
      --expires-at string           When the grant expires. If omitted, the grant does not expire.
  -h, --help                        help for purchase
  -i, --idempotency-key string      Caller-provided deduplication key. Retrying with the same key returns the existing invoice. [required]
      --payment-expires-at string   When the payment session expires. If omitted, uses the default expiry.
      --price string                The price in decimal format (e.g., '5.00' for $5.00 USD). Must be at least $0.50. [required]
  -s, --success-url string          URL to redirect the customer to after successful payment.
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

* [paygentic entitlements grants](paygentic_entitlements_grants.md)	 - Operations for grants
