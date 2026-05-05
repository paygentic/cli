## paygentic

Paygentic API: The Paygentic API provides billing infrastructure for usage-based and subscription monetization — customers, subscriptions, usage metering, invoicing, entitlements, and payments

### Synopsis

Paygentic API: The Paygentic API provides billing infrastructure for usage-based and subscription monetization — customers, subscriptions, usage metering, invoicing, entitlements, and payments.

See the [Quickstart](https://docs.paygentic.io/getting-started/quickstart) to go from zero to billing in a handful of steps.

```
paygentic [flags]
```

### Options

```
      --agent-mode             Enable structured errors and default TOON output for AI coding agents. Automatically enabled when a known agent environment is detected (CLAUDE_CODE, CURSOR_AGENT, etc.). Use --agent-mode=false to disable.
      --bearer-auth string     API key authentication
      --color string           Control colored output: auto (color when output is a TTY), always, or never. Respects NO_COLOR and FORCE_COLOR env vars. (default "auto")
  -d, --debug                  Log request and response diagnostics to stderr
      --dry-run                Preview the request that would be sent without executing it (output to stderr)
  -H, --header stringArray     Set a custom HTTP request header (format: "Key: Value"). Can be specified multiple times.
  -h, --help                   help for paygentic
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

* [paygentic auth](paygentic_auth.md)	 - Manage authentication credentials
* [paygentic billable-metrics](paygentic_billable-metrics.md)	 - Operations for billable-metrics
* [paygentic configure](paygentic_configure.md)	 - Configure authentication credentials and preferences
* [paygentic costs](paygentic_costs.md)	 - A Cost represents the operational or infrastructure expense of serving customers for a given product
* [paygentic customers](paygentic_customers.md)	 - A `Customer` is an entity connected to a `Merchant` via a `Subscription`
* [paygentic entitlements](paygentic_entitlements.md)	 - Operations for entitlements
* [paygentic events](paygentic_events.md)	 - Ingest raw metering events that are processed by the meters service
* [paygentic explore](paygentic_explore.md)	 - Interactively browse and run commands
* [paygentic features](paygentic_features.md)	 - A `Feature` represents a specific capability or functionality provided by a `Product`
* [paygentic fees](paygentic_fees.md)	 - A `Fee` defines a recurring or one-time charge tied to a `Product`
* [paygentic invoices-v2](paygentic_invoices-v2.md)	 - Invoice V2 operations supporting billing cycles organized by time periods
* [paygentic payment-sessions](paygentic_payment-sessions.md)	 - Handle payment session lifecycle and processing across various entity types including invoices and subscriptions
* [paygentic payments](paygentic_payments.md)	 - Create and manage one-off payments
* [paygentic plans](paygentic_plans.md)	 - A `Plan` links a collection of `Prices` to a `Product`
* [paygentic prices](paygentic_prices.md)	 - A `Price` determines the monetary value for a single unit of a `Billable Metric`
* [paygentic products](paygentic_products.md)	 - A `Product` is an offering sold by a `Merchant`
* [paygentic profitability](paygentic_profitability.md)	 - Per-customer profitability summaries
* [paygentic revenue](paygentic_revenue.md)	 - Revenue data from invoices and payments
* [paygentic sources](paygentic_sources.md)	 - A `Source` is an external data provider capable of automatically creating usage events
* [paygentic subscriptions](paygentic_subscriptions.md)	 - A `Subscription` is a customer's commitment to purchase a `Product` following the terms of a `Plan` and its linked `Prices`
* [paygentic test-clocks](paygentic_test-clocks.md)	 - Test clocks provide programmable time control to simulate subscription and billing scenarios during testing
* [paygentic users](paygentic_users.md)	 - A `User` is an entity granted access to an Organization's resources
* [paygentic version](paygentic_version.md)	 - Print the CLI version
* [paygentic whoami](paygentic_whoami.md)	 - Display current authentication configuration
