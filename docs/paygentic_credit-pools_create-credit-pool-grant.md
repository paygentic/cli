## paygentic credit-pools create-credit-pool-grant

Grant credits

### Synopsis

Mint a credit grant on the pool. Set `recurrencePeriod` (+ optional `recurrenceAnchor`, defaults to `effectiveAt`) for a recurring grant that re-adds `amount` each interval; set `expiresAt` for a per-grant expiry. Standalone of any plan or subscription.

```
paygentic credit-pools create-credit-pool-grant [flags]
```

### Examples

```
  paygentic credit-pools create-credit-pool-grant --id <id> --amount 5717.01
```

### Options

```
  -a, --amount float                    Credits to allocate (in the pool's pricing unit). [required]
      --body string                     Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --effective-at string             When the block becomes active. Defaults to now (or the customer's active-subscription test-clock time).
      --expires-at string               When the block expires (per-block expiry).
  -h, --help                            help for create-credit-pool-grant
      --id string                       [required]
      --idempotency-key string          Idempotency key; a repeat with the same key returns the existing grant.
  -p, --priority int                    Drawdown priority (lower = consumed first). Defaults to 0.
      --recurrence-anchor effectiveAt   Recurrence phase anchor. Defaults to effectiveAt. Only valid with `recurrencePeriod`.
      --recurrence-period P1M           ISO-8601 duration (e.g. P1M). When set, `amount` is re-added each interval within the block's envelope.
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

* [paygentic credit-pools](paygentic_credit-pools.md)	 - A `CreditPool` is the `(customer, pricingUnit)` identity that credit-denominated prices draw down
