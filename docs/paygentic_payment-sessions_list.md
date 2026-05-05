## paygentic payment-sessions list

List

### Synopsis

List payment sessions for the authenticated merchant with optional filters. Supports filtering by subscriptionId, customerId, status, and entityType. When subscriptionId is provided the result includes both the subscription's own activation session (entityType='subscription') and any session attached to invoices for that subscription (entityType='invoice').

```
paygentic payment-sessions list [flags]
```

### Examples

```
  paygentic payment-sessions list
```

### Options

```
  -c, --customer-id string       Filter to sessions linked to a payment for this customer.
  -e, --entity-type string       Filter by the kind of entity the session pays for. (options: invoice, subscription, payment, topup)
  -h, --help                     help for list
  -l, --limit int                Number of sessions to return. (default 10)
  -m, --merchant-id string       Merchant organization ID. Required when using an API key that is not scoped to a single merchant.
      --offset int               Number of sessions to skip.
      --status string            Filter by payment session status. (options: pending, processing, completed, failed, expired, cancelled)
      --subscription-id string   Filter to sessions linked to this subscription (its own activation session plus all of its invoices' sessions).
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

* [paygentic payment-sessions](paygentic_payment-sessions.md)	 - Handle payment session lifecycle and processing across various entity types including invoices and subscriptions
