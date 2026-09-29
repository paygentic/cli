## paygentic plans mint-plan-version

Mint a plan version

### Synopsis

Mint a new plan version from the price set it is to hold, and make it the version the plan bills from, in one step. The request names the complete set, not a change to it: create prices beforehand with POST /prices, then list every price the new version holds. The change against the current version follows from the keys — a key on both sides with a different price ID replaces that line, a key only in the request adds a line, and a key the current version holds and the request omits removes that line. To return to an earlier price set, make that version the default with a PATCH on the version.

```
paygentic plans mint-plan-version [flags]
```

### Examples

```
  paygentic plans mint-plan-version --id <id> --prices '[{"priceId":"<id>"}]'
```

### Options

```
  -b, --based-on-version-id string   The ID of the plan version you read the current price set from. Supply it to be told when the plan has moved on: the request is rejected with 409 if the plan's current version is no longer this one, so a set built from a stale read cannot drop a line another caller has just added. Omit it to write the set unconditionally.
      --body string                  Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help                         help for mint-plan-version
  -i, --id string                    [required]
  -p, --prices string                The full price set the new version holds. To move off the previous addPrices, removePrices and replacePrices fields: a replacePrices entry becomes the same key with the new price ID, a removePrices entry becomes an omitted key, and an addPrices entry becomes a new entry. [required]
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

* [paygentic plans](paygentic_plans.md)	 - A `Plan` links a collection of `Prices` to a `Product`
