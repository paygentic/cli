## paygentic subscription-proposals list

List

### Synopsis

Lists the subscription proposals you can read, newest first. Filter by `status` to list, for example, the proposals waiting for a decision: `pagination.total` then counts them. Pass `merchantId` to list one merchant's proposals. A `merchantId` you cannot read answers 403, not an empty page.

```
paygentic subscription-proposals list [flags]
```

### Examples

```
  paygentic subscription-proposals list
```

### Options

```
  -h, --help                                     help for list
  -l, --limit int                                Number of proposals to return. (default 50)
  -m, --merchant-id string                       Return only this merchant's proposals.
      --offset int                               Number of proposals to skip.
  -s, --status ?status=pending&status=approved   Return proposals in any of these statuses. Repeat the parameter to pass several, e.g. ?status=pending&status=approved. Omit it to return every status.
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

* [paygentic subscription-proposals](paygentic_subscription-proposals.md)	 - A `SubscriptionProposal` holds the values of a subscription until a person on your team approves or rejects it
