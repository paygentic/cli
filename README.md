# paygentic

Command-line interface for *Paygentic*.

[![Built by Speakeasy](https://img.shields.io/badge/Built_by-SPEAKEASY-374151?style=for-the-badge&labelColor=f3f4f6)](https://www.speakeasy.com/?utm_source=github-com/paygentic/cli&utm_campaign=cli)
[![License: MIT](https://img.shields.io/badge/LICENSE_//_MIT-3b5bdb?style=for-the-badge&labelColor=eff6ff)](https://opensource.org/licenses/MIT)


<!-- Start Summary [summary] -->
## Summary

Paygentic API: The Paygentic API provides billing infrastructure for usage-based and subscription monetization — customers, subscriptions, usage metering, invoicing, entitlements, and payments.

See the [Quickstart](https://docs.paygentic.io/getting-started/quickstart) to go from zero to billing in a handful of steps.
<!-- End Summary [summary] -->

<!-- Start Table of Contents [toc] -->
## Table of Contents
<!-- $toc-max-depth=2 -->
* [paygentic](#paygentic)
  * [CLI Installation](#cli-installation)
  * [Shell Completion](#shell-completion)
  * [CLI Example Usage](#cli-example-usage)
  * [Authentication](#authentication)
  * [Available Commands](#available-commands)
  * [Request Body Input](#request-body-input)
  * [Server Selection](#server-selection)
  * [Output Formats](#output-formats)
  * [Error Handling](#error-handling)
  * [Diagnostics](#diagnostics)
* [Development](#development)
  * [Maturity](#maturity)
  * [Contributions](#contributions)

<!-- End Table of Contents [toc] -->

<!-- Start CLI Installation [installation] -->
## CLI Installation

### Quick Install (Linux/macOS)

```bash
curl -fsSL https://raw.githubusercontent.com/paygentic/cli/main/scripts/install.sh | bash
```

### Quick Install (Windows PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/paygentic/cli/main/scripts/install.ps1 | iex
```

### Go Install

Alternatively, install directly via Go:

```bash
go install github.com/paygentic/cli/cmd/paygentic@latest
```

### Manual Download

Download pre-built binaries for your platform from the [releases page](https://github.com/paygentic/cli/releases).
<!-- End CLI Installation [installation] -->

<!-- Start Shell Completion [completion] -->
## Shell Completion

Shell completions are available for Bash, Zsh, Fish, and PowerShell.

### Bash

```bash
# Add to ~/.bashrc:
source <(paygentic completion bash)

# Or install permanently:
paygentic completion bash > /etc/bash_completion.d/paygentic
```

### Zsh

```zsh
# Add to ~/.zshrc:
source <(paygentic completion zsh)

# Or install permanently:
paygentic completion zsh > "${fpath[1]}/_paygentic"
```

### Fish

```fish
paygentic completion fish | source

# Or install permanently:
paygentic completion fish > ~/.config/fish/completions/paygentic.fish
```

### PowerShell

```powershell
paygentic completion powershell | Out-String | Invoke-Expression
```
<!-- End Shell Completion [completion] -->

<!-- Start CLI Example Usage [usage] -->
## CLI Example Usage

### Create a customer

Create a customer for each organization you bill. This is the first step in the billing setup — see the [Quickstart](https://docs.paygentic.io/getting-started/quickstart) for the full flow.

```bash
paygentic customers create --bearer-auth 'Bearer test_token' --consumer '{"name":"Jane Smith","email":"jane@example.com","address":{"city":"San Francisco","state":"CA","country":"US"\x7d\x7d' --merchant-id org_YS8jkP59V71TdUvj

```

### Create a subscription

Subscribe a customer to a plan. If the plan includes in-advance charges, Paygentic generates an initial invoice and the subscription activates once paid.

```bash
paygentic subscriptions create --bearer-auth 'Bearer test_token' --customer-id cus_abc123 --name 'Monthly API Service' --plan-id plan_abc123 --started-at '2024-01-15T00:00:00Z'

```

### Report usage

Send meter events to record consumption once a subscription is active. The endpoint is fire-and-forget — it always returns `202 Accepted`.

```bash
paygentic events ingest --bearer-auth 'Bearer test_token' --type ai.inference --source 'https://api.myapp.com' --subject cus_abc123 --data '{"tokens":1500,"model":"gpt-4o"}'

```
<!-- End CLI Example Usage [usage] -->

<!-- Start Authentication [security] -->
## Authentication

Authentication credentials can be configured in four ways (in order of priority):

### 1. Command-line flags

Pass credentials directly as flags to any command:

```bash
paygentic --bearer-auth <value> <command> [arguments]
```

### 2. Environment variables

Set credentials via environment variables:

| Variable | Description |
|----------|-------------|
| `PAYGENTIC_BEARER_AUTH` | API key authentication |

### 3. OS Keychain (recommended for workstations)

Credentials are stored securely in your operating system's keychain when you run:

```bash
paygentic configure
```

Secret credentials (tokens, API keys, passwords) are automatically stored in:
- **macOS**: Keychain
- **Linux**: GNOME Keyring / KWallet (via D-Bus Secret Service)
- **Windows**: Windows Credential Locker

If no keychain is available (e.g., in CI environments), credentials fall back to the config file.

### 4. Configuration file

Run the interactive `configure` command to store non-secret settings:

```bash
paygentic configure
```

Configuration is stored in `~/.config/paygentic/config.yaml`.
<!-- End Authentication [security] -->

<!-- Start Available Commands [operations] -->
## Available Commands

<details open>
<summary>Available commands</summary>

### [billable-metrics](docs/paygentic_billable-metrics.md)

* [`create`](docs/paygentic_billable-metrics_create.md) - Create
* [`list`](docs/paygentic_billable-metrics_list.md) - List
* [`get`](docs/paygentic_billable-metrics_get.md) - Get
* [`update`](docs/paygentic_billable-metrics_update.md) - Update
* [`meter`](docs/paygentic_billable-metrics_meter.md) - Query Meter Usage
* [`list-events`](docs/paygentic_billable-metrics_list-events.md) - List Meter Events

### [customers](docs/paygentic_customers.md)

* [`list`](docs/paygentic_customers_list.md) - List by Merchant
* [`create`](docs/paygentic_customers_create.md) - Create
* [`get`](docs/paygentic_customers_get.md) - Get
* [`delete`](docs/paygentic_customers_delete.md) - Delete
* [`update`](docs/paygentic_customers_update.md) - Update
* [`list-customer-payment-methods`](docs/paygentic_customers_list-customer-payment-methods.md) - List payment methods
* [`create-customer-payment-method`](docs/paygentic_customers_create-customer-payment-method.md) - Set up a payment method

### [entitlements](docs/paygentic_entitlements.md)

* [`list`](docs/paygentic_entitlements_list.md) - List Entitlements
* [`issue`](docs/paygentic_entitlements_issue.md) - Issue Entitlement
* [`get`](docs/paygentic_entitlements_get.md) - Get Entitlement

#### [grants](docs/paygentic_entitlements_grants.md)

* [`list`](docs/paygentic_entitlements_grants_list.md) - List Grants
* [`create`](docs/paygentic_entitlements_grants_create.md) - Create Grant
* [`purchase`](docs/paygentic_entitlements_grants_purchase.md) - Purchase Grant
* [`get`](docs/paygentic_entitlements_grants_get.md) - Get Grant
* [`void`](docs/paygentic_entitlements_grants_void.md) - Void Grant

### [features](docs/paygentic_features.md)

* [`list`](docs/paygentic_features_list.md) - List
* [`create`](docs/paygentic_features_create.md) - Create
* [`get`](docs/paygentic_features_get.md) - Get
* [`update`](docs/paygentic_features_update.md) - Update
* [`delete`](docs/paygentic_features_delete.md) - Delete

### [fees](docs/paygentic_fees.md)

* [`create`](docs/paygentic_fees_create.md) - Create
* [`list`](docs/paygentic_fees_list.md) - List
* [`get`](docs/paygentic_fees_get.md) - Get
* [`update`](docs/paygentic_fees_update.md) - Update
* [`delete`](docs/paygentic_fees_delete.md) - Delete
* [`get-price`](docs/paygentic_fees_get-price.md) - Get Fee Price

### [plans](docs/paygentic_plans.md)

* [`create`](docs/paygentic_plans_create.md) - Create
* [`list`](docs/paygentic_plans_list.md) - List
* [`list-available`](docs/paygentic_plans_list-available.md) - List Available Plans
* [`get`](docs/paygentic_plans_get.md) - Get
* [`update`](docs/paygentic_plans_update.md) - Update

### [prices](docs/paygentic_prices.md)

* [`create`](docs/paygentic_prices_create.md) - Create
* [`list`](docs/paygentic_prices_list.md) - List
* [`get`](docs/paygentic_prices_get.md) - Get
* [`update`](docs/paygentic_prices_update.md) - Update
* [`delete`](docs/paygentic_prices_delete.md) - Delete

### [products](docs/paygentic_products.md)

* [`create`](docs/paygentic_products_create.md) - Create
* [`list`](docs/paygentic_products_list.md) - List
* [`get`](docs/paygentic_products_get.md) - Get
* [`update`](docs/paygentic_products_update.md) - Update

### [sources](docs/paygentic_sources.md)

* [`create`](docs/paygentic_sources_create.md) - Create
* [`list`](docs/paygentic_sources_list.md) - List
* [`get`](docs/paygentic_sources_get.md) - Get
* [`update`](docs/paygentic_sources_update.md) - Update

#### [sources-events](docs/paygentic_sources_sources-events.md)

* [`list`](docs/paygentic_sources_sources-events_list.md) - List Events
* [`approve`](docs/paygentic_sources_sources-events_approve.md) - Approve
* [`reject`](docs/paygentic_sources_sources-events_reject.md) - Reject
* [`bulk-approve`](docs/paygentic_sources_sources-events_bulk-approve.md) - Bulk Approve
* [`bulk-reject`](docs/paygentic_sources_sources-events_bulk-reject.md) - Bulk Reject

#### [rules](docs/paygentic_sources_rules.md)

* [`list`](docs/paygentic_sources_rules_list.md) - List Rules
* [`create`](docs/paygentic_sources_rules_create.md) - Create Rule
* [`get`](docs/paygentic_sources_rules_get.md) - Get Rule
* [`update`](docs/paygentic_sources_rules_update.md) - Update Rule
* [`delete`](docs/paygentic_sources_rules_delete.md) - Delete Rule

### [subscriptions](docs/paygentic_subscriptions.md)

* [`list`](docs/paygentic_subscriptions_list.md) - List
* [`create`](docs/paygentic_subscriptions_create.md) - Create
* [`get`](docs/paygentic_subscriptions_get.md) - Get
* [`generate-portal-link`](docs/paygentic_subscriptions_generate-portal-link.md) - Generate Portal Link
* [`terminate`](docs/paygentic_subscriptions_terminate.md) - Terminate

### [users](docs/paygentic_users.md)

* [`get`](docs/paygentic_users_get.md) - Get
* [`update`](docs/paygentic_users_update.md) - Update

### [invoices-v2](docs/paygentic_invoices-v2.md)

* [`list`](docs/paygentic_invoices-v2_list.md) - List
* [`list-line-items`](docs/paygentic_invoices-v2_list-line-items.md) - List Line Items
* [`create-line-item`](docs/paygentic_invoices-v2_create-line-item.md) - Create Manual Line Item
* [`get`](docs/paygentic_invoices-v2_get.md) - Get
* [`get-line-items`](docs/paygentic_invoices-v2_get-line-items.md) - Get Line Items

### [payments](docs/paygentic_payments.md)

* [`list`](docs/paygentic_payments_list.md) - List Payments
* [`create`](docs/paygentic_payments_create.md) - Create Payment
* [`get`](docs/paygentic_payments_get.md) - Get Payment

### [payment-sessions](docs/paygentic_payment-sessions.md)

* [`list`](docs/paygentic_payment-sessions_list.md) - List

### [events](docs/paygentic_events.md)

* [`ingest`](docs/paygentic_events_ingest.md) - Ingest Event

### [costs](docs/paygentic_costs.md)

* [`create`](docs/paygentic_costs_create.md) - Create
* [`list`](docs/paygentic_costs_list.md) - List
* [`get`](docs/paygentic_costs_get.md) - Get
* [`update`](docs/paygentic_costs_update.md) - Update
* [`delete`](docs/paygentic_costs_delete.md) - Delete
* [`get-cost-summary`](docs/paygentic_costs_get-cost-summary.md) - Query Summary
* [`get-cost-report`](docs/paygentic_costs_get-cost-report.md) - Report

### [revenue](docs/paygentic_revenue.md)

* [`get`](docs/paygentic_revenue_get.md) - Get revenue summary

### [profitability](docs/paygentic_profitability.md)

* [`get`](docs/paygentic_profitability_get.md) - Get profitability summary

### [test-clocks](docs/paygentic_test-clocks.md)

* [`list`](docs/paygentic_test-clocks_list.md) - List
* [`create`](docs/paygentic_test-clocks_create.md) - Create
* [`get`](docs/paygentic_test-clocks_get.md) - Get
* [`advance`](docs/paygentic_test-clocks_advance.md) - Advance
* [`delete`](docs/paygentic_test-clocks_delete.md) - Delete

</details>
<!-- End Available Commands [operations] -->

<!-- Start Request Body Input [stdinpiping] -->
## Request Body Input

Operations that accept a request body support three input methods, with a clear priority chain:

### Individual flags (highest priority)

```bash
paygentic <command> --name "Jane" --age 30
```

### `--body` flag

Provide the entire request body as a JSON string:

```bash
paygentic <command> --body '{"name": "John", "age": 30}'
```

Individual flags override `--body` values:

```bash
# Result: {name: "Jane", age: 30}
paygentic <command> --body '{"name": "John", "age": 30}' --name "Jane"
```

### Stdin piping (lowest priority)

Pipe JSON into any command that accepts a request body:

```bash
echo '{"name": "John", "age": 30}' | paygentic <command>
```

Individual flags override stdin values:

```bash
# Result: {name: "Jane", age: 30}
echo '{"name": "John", "age": 30}' | paygentic <command> --name "Jane"
```

This is useful for chaining commands, reading from files, or scripting:

```bash
# Read body from a file
paygentic <command> < request.json

# Pipe from another command
curl -s https://example.com/data.json | paygentic <command>
```

### Priority

When multiple input methods are used, the priority is:

| Priority | Source | Description |
|----------|--------|-------------|
| 1 (highest) | Individual flags | `--name "Jane"` always wins |
| 2 | `--body` flag | Whole-body JSON via flag |
| 3 (lowest) | Stdin | Piped JSON input |
<!-- End Request Body Input [stdinpiping] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Index

Use `--server <index>` to select a server by its zero-based index (default: `0`):

| #   | Server                             | Description    |
| --- | ---------------------------------- | -------------- |
| 0   | `https://api.paygentic.io`         | Production API |
| 1   | `https://api.sandbox.paygentic.io` | Sandbox API    |

```bash
paygentic --server <index> <command> [arguments]
```

### Override Server URL

Use `--server-url` to override the server URL entirely, bypassing any named or indexed server selection:

```bash
paygentic --server-url https://custom-api.example.com <command> [arguments]
```

**Precedence**: `--server-url` > `--server` > default
<!-- End Server Selection [server] -->

<!-- Start Output Formats [output-formats] -->
## Output Formats

Every command supports a `--output-format` flag that controls how the response is rendered to stdout.

### Available formats

| Format | Flag | Description |
|--------|------|-------------|
| Pretty | `--output-format pretty` (default) | Aligned key-value pairs with color, nested indentation. Human-readable at a glance. |
| JSON | `--output-format json` | JSON output. Passthrough when the response is already JSON (preserves original field order and numeric precision). Falls back to typed marshaling otherwise. |
| YAML | `--output-format yaml` | YAML output via standard marshaling. |
| Table | `--output-format table` | Tabular output for array responses. |
| TOON | `--output-format toon` | [Token-Oriented Object Notation](https://github.com/toon-format/spec) — a compact, line-oriented format that typically uses 30–60% fewer tokens than JSON. Well-suited for piping responses into LLM prompts. |

```bash
# Default pretty output
paygentic <command>

# Machine-readable JSON
paygentic <command> --output-format json

# TOON for LLM-friendly compact output
paygentic <command> --output-format toon

# Pipe JSON to jq without using --output-format
paygentic <command> --output-format json | jq '.fieldName'
```

### jq filtering

Use `--jq` to filter or transform the response inline using a [jq](https://jqlang.org) expression. This always outputs JSON and overrides `--output-format`:

```bash
# Extract a single field
paygentic <command> --jq '.name'

# Filter an array
paygentic <command> --jq '.items[] | select(.active == true)'
```

### Color control

Use `--color` to control terminal colors:

| Value | Behavior |
|-------|----------|
| `auto` (default) | Color when stdout is a TTY, plain text otherwise |
| `always` | Always colorize |
| `never` | Never colorize |

The `NO_COLOR` and `FORCE_COLOR` environment variables are also respected.

### Streaming and pagination

When using `--all` (pagination) or streaming operations, output is written incrementally as items arrive:

| Format | Streaming behavior |
|--------|-------------------|
| `json` | One compact JSON object per line ([NDJSON](https://github.com/ndjson/ndjson-spec)) |
| `yaml` | YAML documents separated by `---` |
| `toon` | One TOON-encoded object per block, separated by blank lines |
| `pretty` (default) | Pretty-printed items separated by blank lines |
<!-- End Output Formats [output-formats] -->

<!-- Start Error Handling [errors] -->
## Error Handling

The CLI uses standard exit codes to indicate success or failure:

| Exit Code | Meaning |
|-----------|---------|
| `0` | Success |
| `1` | Error (API error, invalid input, etc.) |

On success, the response data is printed to **stdout** as JSON. On failure, error details are printed to **stderr**.

```bash
# Capture output and handle errors
paygentic ... > output.json 2> error.log
if [ $? -ne 0 ]; then
  echo "Error occurred, see error.log"
fi
```
<!-- End Error Handling [errors] -->

<!-- Start Diagnostics [diagnostics] -->
## Diagnostics

The CLI includes two diagnostic flags available on all commands:

### Dry Run

Preview what would be sent without making any network calls:

```bash
paygentic <command> --dry-run
```

Output goes to stderr and includes:
- HTTP method and URL
- Request headers (sensitive values redacted)
- Request body preview (sensitive fields redacted)

The command exits successfully without contacting the API. This is useful for verifying request construction before executing.

### Debug

Log request and response diagnostics while running normally:

```bash
paygentic <command> --debug
```

Debug output goes to stderr and includes:
- Request method, URL, headers, and body preview
- Response status, headers, and body preview
- Transport errors (if any)

The command still executes normally and produces its regular output on stdout.

### Flag Precedence

If both `--dry-run` and `--debug` are set, `--dry-run` takes precedence and no network calls are made.

### Security

Sensitive information is automatically redacted in diagnostic output:
- **Headers**: `Authorization`, `Cookie`, `Set-Cookie`, `X-API-Key`, and other security headers show `[REDACTED]`
- **Body**: JSON fields named `password`, `secret`, `token`, `api_key`, `client_secret`, etc. show `[REDACTED]`

Diagnostic output should still be treated as potentially sensitive operational data.
<!-- End Diagnostics [diagnostics] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This CLI is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this CLI, this library is generated programmatically. Any manual changes added to internal files will be overwritten on the next generation. 
We look forward to hearing your feedback. Feel free to open a PR or an issue with a proof of concept and we'll do our best to include it in a future release. 

### CLI Created by [Speakeasy](https://www.speakeasy.com/?utm_source=github-com/paygentic/cli&utm_campaign=cli)
