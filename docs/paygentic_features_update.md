## paygentic features update

Update

### Synopsis

Update

```
paygentic features update [flags]
```

### Examples

```
  paygentic features update --id <id>
```

### Options

```
      --body string       Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help              help for update
  -i, --id string         The unique identifier of the feature [required]
  -k, --key string        Updated feature key slug. Sample values: 'increased-api-limit', 'new-storage-tier'
  -m, --metadata string   Updated metadata for the feature
  -n, --name string       Updated feature name.
  -t, --type string       Updated feature type (options: metered, static, boolean)
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

* [paygentic features](paygentic_features.md)	 - A `Feature` represents a specific capability or functionality provided by a `Product`
