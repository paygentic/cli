## paygentic payments create

Create Payment

### Synopsis

Create a new payment for collecting a one-off charge. Returns a payment URL that can be shared with the customer.

```
paygentic payments create [flags]
```

### Examples

```
  paygentic payments create --amount 10.50 --currency USD
```

### Options

```
  -a, --amount string                 Payment amount in decimal format (e.g. '10.50'). Minimum 1.00, maximum 5,000.00. Contact support for higher limits. [required]
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --currency string               ISO 4217 currency code. (options: USD, EUR, GBP, AUD) [required]
      --customer-id string            Optional customer ID. Must belong to this merchant.
  -e, --expires-in string             ISO 8601 duration for the payment lifetime. Defaults to P30D (30 days). Maximum is P31D (31 days). Examples: PT1H, P1D, P7D, P30D.
  -f, --failure-redirect-url string   URL to redirect the customer to after a failed payment.
  -h, --help                          help for create
  -i, --idempotency-key string        Client-provided key for safe retries. If a payment with the same key already exists, the existing payment is returned.
  -l, --line-items string             Optional breakdown of what the customer is being charged for.
      --merchant-id string            Merchant organization ID. Required when using an API key that is not scoped to a single merchant.
      --metadata string               Arbitrary key-value string pairs to attach to the payment.
  -r, --reference string              Merchant-defined reference for this payment (e.g. order ID, invoice number).
      --save-payment-method           Whether to save the customer's payment method for future use. Defaults to false.
      --success-redirect-url string   URL to redirect the customer to after a successful payment.
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

* [paygentic payments](paygentic_payments.md)	 - Create and manage one-off payments
