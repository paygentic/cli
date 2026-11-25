## paygentic pricing-units create

Create

### Synopsis

Create

```
paygentic pricing-units create [flags]
```

### Examples

```
  paygentic pricing-units create --merchant-id <id> --identifier <value> --display-name Jay.Kerluke70 --short-name <value> --conversion-rate <value>
```

### Options

```
      --body string               Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --conversion-rate string    Default rate converting one credit to the invoicing currency ($/credit), as a decimal string. [required]
      --currency conversionRate   ISO 4217 currency code that conversionRate maps to (e.g. `USD`). [required]
      --display-name string       Human-readable name shown in the UI. [required]
  -h, --help                      help for create
  -i, --identifier credits        Programmatic identifier, a slug unique per merchant (e.g. credits). [required]
  -m, --merchant-id string        Unique identifier for an organization [required]
  -s, --short-name credits        Short label used on invoice lines (e.g. credits). [required]
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

* [paygentic pricing-units](paygentic_pricing-units.md)	 - A `PricingUnit` is a merchant-scoped catalog object that names a credit denomination and the rate (`conversionRate`) at which it converts to an invoicing `currency`
