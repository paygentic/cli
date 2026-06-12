## paygentic external-references

An `ExternalReference` links a Paygentic entity (e

### Synopsis

An `ExternalReference` links a Paygentic entity (e.g. an `Item`) to a record in an external system such as Salesforce or NetSuite. Multiple external records may map to the same Paygentic entity, but each external id is the *primary* reference of at most one entity per merchant.

```
paygentic external-references [flags]
```

### Options

```
  -h, --help   help for external-references
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

* [paygentic](paygentic.md)	 - Paygentic API: The Paygentic API provides billing infrastructure for usage-based and subscription monetization — customers, subscriptions, usage metering, invoicing, entitlements, and payments
* [paygentic external-references create](paygentic_external-references_create.md)	 - Create
* [paygentic external-references delete](paygentic_external-references_delete.md)	 - Delete
* [paygentic external-references get](paygentic_external-references_get.md)	 - Get
* [paygentic external-references list](paygentic_external-references_list.md)	 - List
* [paygentic external-references update](paygentic_external-references_update.md)	 - Update
