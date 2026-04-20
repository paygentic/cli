## paygentic customers list

List by Merchant

### Synopsis

List by Merchant

```
paygentic customers list [flags]
```

### Examples

```
  paygentic customers list --organization-id <id>
```

### Options

```
      --email string             Filter customers by billing email (case-insensitive substring match). Minimum 3 characters required for efficient index usage. Accepts partial values — e.g. a domain ("acme.com") or local part ("billing").
      --external-id string       Filter customers by exact external ID match.
  -h, --help                     help for list
  -l, --limit int                Number of customers to return (default 10)
  -n, --name string              Filter customers by consumer name (case-insensitive substring match). Minimum 3 characters required for efficient index usage.
      --offset int               Number of customers to skip
      --organization-id string   ID of the merchant organization to filter customers by [required]
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

* [paygentic customers](paygentic_customers.md)	 - A `Customer` is an entity connected to a `Merchant` via a `Subscription`
