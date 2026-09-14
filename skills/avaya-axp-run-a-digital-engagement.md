---
name: Run a custom digital chat engagement on Avaya Experience Platform
description: Create a digital session, open an engagement, exchange messages, subscribe to the message webhooks, and disconnect cleanly.
api: openapi/avaya-axp-digital-custom-chat-openapi.yml
operations: [createDigitalSession, getDigitalSession, createDigitalEngagement, joinDigitalEngagement, sendDigitalMessage, listDigitalMessages, appendIdentifiersInDigitalSession, disconnectDigitalEngagement, createDigitalWebhookSubscription]
generated: '2026-09-14'
method: generated
source: derived from openapi/avaya-axp-digital-custom-chat-openapi.yml, openapi/avaya-axp-digital-notification-openapi.yml and asyncapi/avaya-webhooks.yml
---

# Run a custom digital chat engagement on Avaya Experience Platform

Base: `https://{region}.api.avayacloud.com/accounts/{accountId}`. Bearer JWT **and** `appkey` header.

## Step 1 — subscribe to events first (`createDigitalWebhookSubscription`)

`POST /accounts/{accountId}/subscriptions` (Digital - Notification API)

Do this **before** creating the engagement, or you will miss `ENGAGEMENT_CREATED`. Event types:

`MESSAGES`, `CUSTOMER_MESSAGES`, `CC_MESSAGES`, `PARTICIPANT_ADDED`, `PARTICIPANT_DISCONNECTED`,
`ENGAGEMENT_CREATED`, `ENGAGEMENT_ERROR`, `TYPING`, `ALL`.

This is the one Avaya spec that declares OpenAPI `callbacks`, so the delivered payload shape is
machine-readable — read it from the spec rather than from prose.

## Step 2 — create the session (`createDigitalSession`)

`POST /accounts/{accountId}/sessions` returns the session the customer conversation hangs off.
`GET /accounts/{accountId}/sessions/{sessionId}` reads it back.

Attach customer identity with `appendIdentifiersInDigitalSession`
(`POST /accounts/{accountId}/sessions/{sessionId}:appendIdentifiers`) so the engagement lands on the
right customer journey.

## Step 3 — open and join the engagement

- `createDigitalEngagement` — `POST /accounts/{accountId}/engagements`
- `joinDigitalEngagement` — `POST /accounts/{accountId}/engagements/{engagementId}:join`

## Step 4 — exchange messages

- `sendDigitalMessage` — `POST /accounts/{accountId}/engagements/{engagementId}/messages`
- `listDigitalMessages` — `GET /accounts/{accountId}/engagements/{engagementId}/messages`

Message bodies support `PLAINTEXT`, `HTML` and `MARKDOWN`. Participant roles are `CUSTOMER`, `AGENT`,
`SUPERVISOR`, `SYSTEM`, `BOT`. Delivery states are `NONE`, `SENT`, `DELIVERED`, `READ`, `FAILED`,
`DELETED`.

> **`sendDigitalMessage` has no idempotency key.** A retried send delivers the message twice to a real
> human. If a send times out, call `listDigitalMessages` and check before resending.

## Step 5 — disconnect (`disconnectDigitalEngagement`)

`POST /accounts/{accountId}/engagements/{engagementId}:disconnect`

**Terminal.** A disconnected engagement cannot be reopened; there is no reconnect operation. Start a
new engagement on the same session instead.

## Rules

- Nothing in this flow is reversible. `disconnect` ends a live conversation and
  `deleteDigitalSession` destroys the session — neither has a restore path or a stated window.
- `429` carries no readable budget yet (the `RateLimit-*` headers are documented as "Coming Soon"), so
  rate-limit yourself.
