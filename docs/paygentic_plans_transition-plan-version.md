## paygentic plans transition-plan-version

Set the default version

### Synopsis

Point the plan's default at this version, so its floating subscriptions bill from it. Any version may become default, in either direction — this is how you roll a plan back to (or forward to) an earlier price set. Idempotent when the version is already the default.

```
paygentic plans transition-plan-version [flags]
```

### Examples

```
  paygentic plans transition-plan-version --id <id> --version-number 414716
```

### Options

```
      --body string          Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --default              Set to true to point the plan's default at this version. Idempotent on the already-default version.
  -h, --help                 help for transition-plan-version
  -i, --id string            [required]
  -v, --version-number int   The version number within the plan (1-based). [required]
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

* [paygentic plans](paygentic_plans.md)	 - A `Plan` links a collection of `Prices` to a `Product`
