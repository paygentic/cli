## paygentic approvals update

Update an approval (approve, reject, or cancel)

### Synopsis

Update an approval (approve, reject, or cancel)

```
paygentic approvals update [flags]
```

### Examples

```
  paygentic approvals update --id <id> --decision rejected
```

### Options

```
  -a, --actor-id string   Optional. The real user id performing the action. Used when the request is made via a platform-level key on behalf of a human user. Ignored when the caller is a non-platform API key.
      --body string       Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --decision string   approved/rejected: reviewer decision (maker-checker enforced). cancelled: recall a pending approval or reopen an approved one. (options: approved, rejected, cancelled) [required]
  -h, --help              help for update
  -i, --id string         [required]
  -n, --note string       string value
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
