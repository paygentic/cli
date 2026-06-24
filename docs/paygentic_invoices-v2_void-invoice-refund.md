## paygentic invoices-v2 void-invoice-refund

Void Invoice Refund

### Synopsis

Void a previously-issued refund (credit note). Reverses the credit note in the tax provider and excludes it from revenue. Accessible to the owning merchant or platform operators.

```
paygentic invoices-v2 void-invoice-refund [flags]
```

### Examples

```
  paygentic invoices-v2 void-invoice-refund --id <id> --refund-id <id>
```

### Options

```
      --body string        Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help               help for void-invoice-refund
  -i, --id string          The invoice ID [required]
      --reason string      Optional reason for voiding the refund (recorded on the credit note)
      --refund-id string   The refund (credit note) ID [required]
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
