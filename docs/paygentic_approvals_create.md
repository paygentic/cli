## paygentic approvals create

Submit a resource for approval

### Synopsis

Submit a resource for approval

```
paygentic approvals create [flags]
```

### Examples

```
  paygentic approvals create --merchant-id <id> --resource-type invoice --resource-id <id> --data-snapshot-hash <value>
```

### Options

```
  -a, --actor-id string             Optional. The real user id to record as the requester. Used when the request is made via a platform-level key on behalf of a human user (e.g. from the platform Next.js frontend). When supplied and the authenticated principal is 'platform', this value overrides the derived principal as the requester. Ignored when the caller is a non-platform API key.
      --body string                 Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --data-snapshot-hash string   A precomputed hash of the resource state being approved. The resource-owning domain builds this snapshot; approvals stays decoupled from any specific resource shape. [required]
  -h, --help                        help for create
  -k, --kind string                 Defaults to data_review. (options: data_review, financial_review, push)
  -m, --merchant-id string          The merchant that owns the resource being approved. [required]
  -n, --note string                 string value
      --resource-id string          [required]
      --resource-type string        options: order, invoice [required]
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

* [paygentic approvals](paygentic_approvals.md)	 - Submit, decide, cancel, and read maker-checker approvals
