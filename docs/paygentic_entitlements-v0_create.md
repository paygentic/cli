## paygentic entitlements-v0 create

Create

### Synopsis

Create an entitlement for a customer. This temporarily reserves funds in the customer's wallet to guarantee payment for future usage.

```
paygentic entitlements-v0 create [flags]
```

### Examples

```
  paygentic entitlements-v0 create --customer-id <id> --entitlement-data '[]' --merchant-id <id>
```

### Options

```
      --body string               Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --customer-id string        Unique identifier for a customer [required]
  -e, --entitlement-data string   Array of consumption metrics with quantities to pre-authorize payment for. [required]
  -h, --help                      help for create
      --max-uses int              Maximum consumption events allowed before expiration (optional). Defaults to 1 for global entitlements, 100 for regional entitlements.
      --merchant-id string        Unique identifier for a merchant/organization [required]
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

* [paygentic entitlements-v0](paygentic_entitlements-v0.md)	 - Operations for entitlements-v0
