## paygentic subscriptions delete-subscription-adjustment

Delete Adjustment

### Synopsis

Stops an adjustment from applying to any period it has not already been billed on. An adjustment that has never reached an issued invoice is removed, and the response is 204. An adjustment that has already been billed on an issued invoice is RETRACTED instead: its effectiveTo moves to the end of the last period it was billed on, the adjustment still exists, and the response is 200 carrying it. Read a 200 as "shortened", not as "removed". No invoice changes either way: an issued invoice keeps its numbers, and a draft loses the adjustment only when its period is calculated again. Deleting the same adjustment again returns the same 200 and the same window.

```
paygentic subscriptions delete-subscription-adjustment [flags]
```

### Examples

```
  paygentic subscriptions delete-subscription-adjustment --id <id> --adjustment-id <id>
```

### Options

```
  -a, --adjustment-id string   The adjustment ID [required]
  -h, --help                   help for delete-subscription-adjustment
  -i, --id string              The subscription ID [required]
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

* [paygentic subscriptions](paygentic_subscriptions.md)	 - A `Subscription` is a customer's commitment to purchase a `Product` following the terms of a `Plan` and its linked `Prices`
