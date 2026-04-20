## paygentic customers create

Create

### Synopsis

Create a new customer for a merchant organization. This endpoint is currently only used by the Paygentic platform as part of the subscription flow.

```
paygentic customers create [flags]
```

### Examples

```
  paygentic customers create --merchant-id org_YS8jkP59V71TdUvj
```

### Options

```
      --body string           Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --consumer consumerId   Fields to create a new consumer. Will use an existing consumer if one exists with the same email address. Required if consumerId is not provided. Address with complete tax information (country, state, zipCode) is required for tax calculation when using Paygentic Tax.
      --consumer-id string    Unique identifier for an organization
  -e, --external-id string    Merchant-defined identifier for this customer in their own system.
  -h, --help                  help for create
  -m, --merchant-id string    Unique identifier for an organization [required]
      --tax-id string         Optional business tax registration identifier. Sample values: 'GB123456789' for UK VAT, 'DE123456789' for German VAT, 'FR12345678901' for French VAT. Supplying this value enables inter-company tax handling and exemption from standard tax collection.
      --tax-rates string      An object mapping plan IDs, metric IDs, or 'default' to a tax rate percentage (e.g., 13 for 13%)
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

* [paygentic customers](paygentic_customers.md)	 - A `Customer` is an entity connected to a `Merchant` via a `Subscription`
