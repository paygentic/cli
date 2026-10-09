## paygentic subscriptions migrate-subscription-version

Migrate To A Plan Version

### Synopsis

Moves the subscription to a named version of its plan. By default the move follows the plan's versionTransition. With timing next_period, the move takes effect at the end of the current billing period: the current period bills as before, and each period that starts at or after that boundary bills from the target version. With timing immediate, entitlements change at once, in-arrears prices bill the whole current period at the target version, and in-advance prices change at the end of the current period, with no proration. The target can be an older or a newer published version. A migration always sets versionPolicy to pinned, so a later change of the plan's default version does not move the subscription. To follow the plan default again, call PATCH /v0/subscriptions/{id} with versionPolicy: 'floating'. A second migration before the boundary replaces the first. Migrating to the version the subscription is already on changes nothing except that it pins a floating subscription, so it is safe to repeat. A version number that does not exist on the plan and an archived version both return 404. The request is refused with 409 and a code when: the subscription is not live; the subscription ends at or before the boundary; a kept override has a rate that would mean something else on the new price; a feature's reset period, metric or pricing unit changes; or the new version sells a price that a continuing interval already covers.

```
paygentic subscriptions migrate-subscription-version [flags]
```

### Examples

```
  paygentic subscriptions migrate-subscription-version --id <id> --target-version-number 2
```

### Options

```
      --body string                 Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help                        help for migrate-subscription-version
  -i, --id string                   The subscription ID [required]
      --target-version-number int   The number of a published version of the subscription's plan. [required]
      --timing next_period          When the migration takes effect. next_period moves everything at the end of the current billing period. `immediate` changes entitlements at once, bills in-arrears prices for the whole current period at the target version, and changes in-advance prices at the end of the current period. Neither prorates. If absent, the plan's versionTransition applies. (options: next_period, immediate)
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
