## paygentic orders create

Create an order

### Synopsis

Create an order

```
paygentic orders create [flags]
```

### Examples

```
  paygentic orders create --customer-id <id> --currency Bhutanese Ngultrum --term-start-date 2024-07-21T22:30:59.168Z --term-end-date 2026-01-25T22:12:02.280Z --total-amount <value>
```

### Options

```
      --body string                     Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --close-date string               date/time value
      --currency string                 [required]
      --customer-id string              [required]
      --default-payment-term-days int   integer value
  -h, --help                            help for create
  -l, --line-items string               list of values
  -m, --metadata string                 value
  -r, --reseller-id string              string value
  -s, --selling-entity string           string value
      --tax-exempt                      boolean flag
      --term-end-date string            [required]
      --term-start-date string          [required]
      --total-amount string             [required]
      --type string                     options: new_business, renewal, expansion
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

* [paygentic orders](paygentic_orders.md)	 - Manage Orders, their line items, and billing schedules
