<!-- Start SDK Example Usage [usage] -->
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
<!-- End SDK Example Usage [usage] -->