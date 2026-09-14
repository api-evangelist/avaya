---
name: Authenticate with Avaya Infinity and read live queue metrics
description: Obtain a bearer token from the tenant Keycloak realm and query real-time queue occupancy, agent availability and wait counts on the Avaya Infinity contact center platform.
api: openapi/avaya-infinity-queue-metrics-openapi.yml
operations: [generateAccessToken, queryQueueMetrics, listQueues, describeQueue]
generated: '2026-09-14'
method: generated
source: derived from openapi/avaya-infinity-access-token-openapi.yml, openapi/avaya-infinity-queue-metrics-openapi.yml, openapi/avaya-infinity-queue-management-openapi.yml and conventions/avaya-conventions.yml
---

# Authenticate with Avaya Infinity and read live queue metrics

## Before you start

There is **no shared base URL**. Every Avaya Infinity tenant gets its own host:

```
https://core.{customerId}.ec.avayacloud.com
```

`{customerId}` is your Avaya-issued tenant subdomain. You cannot discover it — it is handed to you
with the client credentials. Ask for both together.

Client id and secret are issued by Avaya, not self-serve. See
<https://developers.avayacloud.com/avaya-infinity/docs/obtaining-a-client-id-and-secret-from-avaya>.

## Step 1 — get a token (`generateAccessToken`)

`POST /auth/realms/avaya/protocol/openid-connect/token` on the tenant host.

- `Content-Type: application/x-www-form-urlencoded`
- `grant_type=client_credentials`, plus `client_id` and `client_secret`
- Request the scope the operation needs — `workflows:execute` is the only scope the published
  contract declares.

The response carries `access_token`, `expires_in`, `refresh_token`, `token_type: bearer` and `scope`.

**The access token lives 900 seconds and the refresh token 9000 seconds.** Cache it and refresh on a
timer; do not mint a new token per request.

## Step 2 — find the queue (`listQueues`, `describeQueue`)

`GET /api/config/v1/queues` returns the queues on the tenant. `GET /api/config/v1/queues/{id}`
returns one. Page with `pageNumber` and `pageSize` — there is no cursor.

## Step 3 — query metrics (`queryQueueMetrics`)

`POST /api/matching-extensions/v1/queue-metrics` with `Authorization: Bearer <token>`.

Returns real-time operational metrics — agent availability, engagement wait counts, queue occupancy.
This is a **read**; it is safe to retry.

## Rules that apply to every call

- **No idempotency.** Avaya publishes no `Idempotency-Key` header on any of its 367 operations. This
  step is read-only so retries are safe, but do not carry that assumption into the write skills.
- **Errors** are RFC 7807-shaped: `type`, `title`, `status`, `detail`. A `401` usually means the
  900-second token expired — refresh and retry once. See `errors/avaya-problem-types.yml`.
- **429** means the tenant quota or the spike limit is exhausted. Avaya documents `Retry-After` and
  the `RateLimit-*` family but marks them "Coming Soon" and does not return them yet, so back off
  exponentially from a local timer rather than reading a budget off the response.
