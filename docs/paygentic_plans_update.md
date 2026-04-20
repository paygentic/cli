## paygentic plans update

Update

### Synopsis

Update

```
paygentic plans update [flags]
```

### Examples

```
  paygentic plans update --id <id>
```

### Options

```
      --billing-cadence string        ISO 8601 duration for the billing period. Takes precedence over billingInterval when both are provided. (options: P1M, P3M, P1Y)
      --billing-interval string       Recurring billing period frequency. Sample values: 'monthly' for monthly billing, 'quarterly' for quarterly billing, 'yearly' for annual billing (options: monthly, quarterly, yearly, annual)
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --default-tax-code string       Default tax code for plan line items. Common values: 'eservice' (electronically supplied services), 'saas' (software as a service), 'consulting', 'ebook', 'standard', 'reduced', 'exempt'. Full list available via GET /tax/codes endpoint.
      --default-tax-rate float        Fallback tax rate (as percentage) if automatic tax calculation is unavailable
      --description string            Plan details explaining included features and limits. Sample values: 'Claude API access with 500K tokens monthly allowance', 'Unlimited cloud storage plus real-time analytics tools', 'Complete machine learning infrastructure with GPU access', 'Flexible usage-based pricing with no monthly commitment'
  -h, --help                          help for update
      --id string                     The unique identifier of the plan [required]
      --invoice-display-name string   Plan name shown on billing statements. Sample values: 'LLM API Basic Plan', 'Data Warehouse Business', 'ML Platform Enterprise', 'Pay-Per-Use Model'
  -n, --name string                   Plan identifier visible to customers. Sample values: 'Basic Tier', 'Business Package', 'Enterprise Solution', 'Metered Billing', 'Free Tier', 'Premium Access'
  -p, --prices stringArray            Array of price IDs to associate with this plan
      --renewal-reminder-days int     Number of days before renewal to send the reminder email
      --renewal-reminder-enabled      Whether to send renewal reminder emails to customers before their subscription renews
  -t, --tax-behavior string           Whether tax is added on top of the price (exclusive) or included in the price (inclusive) (options: exclusive, inclusive)
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

* [paygentic plans](paygentic_plans.md)	 - A `Plan` links a collection of `Prices` to a `Product`
