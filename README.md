# DataLink Nexus — Postman API Collections

Postman collections for the **DataLink Nexus** tenant API — one per queue type and platform feature,
so you can exercise the live API end to end (publish, consume, ack/nack, masking, tokenization,
cross-tenant fan-out, and more) from Postman.

## Quick start

1. **Import the collections** in [`collections/`](collections/) into Postman.
2. **Import the environment** [`datalinknexus-tenant.postman_environment.json`](datalinknexus-tenant.postman_environment.json).
   It already points at the public demo tenant (`tenant_exp_url = https://example.dev.datalinknexus.com`)
   and user `demo@datalinknexus.com` — just fill in **`user_password`** with the demo password.
3. Select the environment, pick a collection, and hit **Run**. The auth/setup requests run first and
   populate the variables the rest of the collection needs.

> The demo tenant is a shared sandbox — please be gentle; data may reset periodically.

## What's in here (18 collections)

**Queue types**
- `one-to-one`, `one-to-many` — point-to-point and fan-out delivery
- `key-value` — latest-value-per-key
- `time-series` — bucketed aggregates
- `stream-to-one`, `stream-to-many` — enrichment streams
- `document` — encrypted document store

**Data protection & validation**
- `masking` — field masking + tokenization on delivery
- `schema-validation`, `create-validation` — payload + queue-config validation

**Platform features**
- `storage-quota`, `storage-quota-caps` — tenant storage limits
- `ts-retention` — time-series retention
- `environments` — per-tenant environments
- `billing` — usage/metering
- `feedback` — bug/feature reporting
- `file-upload` — document upload
- `cross-tenant` — cross-tenant subscription fan-out

## Notes

- The collections use Postman **variables** only — no credentials are baked in.
- Every request sends a unique `X-Correlation-Id` (the API enforces per-request uniqueness).
- Learn more at **https://datalinknexus.com**.
