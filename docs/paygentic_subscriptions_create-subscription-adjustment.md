## paygentic subscriptions create-subscription-adjustment

Create Adjustment

### Synopsis

Attaches a percentage discount to the subscription for a dated window. Every invoice calculated while the window is open carries one discount line for each discounted charge, and tax is assessed on the reduced amount. An invoice that already exists is not changed, including one still in draft — the discount reaches the periods that close after it is created. There is no update operation, and a window cannot be changed after it is created. To change a rate before any invoice has issued under the discount, delete the adjustment and create a replacement. Once an invoice has issued the adjustment is permanent, so set effectiveTo at creation time whenever the deal has a known end date.

```
paygentic subscriptions create-subscription-adjustment [flags]
```

### Examples

```
  paygentic subscriptions create-subscription-adjustment --id <id> --type percentageDiscount --percentage-discount 0.35 --effective-from 2026-01-01T00:00:00Z
```

### Options

```
      --body string                  Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --description string           The deal's own name, shown on each discount line of the invoice.
      --effective-from string        The first instant the discount applies. Inclusive. [required]
      --effective-to string          The instant the discount stops applying. Exclusive, so a window ending on the same date another begins neither overlaps nor leaves a gap. Null means the discount never stops, and it cannot be ended later — set an instant whenever the deal has a known end date. Must be after effectiveFrom.
  -h, --help                         help for create-subscription-adjustment
      --id string                    The subscription ID [required]
      --idempotency-key string       A key of your choosing that makes a retry safe. Sending the same key against the same subscription returns the adjustment already created and creates no second one. Without a key a retried request creates a second adjustment, and two percentage discounts compound — two of 0.35 bill 57.75 percent off, not 35 percent.
  -p, --percentage-discount string   The discount rate as a decimal fraction between 0 and 1, sent as a string. "0.35" means 35 percent. "1" means 100 percent, not 1 percent. At most 6 decimal places. A value of 0 or above 1 is rejected. [required]
  -t, --type percentageDiscount      The kind of adjustment. percentageDiscount reduces every discountable charge by a rate. (options: percentageDiscount) [required]
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
