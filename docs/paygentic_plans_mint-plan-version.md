## paygentic plans mint-plan-version

Mint a plan version

### Synopsis

Mint a new plan version from a price diff and make it the version the plan bills from, in one step. The diff references existing prices by id: create prices beforehand with POST /prices, then add, remove, or replace them here. To return to an earlier price set, make that version the default with a PATCH on the version.

```
paygentic plans mint-plan-version [flags]
```

### Examples

```
  paygentic plans mint-plan-version --id <id>
```

### Options

```
  -a, --add-prices stringArray      Prices to add to the version. Each must not already be on the plan's current version.
      --body string                 Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help                        help for mint-plan-version
  -i, --id string                   [required]
      --remove-prices stringArray   Prices to remove. Each must be on the plan's current version.
      --replace-prices string       Prices to swap in place, preserving the slot's lineage so the price keeps its identity where the plan is configured for stable price ids. replacesPriceId must be on the plan's current version; withPriceId is the new price.
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
