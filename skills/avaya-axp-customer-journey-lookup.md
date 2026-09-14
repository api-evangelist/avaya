---
name: Look up a customer journey and annotate an engagement on AXP
description: Resolve a customer by identifier, read their engagement history, add an agent note, and pull the conversation transcript.
api: openapi/avaya-axp-customer-journey-openapi.yml
operations: [createIdentifier, getIdentifiers, getIdentifier, getJourneys, getEngagements, getEngagement, appendIdentifiers, createAgentNote, getAgentNotes, listMessages]
generated: '2026-09-14'
method: generated
source: derived from openapi/avaya-axp-customer-journey-openapi.yml and openapi/avaya-axp-transcript-retrieval-openapi.yml
---

# Look up a customer journey and annotate an engagement

Base: `https://{region}.api.avayacloud.com/accounts/{accountId}`. Bearer JWT **and** `appkey` header.

## Step 1 — resolve the customer (`getIdentifiers`, `getIdentifier`, `createIdentifier`)

An identifier is the phone number, email or external id that ties conversations to one person.

- `GET /accounts/{accountId}/identifiers` — list, paged with `pageNumber` / `pageSize`
- `GET /accounts/{accountId}/identifiers/{identifierId}` — read one
- `POST /accounts/{accountId}/identifiers` — create one when the customer is new

## Step 2 — search the journey (`getJourneys`)

`POST /accounts/{accountId}/journeys:search` returns the stitched history across channels.
`POST /accounts/{accountId}/journeys:listAgents` (`listAgents`) names the agents who handled it.

## Step 3 — read the engagements (`getEngagements`, `getEngagement`)

- `GET /accounts/{accountId}/engagements`
- `GET /accounts/{accountId}/engagements/{engagementId}`

Attach a newly-discovered identifier to an existing engagement with `appendIdentifiers`
(`POST /accounts/{accountId}/engagements/{engagementId}:appendIdentifiers`).

## Step 4 — pull the transcript (`listMessages`)

`GET /accounts/{accountId}/engagements/{engagementId}/messages` on the Transcript - Retrieval API
returns the message record for the engagement.

## Step 5 — annotate (`createAgentNote`, `getAgentNotes`)

- `POST /accounts/{accountId}/engagements/{engagementId}/agent-note`
- `GET /accounts/{accountId}/engagements/{engagementId}/agent-notes`

## Rules

- Steps 1-4 are reads and safe to retry. Step 5 is a write with **no idempotency key** — a retried
  note create leaves two notes on the engagement. Read `getAgentNotes` before retrying.
- `unlinkIdentifier` (`POST /accounts/{accountId}/journeys:unlinkIdentifier`) and `deleteIdentifiers`
  (`POST /accounts/{accountId}/identifiers:delete`) break the customer's stitched history and have no
  documented restore. Treat both as destructive.
- This flow reads customer conversation content. Handle it under the tenant's own data-protection
  obligations; Avaya's posture is at <https://www.avaya.com/en/trust-center/privacy/>.
