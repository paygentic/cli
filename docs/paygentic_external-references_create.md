## paygentic external-references create

Create

### Synopsis

Create

```
paygentic external-references create [flags]
```

### Examples

```
  paygentic external-references create --merchant-id <id> --entity-type item --entity-id <id> --provider <value> --external-id <id>
```

### Options

```
      --body string                                   Request body as JSON (alternative to individual flags). Can also be provided via stdin.
      --entity-id itm_xxx                             Paygentic id of the entity, e.g. itm_xxx [required]
      --entity-type string                            The type of Paygentic entity this external reference points at (options: item, customer) [required]
      --external-id string                            Identifier of the record in the external system [required]
      --external-label string                         Human-friendly name shown in UIs (e.g. a NetSuite financial-treatment name)
  -h, --help                                          help for create
      --is-default (entityType, entityId, provider)   Whether this is the code sent *to* the provider for this entity. At most one per (entityType, entityId, provider). **Omit** to have the entity's first code for the provider designated automatically — see the note on `isPrimary` for why this carries no schema default.
      --is-primary (provider, externalId)             Whether this reference claims (provider, externalId) — the code resolves back to this one entity. Unique per merchant; unclaimed references are aliases. **Omitting it claims the code.** Send `false` for a code that is only ever sent outward, such as a ledger account several items post to — claiming that refuses the second item to use it. The default is not derived from the provider: what a code is for is a property of the operation recording it, and one provider can both resolve an arriving code and be sent a selected one. Declaring a schema default here would defeat the distinction, because a generated client materialises the default into the request body and the caller can no longer express "I did not say".
      --merchant-id string                            [required]
      --metadata { "sfObject": "Product2" }           Provider-specific fields (e.g. { "sfObject": "Product2" })
      --move-claim 409                                Take this code's claim from whichever entity currently holds it, in the same transaction.
                                                      
                                                      Without it, claiming a code another entity claims is a 409 identifying the holder — the right answer to an accident, and the common case. With it, the reassignment is the point.
                                                      
                                                      It exists because the alternative route — remove the old claim, then create the new one — leaves a window in which the code resolves to nothing. An arrival in that window is still recorded, untagged rather than rejected, so nothing is lost; but it is silent while it lasts and leaves work to repair.
                                                      
                                                      Deliberately opt-in, unlike moving a designation. A designation moves within one entity; a claim moves *between* entities and changes what future arrivals resolve to, which should never be a side effect of recording a code. Ignored when the write is not claiming the code.
  -p, --provider salesforce                           Lowercase snake_case provider identifier (e.g. salesforce, `netsuite`) [required]
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

* [paygentic external-references](paygentic_external-references.md)	 - An `ExternalReference` links a Paygentic entity (e
