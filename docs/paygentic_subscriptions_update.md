## paygentic subscriptions update

Update

### Synopsis

Update

```
paygentic subscriptions update [flags]
```

### Examples

```
  paygentic subscriptions update --id <id>
```

### Options

```
  -a, --auto-charge                       Enable or disable automatic charging of invoices using stored payment methods.
      --body string                       Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -e, --ending-at string                  date/time value
  -h, --help                              help for update
  -i, --id string                         [required]
  -m, --minimum-account-balance string    Minimum wallet balance requirement in decimal dollars (e.g., '100.00'). Can be set to '0' to disable. Maximum allowed is $5,000. Contact support for higher limits. Note: If the calculated charge amount at renewal is below payment processor minimums (typically $1.00), it will be automatically adjusted upward to meet the minimum requirement. Changes apply at next renewal.
  -p, --payment-term-days int             Payment term in days ("Net X") applied to subsequently generated invoices: invoice dueAt = invoice issue date + paymentTermDays. A non-zero value is only valid alongside bankTransferOnly=true. Set 0 for "due on issue". Already-issued invoices keep their snapshotted dueAt.
      --renewal-reminder-days string      Override plan setting for number of days before renewal to send the reminder. Set to null to use plan default.
      --renewal-reminder-enabled string   Override plan setting for renewal reminder emails. Set to true to enable, false to disable, or null to use plan default.
  -s, --status string                     options: active, terminated
      --tax-exempt                        When true, forces tax rate to 0%.
      --terminated-at string              date/time value
      --terminated-by string              Identifier of entity that cancelled the subscription. Sample values: 'cust_abc123' for customer-initiated cancellation, 'org_xyz789' for merchant-initiated cancellation
      --termination-reason string         Explanation for subscription cancellation. Sample values: 'Customer requested cancellation', 'Payment failure', 'Service migration', 'Contract expiration'
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
