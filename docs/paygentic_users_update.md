## paygentic users update

Update

### Synopsis

Update

```
paygentic users update [flags]
```

### Examples

```
  paygentic users update --id <id>
```

### Options

```
  -a, --address string         JSON object
      --body string            Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --date-of-birth string   The date of birth of the user.
  -f, --first-name string      The first name of the user.
  -h, --help                   help for update
  -i, --id string              [required]
  -l, --last-name string       The last name of the user.
  -p, --phone string           The phone number of the user.
  -t, --type string            Type of entity the user represents. (options: COMPANY, INDIVIDUAL)
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

* [paygentic users](paygentic_users.md)	 - A `User` is an entity granted access to an Organization's resources
