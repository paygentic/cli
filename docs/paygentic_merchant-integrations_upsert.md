## paygentic merchant-integrations upsert

Upsert

### Synopsis

Create or re-activate a merchant's connection to a provider. Idempotent on `(merchantId, provider)` — connecting an already-connected provider re-activates the existing row, never creating a duplicate.

```
paygentic merchant-integrations upsert [flags]
```

### Examples

```
  paygentic merchant-integrations upsert --merchant-id <id> --provider salesforce
```

### Options

```
      --body string           Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --config-param string   value
  -e, --external-id string    Ampersand installation id.
  -h, --help                  help for upsert
      --merchant-id string    Unique identifier for an organization [required]
      --metadata string       value
  -p, --provider string       External provider a merchant can connect at the tenant level (options: salesforce) [required]
  -s, --status string         Connection lifecycle state. Live Ampersand health is separate and not stored here. (options: active, disconnected, error)
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

* [paygentic merchant-integrations](paygentic_merchant-integrations.md)	 - A `MerchantIntegration` records a merchant's connection to an external provider
