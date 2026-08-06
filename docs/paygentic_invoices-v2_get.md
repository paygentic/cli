## paygentic invoices-v2 get

Get

### Synopsis

Retrieve a single invoice with real-time aggregates (for ACTIVE/CLOSING/CLOSED) or cached aggregates (for finalized invoices). Optionally include line items with expand=lineItems.

```
paygentic invoices-v2 get [flags]
```

### Examples

```
  paygentic invoices-v2 get --id <id>
```

### Options

```
  -e, --expand items                   Comma-separated list of fields to expand. Supports: lineItems, items. items resolves each returned line's item and its external accounting codes into an `items` collection inside the lineItems block; because those ids come from the lines, requesting `items` also expands `lineItems` on its default paging.
  -h, --help                           help for get
  -i, --id string                      The invoice ID [required]
      --line-items-limit int           Page size for line items when expand=lineItems (default 100)
      --line-items-page-token string   Opaque pagination token for line items when expand=lineItems, taken from a previous response's nextPageToken. Do not construct or parse this value.
  -p, --provider string                Narrows which external references are returned per item when expand=items. Matched exactly against the provider stored on the reference (e.g. accountsiq); there is no allowlist of known providers, but the value must satisfy the same format every stored provider does, so a malformed one is rejected rather than answered with an empty result that reads as "nothing is mapped". It never removes lines or items: an item with no reference for this provider comes back with an empty list, so unmapped SKUs stay visible. Ignored when the items expansion is not requested.
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

* [paygentic invoices-v2](paygentic_invoices-v2.md)	 - Invoice V2 operations supporting billing cycles organized by time periods
