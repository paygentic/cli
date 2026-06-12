## paygentic external-references create

Create

### Synopsis

Create

```
paygentic external-references create [flags]
```

### Examples

```
  paygentic external-references create --merchant-id <id> --entity-type item --entity-id <id> --provider <value> --external-id <id>
```

### Options

```
      --body string                                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --entity-id itm_xxx                             Paygentic id of the entity, e.g. itm_xxx [required]
      --entity-type string                            The type of Paygentic entity this external reference points at (options: item) [required]
      --external-id string                            Identifier of the record in the external system [required]
      --external-label string                         Human-friendly name shown in UIs (e.g. a NetSuite financial-treatment name)
  -h, --help                                          help for create
      --is-default (entityType, entityId, provider)   Whether this is the default target for the entity + provider. At most one default per (entityType, entityId, provider).
      --is-primary (provider, externalId)             Whether this is the canonical reference for (provider, externalId). The primary is unique per merchant; non-primary references are aliases. (default true)
      --merchant-id string                            [required]
      --metadata { "sfObject": "Product2" }           Provider-specific fields (e.g. { "sfObject": "Product2" })
  -p, --provider salesforce                           Lowercase snake_case provider identifier (e.g. salesforce, `netsuite`) [required]
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
