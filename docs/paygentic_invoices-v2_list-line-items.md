## paygentic invoices-v2 list-line-items

List Line Items

### Synopsis

List pending and invoiced line items for a subscription from the billing database. Returns exact fee amounts and estimated metered charges.

```
paygentic invoices-v2 list-line-items [flags]
```

### Examples

```
  paygentic invoices-v2 list-line-items
```

### Options

```
  -e, --expand items             Comma-separated list of fields to expand. Supports: items — resolves each returned line's item and that item's external accounting codes into an items collection, so a line can be translated to a GL/SKU code without a second call.
  -h, --help                     help for list-line-items
  -i, --invoice-id string        Filter by invoice ID. When provided without subscriptionId, returns all line items for that invoice. At least one of subscriptionId or invoiceId must be provided.
  -l, --limit int                Maximum number of line items to return (default 100)
      --offset int               Number of line items to skip for pagination
  -p, --provider string          Narrows which external references are returned per item when expand=items. Matched exactly against the provider stored on the reference (e.g. accountsiq); there is no allowlist of known providers, but the value must satisfy the same format every stored provider does, so a malformed one is rejected rather than answered with an empty result that reads as "nothing is mapped". It never removes lines or items: an item with no reference for this provider comes back with an empty list, so unmapped SKUs stay visible. Ignored when the items expansion is not requested.
      --status string            Filter by line item status. 'pending' returns items not yet on an invoice, 'invoiced' returns items already assigned to an invoice. Omit to return both. Cannot be combined with invoiceId — when filtering by invoice ID all statuses are returned. (options: pending, invoiced)
      --subscription-id string   Filter by subscription ID. At least one of subscriptionId or invoiceId must be provided.
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
