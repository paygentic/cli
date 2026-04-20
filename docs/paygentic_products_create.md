## paygentic products create

Create

### Synopsis

Create

```
paygentic products create [flags]
```

### Examples

```
  paygentic products create --description at through very dishearten knife ashamed baa beret amongst --merchant-id <id> --name <value>
```

### Options

```
      --body string          Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --description string   Customer-visible product summary explaining capabilities and use cases. Sample values: 'Enterprise access to advanced language models for natural language tasks', 'Scalable data warehousing with real-time query capabilities', 'On-demand AI image generation using diffusion models', 'Distributed computing infrastructure for training deep learning models', 'High-performance vector similarity search database', 'Production-ready speech-to-text conversion service' [required]
  -h, --help                 help for create
      --merchant-id string   Unique identifier for an organization [required]
      --metadata string      Optional key-value metadata storage for product information. Sample values: {"category": "ai_services", "tier": "enterprise"}, {"region": "global", "support_level": "premium"}
  -n, --name string          Customer-facing product title shown in invoices and dashboards. Sample values: 'Large Language Model Service', 'Cloud Data Warehouse', 'AI Image Creator', 'Neural Network Training Platform', 'Vector Database', 'Speech Recognition API' [required]
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

* [paygentic products](paygentic_products.md)	 - A `Product` is an offering sold by a `Merchant`
