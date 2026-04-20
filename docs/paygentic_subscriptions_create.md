## paygentic subscriptions create

Create

### Synopsis

Creates a subscription for an existing customer or creates a new customer as part of the action.

```
paygentic subscriptions create [flags]
```

### Examples

```
  paygentic subscriptions create --name Monthly API Service --plan-id plan_abc123 --started-at 2024-01-15T00:00:00Z
```

### Options

```
  -a, --auto-charge                       Enable automatic charging of invoices using stored payment methods. When true, invoices will be automatically paid using off-session payment. Defaults to false.
      --body string                       Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --customer customerId               Fields to create a new customer and consumer. Will use an existing consumer if one exists with the same email address. Required if customerId is not provided. Address with complete tax information (country, state, zipCode) is required for tax calculation when using Paygentic Tax.
      --customer-id string                Unique identifier for a customer
  -e, --ending-at string                  Subscription expiration timestamp in ISO 8601 format. Sample values: '2024-12-31T23:59:59Z', '2025-01-15T10:30:00Z'. Omit for indefinite subscriptions.
  -h, --help                              help for create
  -m, --minimum-account-balance string    Minimum wallet balance requirement in decimal dollars (e.g., '100.00'). Can be set to '0' to disable. The system will calculate the difference between this minimum and the customer's current balance, charging only what's needed to reach the minimum. If the customer already has sufficient balance, no charge is made. Note: If the calculated charge amount is below payment processor minimums (typically $1.00), it will be automatically adjusted upward to meet the minimum requirement. Sample values: '200.00' requires minimum $200 balance for metered LLM usage, '1000.00' requires minimum $1000 balance for data processing services
  -n, --name string                       Subscription identifier combining customer and service details. Sample values: 'TechCorp - LLM API Access', 'Analytics Co - Data Platform Enterprise', 'StartupXYZ - Image Generation Service', 'Enterprise Inc - ML Training Platform' [required]
      --plan-id string                    Unique identifier for a plan [required]
      --prefund-amount string             @deprecated Use minimumAccountBalance instead. Required initial wallet deposit amount. Sample values: '200.00' requires $200 prepaid balance for metered LLM usage, '1000.00' requires $1000 prepaid credits for data processing services, '50.00' requires $50 minimum for API call consumption
      --redirect-urls string              Optional redirect URLs after payment completion or failure. If not provided, uses default platform behavior.
      --renewal-reminder-days string      Override plan setting for number of days before renewal to send the reminder. Only used if renewalReminderEnabled is true (or inherited from plan). Set to null to use plan default.
      --renewal-reminder-enabled string   Override plan setting for renewal reminder emails. When set, this subscription's setting takes precedence over the plan default. Set to true to enable reminders, false to disable, or null/omit to use plan default.
      --session-expiry-minutes float      Number of minutes until the payment session expires. Defaults to 240 minutes (4 hours) if not provided.
      --started-at string                 Subscription activation timestamp in ISO 8601 format. Sample values: '2024-01-15T10:30:00Z', '2024-02-01T00:00:00Z' [required]
      --tax-exempt                        When true, forces tax rate to 0%. Use for customers with verified tax-exempt status.
      --test-clock-id string              Test clock identifier for simulating time-based billing scenarios. Sample values: 'tc_abc123xyz', 'tc_789def456'. Restricted to non-production environments (local, dev, sandbox). Must belong to the same merchant organization.
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
