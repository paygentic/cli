## paygentic plans create

Create

### Synopsis

Create

```
paygentic plans create [flags]
```

### Examples

```
  paygentic plans create --currency Won --merchant-id <id> --name <value>
```

### Options

```
      --billing-cadence string        ISO 8601 duration for the billing period. Takes precedence over billingInterval when both are provided. (options: P1M, P3M, P1Y)
      --billing-interval string       Recurring billing period frequency. Sample values: 'monthly' for monthly billing, 'quarterly' for quarterly billing, 'yearly' for annual billing (options: monthly, quarterly, yearly, annual)
      --billing-version string        Billing engine version. 0 = legacy fee-schedule billing (Legacy), 1 = line-item billing with metered usage support (Standard). (options: 0, 1) (default "0")
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --currency string               Three-letter ISO 4217 currency code for plan pricing. Must be one of the merchant's supported currencies. Sample values: 'USD' for US dollars, 'EUR' for euros, 'GBP' for British pounds [required]
      --default-tax-code string       Default tax code for plan line items. Common values: 'eservice' (electronically supplied services), 'saas' (software as a service), 'consulting', 'ebook', 'standard', 'reduced', 'exempt'. Full list available via GET /tax/codes endpoint. (default "eservice")
      --default-tax-rate float        Fallback tax rate percentage when automatic tax calculation fails. Sample values: 8.5 represents 8.5% tax, 10.0 represents 10% tax, 0 represents no tax
      --description string            Plan details explaining included features and limits. Sample values: 'Claude API access with 500K tokens monthly allowance', 'Unlimited cloud storage plus real-time analytics tools', 'Complete machine learning infrastructure with GPU access', 'Flexible usage-based pricing with no monthly commitment'
  -h, --help                          help for create
  -i, --invoice-display-name string   Plan name shown on billing statements. Sample values: 'LLM API Basic Plan', 'Data Warehouse Business', 'ML Platform Enterprise', 'Pay-Per-Use Model'
  -m, --merchant-id string            Unique identifier for an organization [required]
  -n, --name string                   Plan identifier visible to customers. Sample values: 'Basic Tier', 'Business Package', 'Enterprise Solution', 'Metered Billing', 'Free Tier', 'Premium Access' [required]
      --prices stringArray            Array of price IDs to associate with this plan
      --product-id string             Unique identifier for a product
      --renewal-reminder-days int     Number of days before renewal to send the reminder email (default 3)
      --renewal-reminder-enabled      Whether to send renewal reminder emails to customers before their subscription renews (default true)
  -t, --tax-behavior string           Whether tax is added on top of the price (exclusive) or included in the price (inclusive) (options: exclusive, inclusive) (default "exclusive")
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
