## paygentic orders create-order-line-item

Add a line item

### Synopsis

Add a line item

```
paygentic orders create-order-line-item [flags]
```

### Examples

```
  paygentic orders create-order-line-item --order-id <id> --quantity <value> --list-unit-price <value> --unit-price <value> --total-price <value>
```

### Options

```
      --body string                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --description string            string value
      --discount-unit-amount string   string value
  -h, --help                          help for create-order-line-item
  -i, --item-id string                string value
  -l, --list-unit-price string        [required]
  -m, --metadata string               value
      --order-id string               [required]
      --quantity string               [required]
      --term-end-date string          date/time value
      --term-start-date string        date/time value
      --total-price string            [required]
  -u, --unit-price string             [required]
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
