## paygentic invoices-v2 download-invoice-pdf

Download Invoice PDF

### Synopsis

Downloads the Paygentic-rendered invoice document. The caller must be authenticated and entitled to the invoice; the stored document is streamed back, so no storage URL is ever handed out. Returns 404 when the invoice's document is the tax provider's rather than ours — in that case the invoice resource reports pdfSource `tax_provider` and its pdfUrl points at the provider's link instead.

This operation returns binary data. Use --output-file <path> to save to a file, or pipe the output to another command.

```
paygentic invoices-v2 download-invoice-pdf [flags]
```

### Examples

```
  paygentic invoices-v2 download-invoice-pdf --id <id>
```

### Options

```
  -h, --help                 help for download-invoice-pdf
  -i, --id string            The invoice ID [required]
      --output-b64           Encode binary response as base64 and print to stdout
      --output-file string   Save the response body to a file path (recommended for binary/file responses)
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
