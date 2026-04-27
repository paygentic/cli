## paygentic entitlements issue

Issue Entitlement

### Synopsis

Issue a new entitlement to a customer, granting them access to a specific feature. The feature must exist and belong to the same merchant as the customer.

```
paygentic entitlements issue [flags]
```

### Examples

```
  paygentic entitlements issue --customer-id cus_q3r4s5t6u7v8w9x0 --feature-id feat_a1b2c3d4e5f6g7h8 --template '{"type":"boolean"}'
```

### Options

```
      --active-from string                                When the entitlement becomes active. Defaults to now.
      --active-to string                                  When the entitlement expires. Null means no expiration.
      --body string                                       Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --customer-id string                                Unique identifier for a customer [required]
  -f, --feature-id string                                 The feature to grant access to. [required]
  -h, --help                                              help for issue
  -m, --metadata string                                   Additional metadata for the entitlement.
  -s, --subscription-id string                            Optional subscription ID to associate with this entitlement.
  -t, --template string                                   JSON value (variants: boolean: { type: string }, static: { type: string, config: object }, metered: { type: string, usagePeriod: object, isSoftLimit: boolean, issueAfterReset: number, ... })
      --template.boolean string                           EntitlementTemplate_Boolean variant as JSON
      --template.metered string                           EntitlementTemplate_Metered variant as JSON
      --template.metered.is-soft-limit                    When false (hard limit), access is blocked when balance is exhausted and overage is not charged on invoices. When true (soft limit), access continues past the grant and overage is charged at the per-unit rate.
      --template.metered.issue-after-reset float          Amount of grants to issue after each period reset.
      --template.metered.issue-after-reset-priority int   Priority for grants issued after reset.
      --template.metered.preserve-overage-at-reset        When true, overage from the previous period carries over.
      --template.metered.reset-max-rollover float         Maximum amount of unused balance that rolls over on reset.
      --template.metered.reset-min-rollover float         Minimum amount of balance guaranteed to roll over on reset.
      --template.metered.usage-period string              [required]
      --template.static string                            EntitlementTemplate_Static variant as JSON
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

* [paygentic entitlements](paygentic_entitlements.md)	 - Operations for entitlements
