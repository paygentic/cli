## paygentic events ingest

Ingest Event

### Synopsis

Ingest a raw metering event. The event is published to the meter-events PubSub topic for processing by the meters service.

```
paygentic events ingest [flags]
```

### Examples

```
  paygentic events ingest --type ai.inference --source https://api.myapp.com --subject cus_abc123 --data '{"tokens":1500,"model":"gpt-4o"}'
```

### Options

```
      --body string              Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --data string              Event payload containing the metering data. [required]
  -h, --help                     help for ingest
  -i, --idempotency-key string   User-provided deduplication key. If not provided, a unique key is generated.
  -n, --namespace string         Organization/merchant ID. Defaults to the authenticated user's organization. Platform users can specify a different organization.
      --source string            Event source URI identifying the application. [required]
      --subject string           Customer or entity ID this event relates to. [required]
      --timestamp string         Event timestamp. Defaults to server time if not provided.
      --type string              CloudEvents type. Must match an eventType configured on a BillableMetric. [required]
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

* [paygentic events](paygentic_events.md)	 - Ingest raw metering events that are processed by the meters service
