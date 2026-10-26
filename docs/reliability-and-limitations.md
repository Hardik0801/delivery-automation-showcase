# Reliability, safeguards and limitations

## Reliability design

**Durable work:** The backend persists scheduled operations and tracks worker claims, attempts and outcomes.

**Deduplication:** Inbound provider events are checked against recorded message identifiers. Repeated delivery imports with matching scheduling details can return the existing record.

**Database choice:** SQLite supports small local deployments. PostgreSQL is supported for hosted backend use and concurrent workers.

**Uncertain external results:** Provider requests are executed outside database transactions. This avoids holding transactions open during network calls, but an external request may succeed before its result is committed. Therefore exactly-once external messaging is not guaranteed.

**Retry discipline:** Uncertain customer-message sends go to staff review rather than being retried automatically. Carrier mutation replay depends on whether the specific adapter supports a verified idempotency contract.

## Safeguards

- WhatsApp opt-in is required for the documented import workflow.
- Signed inbound webhook events are validated.
- Administrative API access requires authentication.
- Sensitive credentials belong in private configuration, not in source control.
- Production use needs access controls, retention rules and secure handling of phone numbers and backups.

## Current limitations

- The Streamlit demo uses simulated services only.
- Live WhatsApp operation needs a configured Meta app, approved templates, and hosting.
- A real carrier integration must implement the adapter contract.
- A review alert is not a dispatch hold or booking edit.
- Plain-text WhatsApp replies are not processed as customer button selections.
- Delivery/read receipts do not currently drive delivery analytics.
- Automated cancellation handling, opt-out automation and booking edits are not part of the documented implementation.
- The retailer pilot is a reviewed Shopify CSV workflow, not an installed Shopify app.

## What I would improve next

1. Connect a carrier sandbox and validate idempotent booking behavior end to end.
2. Add operational controls that explicitly link review states to dispatch holds.
3. Build opt-out and cancellation workflows.
4. Expand delivery analytics and production monitoring.

These are **future improvements**, not features claimed to be implemented.
