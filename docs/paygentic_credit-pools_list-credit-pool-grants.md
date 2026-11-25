## paygentic credit-pools list-credit-pool-grants

List grants

### Synopsis

Lists the grants on the pool, with the credits left on each. Active and scheduled grants come first, in the order they are spent: lowest priority first, then soonest expiry (no expiry last), then oldest. Expired and voided grants come after, newest first. `remainingBalance` is the grant's balance from the same replay the ledger runs, computed at read time from the usage so far. It is 0 unless the grant is active. Statuses and balances are computed at one instant, returned as `asOf`. It defaults to the pool's current time: the test clock time of the customer's newest active subscription if it has one, otherwise now. A later `at` is read as the pool's current time. Pass `at` to read at a different instant.

```
paygentic credit-pools list-credit-pool-grants [flags]
```

### Examples

```
  paygentic credit-pools list-credit-pool-grants --id <id>
```

### Options

```
  -a, --at string       The instant to compute statuses and balances at. Defaults to the pool's current time: the test clock time of the customer's newest active subscription if it has one, otherwise now. A later instant is read as the pool's current time.
  -h, --help            help for list-credit-pool-grants
  -i, --id string       [required]
  -l, --limit int       Maximum grants to return. (default 50)
      --offset int      Zero-based offset for pagination.
  -s, --status string   Return only grants with this status. (options: active, scheduled, expired, voided)
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
