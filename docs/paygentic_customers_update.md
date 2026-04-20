## paygentic customers update

Update

### Synopsis

Update

```
paygentic customers update [flags]
```

### Examples

```
  paygentic customers update --id <id>
```

### Options

```
      --body string                    Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -e, --external-id string             Merchant-defined identifier for this customer in their own system. Set to null to clear.
  -h, --help                           help for update
  -i, --id string                      The unique identifier of the customer. [required]
  -n, --notification-settings string   Notification preferences for this customer. Only provided fields are updated.
      --tax-id string                  Business tax registration identifier. Sample values: 'GB123456789' for UK VAT, 'DE123456789' for German VAT, 'FR12345678901' for French VAT. Enables inter-company tax handling and exemption from standard tax collection. Assign null to delete the identifier.
      --tax-rates string               JSON value (one of: number | object)
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
