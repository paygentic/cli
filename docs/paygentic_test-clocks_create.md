## paygentic test-clocks create

Create

### Synopsis

Creates a new test clock with an optional initial time. If no time is provided, uses the current time.

```
paygentic test-clocks create [flags]
```

### Examples

```
  paygentic test-clocks create
```

### Options

```
      --body string           Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --current-time string   Initial time for the test clock (defaults to current time). Cannot be more than 1 hour in the past to prevent accidental backdating. The 1-hour buffer accounts for clock drift and network delays.
      --description string    Description of the test clock's purpose
  -h, --help                  help for create
  -m, --merchant-id string    The merchant organization that will own this test clock. If not provided, will be extracted from authenticated user's context.
  -n, --name string           Name of the test clock
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

* [paygentic test-clocks](paygentic_test-clocks.md)	 - Test clocks provide programmable time control to simulate subscription and billing scenarios during testing
