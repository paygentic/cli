## paygentic entitlements grants void

Void Grant

### Synopsis

Void a grant, removing it from the customer's balance. This operation is idempotent — voiding an already-voided grant returns the voided grant without error.

```
paygentic entitlements grants void [flags]
```

### Examples

```
  paygentic grants void --entitlement-id <id> --grant-id <id>
```

### Options

```
  -e, --entitlement-id string   The unique identifier of the entitlement. [required]
  -g, --grant-id string         The unique identifier of the grant to void. [required]
  -h, --help                    help for void
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

* [paygentic entitlements grants](paygentic_entitlements_grants.md)	 - Operations for grants
