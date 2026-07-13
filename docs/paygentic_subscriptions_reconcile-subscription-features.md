## paygentic subscriptions reconcile-subscription-features

Reconcile Features

### Synopsis

Creates a reconciliation that converges a subscription's feature entitlements to its current plan. Provisions a missing entitlement (and, for metered features, its initial grant) for every plan feature the subscription does not already have; cancels the entitlement and voids the grants of any feature no longer on the plan; then synchronizes the corresponding prices' billing. An already-present feature is left unchanged. Restricted to active subscriptions billed on their plan's line-item schedule.

```
paygentic subscriptions reconcile-subscription-features [flags]
```

### Examples

```
  paygentic subscriptions reconcile-subscription-features --id <id>
```

### Options

```
      --body string   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --dry-run       Preview the outcome without creating any entitlement, grant, or line item.
  -h, --help          help for reconcile-subscription-features
  -i, --id string     The subscription ID [required]
```

### Options inherited from parent commands

```
      --agent-mode             Enable structured errors and default TOON output for AI coding agents. Automatically enabled when a known agent environment is detected (CLAUDE_CODE, CURSOR_AGENT, etc.). Use --agent-mode=false to disable.
      --bearer-auth string     API key authentication
      --color string           Control colored output: auto (color when output is a TTY), always, or never. Respects NO_COLOR and FORCE_COLOR env vars. (default "auto")
  -d, --debug                  Log request and response diagnostics to stderr
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
