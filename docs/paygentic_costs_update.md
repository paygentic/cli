## paygentic costs update

Update

### Synopsis

Update

```
paygentic costs update [flags]
```

### Examples

```
  paygentic costs update --id <id>
```

### Options

```
  -a, --aggregation string      Updated aggregation method (metered costs only). (options: SUM, COUNT, AVG, MIN, MAX, UNIQUE_COUNT, LATEST)
      --body string             Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --currency string         Updated ISO 4217 currency code.
  -e, --event-type string       Updated CloudEvents type (metered costs only).
  -g, --group-by string         Updated group-by dimension map (metered costs only).
  -h, --help                    help for update
  -i, --id string               The unique identifier of the cost [required]
  -n, --name string             Updated name for the cost.
      --unit string             Updated unit label (metered costs only).
      --unit-cost float         Updated unit cost.
  -v, --value-property string   Updated JSONPath for value extraction (metered costs only).
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

* [paygentic costs](paygentic_costs.md)	 - A Cost represents the operational or infrastructure expense of serving customers for a given product
