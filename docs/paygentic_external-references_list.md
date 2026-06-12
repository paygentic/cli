## paygentic external-references list

List

### Synopsis

List

```
paygentic external-references list [flags]
```

### Examples

```
  paygentic external-references list
```

### Options

```
      --entity-id itm_xxx      Filter by the Paygentic entity id (e.g. itm_xxx). This is the inverse of the `GET /v0/items?provider=&externalId=` resolution endpoint — look up references from the Paygentic side. All active filters AND together.
      --entity-type item       Filter by the Paygentic entity type the reference points at (e.g. item). All active filters AND together. (options: item)
      --external-id provider   Filter by the external system's record id. Pair with provider to look up all Paygentic entities that carry a given external reference. All active filters AND together.
  -h, --help                   help for list
  -l, --limit int              integer value (default 50)
  -m, --merchant-id string     Restrict results to a specific merchant. All active filters AND together.
      --offset int             integer value
  -p, --provider salesforce    Filter by provider (e.g. salesforce, `netsuite`). All active filters AND together.
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

* [paygentic external-references](paygentic_external-references.md)	 - An `ExternalReference` links a Paygentic entity (e
