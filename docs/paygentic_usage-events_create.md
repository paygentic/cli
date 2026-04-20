## paygentic usage-events create

Create

### Synopsis

Creates a usage event. The idempotencyKey is used to ensure the event is processed only once by downstream consumers, even if the same event is submitted multiple times. Duplicate submissions will be accepted and return the same response.

```
paygentic usage-events create [flags]
```

### Examples

```
  paygentic usage-events create --customer-id <id> --idempotency-key <value> --merchant-id <id> --properties '[]' --timestamp 2026-05-14T00:54:35.100Z
```

### Options

```
      --body string              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
  -c, --customer-id string       Customer identifier that generated this consumption event. Sample values: 'cus_abc123xyz', 'cus_789def456' [required]
  -e, --entitlement-id string    Commitment identifier for this consumption event. Sample values: 'com_abc123xyz', 'com_789def456'
  -h, --help                     help for create
  -i, --idempotency-key string   Unique deduplication key preventing duplicate event processing. Sample values: 'usg_2024_01_15_abc123', 'event_wallet_xyz789', 'consumption_ref_456def' [required]
      --merchant-id string       Merchant organization identifier owning this consumption event. Sample values: 'org_abc123xyz', 'org_789def456' [required]
      --metadata string          Custom key-value attributes providing context about the consumption event. Sample values: {"model_name": "claude-3-opus", "input_tokens": "1500", "output_tokens": "800"} or {"storage_tier": "premium", "data_center": "eu-west-1", "encryption": "enabled"} or {"image_resolution": "1024x1024", "generation_model": "stable-diffusion-xl"}
  -p, --properties string        [required]
  -t, --timestamp string         Actual occurrence timestamp for the consumption event in ISO 8601 format. Sample values: '2024-01-15T10:30:00Z', '2024-02-01T14:45:30Z'. Represents when the event occurred, not when Paygentic received it. [required]
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

* [paygentic usage-events](paygentic_usage-events.md)	 - Operations for usage-events
