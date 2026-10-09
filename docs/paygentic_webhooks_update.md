## paygentic webhooks update

Update

### Synopsis

Turns webhook delivery on or off. Set `enabled` to `false` to pause delivery and to `true` to resume it. Endpoints and their event subscriptions are kept. Returns 404 if webhooks have never been enabled.

```
paygentic webhooks update [flags]
```

### Examples

```
  paygentic webhooks update --enabled true
```

### Options

```
      --body string          Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -e, --enabled              Whether webhooks are enabled [required]
  -h, --help                 help for update
  -m, --merchant-id string   The merchant organization ID. If omitted, defaults to the merchant associated with the authenticated API key.
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

* [paygentic webhooks](paygentic_webhooks.md)	 - Endpoints for setting up webhook integrations and administering webhook settings
