## paygentic customers create-customer-payment-method

Set up a payment method

### Synopsis

Create a payment session that captures a new off-session payment method for this customer without charging. The response contains a hosted-page URL — redirect the customer to it, or load it inside an iframe (when iframed, the page reports outcomes via `postMessage` to the parent window).

```
paygentic customers create-customer-payment-method [flags]
```

### Examples

```
  paygentic customers create-customer-payment-method --id <id>
```

### Options

```
      --body string                        Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -f, --failure-redirect-url postMessage   URL the customer is redirected to on failure. When the page is iframed, failure is reported via postMessage instead.
  -h, --help                               help for create-customer-payment-method
  -i, --id string                          The unique identifier of the customer. [required]
  -m, --metadata string                    Arbitrary key/value pairs to attach to the session.
  -s, --success-redirect-url postMessage   URL the customer is redirected to on success. When the page is iframed, success is reported via postMessage instead.
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

* [paygentic customers](paygentic_customers.md)	 - A `Customer` is an entity connected to a `Merchant` via a `Subscription`
