---
name: Subscribe to Avaya Infinity events and keep the subscription alive
description: Register a webhook endpoint for agent and interaction events on Avaya Infinity, then renew the subscription before it expires so delivery does not silently stop.
api: openapi/avaya-infinity-notifications-openapi.yml
operations: [createSubscription, listSubscriptions, getSubscription, renewSubscription, updateSubscription, deleteSubscription]
generated: '2026-09-14'
method: generated
source: derived from openapi/avaya-infinity-notifications-openapi.yml and asyncapi/avaya-webhooks.yml
---

# Subscribe to Avaya Infinity events and keep the subscription alive

Base: `https://core.{customerId}.ec.avayacloud.com/api/events/v1`. Bearer token from the skill
*Authenticate with Avaya Infinity and read live queue metrics*.

## Step 1 — create the subscription (`createSubscription`)

`POST /subscriptions`

Choose one or more event families from the enum the contract declares:

| Family | Events described |
|---|---|
| `AGENT` | login, logout, ready / not-ready state changes |
| `INTERACTION` | created, completed, transferred |
| `QUEUE` | queue events |
| `ALL` | every family |

The transport block names your endpoint and the method Avaya will use — `POST` or `PUT`.

**Use `POST /subscriptions`, not `POST /accounts/{accountId}/subscriptions`.** The account-scoped
forms of all six operations are marked `deprecated: true` in the contract
(`createSubscriptionLegacy`, `listSubscriptionsLegacy`, `getSubscriptionLegacy`,
`updateSubscriptionLegacy`, `deleteSubscriptionLegacy`, `renewSubscriptionLegacy`).

## Step 2 — renew before expiry (`renewSubscription`)

`POST /subscriptions/{subscriptionId}:renew`

**This is the step that gets missed.** Avaya subscriptions are time-limited. If the renew call does
not land before expiry, the subscription lapses and events stop arriving with no error on your side —
you simply go quiet. Schedule the renewal, and check `status` (`ACTIVE` / `INACTIVE` / `PENDING`) with
`getSubscription` on the same timer.

## Step 3 — inspect and tear down

- `listSubscriptions` — `GET /subscriptions`, paged with `pageNumber` / `pageSize`
- `getSubscription` — `GET /subscriptions/{subscriptionId}`
- `updateSubscription` — `PATCH /subscriptions/{subscriptionId}`
- `deleteSubscription` — `DELETE /subscriptions/{subscriptionId}`

## Rules

- **No idempotency key.** Calling `createSubscription` twice creates two subscriptions and you will
  receive every event twice. Before retrying a create that timed out, call `listSubscriptions` and
  check whether the first one landed.
- **Delete is not reversible.** There is no restore and no retention window. See
  `conventions/avaya-conventions.yml` → `reversibility`.
- Avaya publishes **no signature or HMAC verification scheme** for delivered webhooks in the
  contract, so authenticate the callback at your own edge.
