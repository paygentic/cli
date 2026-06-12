## paygentic items list

List

### Synopsis

List

```
paygentic items list [flags]
```

### Examples

```
  paygentic items list
```

### Options

```
  -e, --external-id (provider, externalId)   Resolve every live Item mapped to this (provider, externalId) — the canonical primary plus any non-primary aliases. The primary Item is returned first and is identifiable by its matching reference's `isPrimary: true`. Empty list on no match. Must be supplied together with `provider`.
  -h, --help                                 help for list
  -l, --limit provider                       Maximum items to return. In resolution mode (provider+`externalId` supplied) pagination is over the de-duplicated resolved Item set, primary Item first. (default 50)
  -m, --merchant-id string                   Filter items by merchant organization id
      --offset int                           Zero-based offset for pagination. In resolution mode this paginates the de-duplicated resolved Item set.
  -p, --provider salesforce                  Provider whose external code to resolve (e.g. salesforce, `netsuite`). Must be supplied together with `externalId`.
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

* [paygentic items](paygentic_items.md)	 - An `Item` is the canonical "thing you sell" that external-system mappings point at
