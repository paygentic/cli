## paygentic credit-pools get-credit-pool-ledger

Get ledger

### Synopsis

Returns a chronologically-ordered ledger of the pool's balance history within a required time window: `increment` (a grant funded the pool, including recurrence refills), `decrement` (usage drawdown), `void` (a grant was cancelled early), and `expiration` (a grant's unused balance lapsed at expiry). Each entry carries the pool's running balance immediately before and after it, and the response reports the window's boundary balances at the top level. Pass `granularity` to receive calendar-aligned buckets instead of itemized entries. There is no full-history view in a single call — page through successive windows to see a pool's complete history.

```
paygentic credit-pools get-credit-pool-ledger [flags]
```

### Examples

```
  paygentic credit-pools get-credit-pool-ledger --id <id> --from 2025-01-03T19:47:34.571Z --to 2025-06-15T09:32:08.085Z
```

### Options

```
  -e, --entry-type increment      Restrict the response to a single entry type: increment (grant funding, including recurrence refills), `decrement` (usage drawdown), `void` (early grant termination), or `expiration` (unused balance lapsing at a grant's expiry). When `granularity` is also set, this filter scopes which entries feed each bucket's net fields and `entryCount`, but never the reported balances. (options: increment, decrement, void, expiration)
  -f, --from string               Start of the requested window (inclusive). Required — this endpoint has no full-lifetime view. Must be before the pool's current time: the test clock time of the customer's newest active subscription if it has one, otherwise now. [required]
  -g, --granularity granularity   Roll the ledger up into calendar-aligned buckets (UTC) instead of itemized entries. Calendar periods with no activity are omitted from the response. To see the individual entries behind a bucket, request the itemized ledger (omit granularity) with the same `entryType` filter and `from`/`to` narrowed to that bucket's `period`. (options: hour, day, month)
  -h, --help                      help for get-credit-pool-ledger
  -i, --id string                 [required]
  -l, --limit granularity         Maximum number of entries (or buckets, when granularity is set) to return. (default 50)
      --offset int                Zero-based offset for pagination.
  -t, --to from                   End of the requested window. Must be strictly after from. The window is capped at a maximum supported span; a wider request is rejected. A `to` after the pool's current time is read as the current time, so the ledger never includes projected refills or expirations. [required]
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
