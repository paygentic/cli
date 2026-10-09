## paygentic invoices-v2 retry-invoice-payment

Retry Payment

### Synopsis

Charge the customer's saved payment method again for an unpaid invoice.

The invoice must be in status `ISSUED` or `PAYMENT_FAILED`, auto-charge must be on for its subscription, and the invoice must have a payment session. If not, the response is 400.

The response status tells you the result. Only 200 means that the charge succeeded. Every other response from this operation that has a `retry_payment_result` body has `success: false`, and `error.code` gives the reason:

| Status | `error.code` | Meaning |
| --- | --- | --- |
| 200 | — | The charge succeeded, the provider had already collected it, or no amount is unpaid. |
| 202 | `processing` | The provider accepted the charge. It settles later (for example, a bank debit). |
| 402 | a decline code, for example `card_declined`, `insufficient_funds`, `do_not_honor`, `authentication_required` | The provider declined the payment method. |
| 409 | `concurrent_attempt` | Another payment attempt for this invoice is in progress. |
| 409 | `PAYMENT_SESSION_EXPIRED` | The payment link expired (after 30 days). Create a new link with `POST /v2/invoices/{id}/payment` and `method: hosted_link`, then retry. If the customer also has no usable saved payment method, the response is 422 instead. |
| 409 | another value, or no `code` | The payment session cannot be charged in its current state (for example `session_unusable`, `non_confirmable`, `PAYMENT_PROCESSING`, `PAYMENT_ALREADY_COMPLETED`). Read `error.message` for the cause. |
| 422 | `no_payment_method` | The customer has no usable saved payment method. Send a payment link instead. |
| 502 | `provider_unavailable` or none | The payment provider did not answer, or the provider failed the charge for a reason that is not known. Retry later. |

A 500 response has the standard error body, not `retry_payment_result`. It is an internal error, and a retry does not fix it.

An invoice that does not exist returns 403, the same as an invoice of another merchant.

This operation is rate limited to one call each minute for each invoice.

```
paygentic invoices-v2 retry-invoice-payment [flags]
```

### Examples

```
  paygentic invoices-v2 retry-invoice-payment --id <id>
```

### Options

```
      --body string     Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -h, --help            help for retry-invoice-payment
  -i, --id string       The invoice ID [required]
  -r, --reason string   Optional reason for the manual retry (for audit logging)
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

* [paygentic invoices-v2](paygentic_invoices-v2.md)	 - Invoice V2 operations supporting billing cycles organized by time periods
