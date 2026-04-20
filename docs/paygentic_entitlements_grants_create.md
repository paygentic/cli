## paygentic entitlements grants create

Create Grant

### Synopsis

Create a grant directly for a metered entitlement, crediting the customer's balance immediately. The entitlement must belong to an active v1 subscription.

```
paygentic entitlements grants create [flags]
```

### Examples

```
  paygentic grants create --entitlement-id <id> --amount 100 --idempotency-key grant-initial-100
```

### Options

```
  -a, --amount float             The number of credits to grant. [required]
      --body string              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --effective-at string      When the grant becomes effective. Defaults to now.
      --entitlement-id string    The unique identifier of the entitlement to grant credits to. [required]
      --expires-at string        When the grant expires. If omitted, the grant does not expire.
  -h, --help                     help for create
  -i, --idempotency-key string   Idempotency key to prevent duplicate grants. Must be unique per entitlement. [required]
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
