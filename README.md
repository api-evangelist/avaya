# Avaya

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Avaya is a global enterprise communications company whose developer surface spans two cloud platforms: Avaya Infinity, the cloud-native customer experience platform launched in 2025, and Avaya Experience Platform (AXP), the CCaaS generation that preceded it. Between them they publish 40 OpenAPI 3.0 documents and 367 operations across administration (users, groups, profiles, queues, timetables, extensions, Communication Manager and hybrid cloud gateways), customer journey and engagement history, digital chat and custom messaging, transcripts, historical and real-time analytics, workflow sessions, outbound campaigns, and a webhook/WebSocket event surface. Authentication is a bearer JWT issued by a per-tenant Keycloak realm, carried alongside a tenant appkey header; every path is rooted at an account id and the Infinity host itself is per-tenant. Avaya publishes an llms.txt, an RFC 9727 API catalog, a public Postman workspace and first-party JavaScript SDKs, but no MCP server, no idempotency mechanism and no public pricing.

**Areas:** Communications · Contact Center · Collaboration · Artificial Intelligence · UCaaS · CCaaS · Customer Experience · Telephony · Webhook · Enterprise Software · Unified Communications · Customer Service

## Avaya on APIs.io

Everything profiled for Avaya is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/avaya/](https://apis.io/providers/avaya/)** — or go straight to one of the APIs or properties below.

### APIs (84)

- [Avaya Access Token API](https://apis.io/apis/avaya/avaya-access-token-api/) — Includes token related operations.
- [Avaya Account API](https://apis.io/apis/avaya/avaya-account-api/) — APIs to manage Accounts.
- [Avaya Agent Location API](https://apis.io/apis/avaya/avaya-agent-location-api/) — Agent location Routing APIs for System Administrator. It will enable agents connecting from different countries to be able to go through specific trunks or…
- [Avaya Agent Notes API](https://apis.io/apis/avaya/avaya-agent-notes-api/) — The Agent Notes API from Avaya — 4 operation(s) for agent notes.
- [Avaya Agents API](https://apis.io/apis/avaya/avaya-agents-api/) — Monitor and manage agent status and activity
- [Avaya Asynchronous Messages API](https://apis.io/apis/avaya/avaya-asynchronous-messages-api/) — Messages related to non-session based communication with the contact center are considered to be asynchronous messages. Based on the information passed, the…
- [Avaya Audit Records API](https://apis.io/apis/avaya/avaya-audit-records-api/) — Search or export audit records for auditable objects.
- [Avaya Available Phone Numbers API](https://apis.io/apis/avaya/avaya-available-phone-numbers-api/) — The available phone numbers that can be added to the contact center.
- [Avaya Avaya Aura Device Services API](https://apis.io/apis/avaya/avaya-avaya-aura-device-services-api/) — Administration of Avaya Aura Device Service Elements. These API are expected to be called by an account administrator. AADS is the abbreviated form for…
- [Avaya Avaya Cloud Office management API](https://apis.io/apis/avaya/avaya-avaya-cloud-office-management-api/) — APIs to manage Avaya Cloud Office element in voice service
- [Avaya Avaya Cloud Office SIP Trunks API](https://apis.io/apis/avaya/avaya-avaya-cloud-office-sip-trunks-api/) — APIs to manage Avaya Cloud Office SIP Trunk element in voice service
- [Avaya Bulk Job API](https://apis.io/apis/avaya/avaya-bulk-job-api/) — Bulk operations related to the Jobs responsible for creating users.
- [Avaya Bulk User API](https://apis.io/apis/avaya/avaya-bulk-user-api/) — Bulk operations related to Users, Add, Update, Delete, Export.
- [Avaya Calls API](https://apis.io/apis/avaya/avaya-calls-api/) — Trigger and complete calls
- [Avaya Campaigns API](https://apis.io/apis/avaya/avaya-campaigns-api/) — Manage outbound campaigns
- [Avaya Category API](https://apis.io/apis/avaya/avaya-category-api/) — Routing is implemented by matching the attributes specified on an engagement, either through customer choice or by business logic, against the attributes…
- [Avaya Comm Manager Job Details API](https://apis.io/apis/avaya/avaya-comm-manager-job-details-api/) — This API is used to get details of list of jobs or a single job for a specific Communication Manager. These API are expected to be called by an account…
- [Avaya Communication Manager API](https://apis.io/apis/avaya/avaya-communication-manager-api/) — Administration of Communication Manager configuration. These API are expected to be called by an account administrator. CM is the abbreviated form for…
- [Avaya Country API](https://apis.io/apis/avaya/avaya-country-api/) — The countries in which available phone numbers are available.
- [Avaya Dataset API](https://apis.io/apis/avaya/avaya-dataset-api/) — The Dataset API from Avaya — 1 operation(s) for dataset.
- [Avaya Dictionaries API](https://apis.io/apis/avaya/avaya-dictionaries-api/) — Dictionaries contain translations for measures for a specific locale and measure producer.
- [Avaya Dimensions API](https://apis.io/apis/avaya/avaya-dimensions-api/) — A Dimension is a collection of related contact center objects used to provide a view of measurement data.
- [Avaya DNC API](https://apis.io/apis/avaya/avaya-dnc-api/) — Do Not Call list management
- [Avaya Drafts API](https://apis.io/apis/avaya/avaya-drafts-api/) — Drafts prepared by an Agent at an early stage before it is in final form in response to Email or Messaging contact. At the moment, only one draft supported…
- [Avaya Element Management API](https://apis.io/apis/avaya/avaya-element-management-api/) — An Element is a server instance which provides feature capability. Some examples of elements are Avaya Cloud Office, Chat Connector, Microsoft Teams and so on.
- [Avaya Engagement API](https://apis.io/apis/avaya/avaya-engagement-api/) — Represents a resource of the Contact Center being allocated. Engagements can be assigned to one or many Conversations, although this is not mandatory.
- [Avaya Engagements API](https://apis.io/apis/avaya/avaya-engagements-api/) — Inbound engagements can be created from the customer side which are then handled by contact center resources like agents, supervisors and bots. Session Id's…
- [Avaya Extension API](https://apis.io/apis/avaya/avaya-extension-api/) — Management of non e164 Extension that are assigned to Account. These API are expected to be called by an account administrator.
- [Avaya Gateway Connection Manager API](https://apis.io/apis/avaya/avaya-gateway-connection-manager-api/) — Get Details of Gateway Connection Manager. These API are expected to be called by an account administrator.
- [Avaya Group Management API](https://apis.io/apis/avaya/avaya-group-management-api/) — A Group is a logical collection of the resources like e.g. user. These groups can be assigned to a user to grant access to the resources present in the group.
- [Avaya Group Users API](https://apis.io/apis/avaya/avaya-group-users-api/) — Group membership operations
- [Avaya Groups API](https://apis.io/apis/avaya/avaya-groups-api/) — Group management operations
- [Avaya Holiday API](https://apis.io/apis/avaya/avaya-holiday-api/) — Holidays are non-working days where the contact center is not staffed by agents and therefore fall outside of the operating business hours.
- [Avaya Hybrid Cloud Gateway API](https://apis.io/apis/avaya/avaya-hybrid-cloud-gateway-api/) — Administration of Avaya Hybrid Cloud Gateway. These API are expected to be called by an account administrator. HCG is the abbreviated form for Hybrid Cloud…
- [Avaya Hybrid Cloud Manager API](https://apis.io/apis/avaya/avaya-hybrid-cloud-manager-api/) — Administration of Hybrid Cloud Manager.This API is expected to be called by an account administrator.
- [Avaya Hybrid Extension API](https://apis.io/apis/avaya/avaya-hybrid-extension-api/) — Management of hybrid extensions assigned to users. These API are expected to be called by an account administrator.
- [Avaya Hybrid Skill API](https://apis.io/apis/avaya/avaya-hybrid-skill-api/) — Administration of Hybrid Skills. These APIs are expected to be called by an account administrator.
- [Avaya Identifiers API](https://apis.io/apis/avaya/avaya-identifiers-api/) — Represents the criteria with which a customer may be identified (Phone numbers, e-mail addresses, social media handles).
- [Avaya Indicators API](https://apis.io/apis/avaya/avaya-indicators-api/) — Indicators are used to indicate the status of the conversation or the activity. For example, when a customer is typing a message, the typing indicator is…
- [Avaya Interactions API](https://apis.io/apis/avaya/avaya-interactions-api/) — The Interactions API from Avaya — 1 operation(s) for interactions.
- [Avaya Interval API](https://apis.io/apis/avaya/avaya-interval-api/) — Intervals are specific dates or working days of the week when the contact center is fully operational and staffed by agents and therefore fall with the…
- [Avaya Journey API](https://apis.io/apis/avaya/avaya-journey-api/) — Represents the history of Conversations and Engagements that a Customer has had with the business.
- [Avaya JWT Token API](https://apis.io/apis/avaya/avaya-jwt-token-api/) — The API provides jwt token used by SDK
- [Avaya Locales API](https://apis.io/apis/avaya/avaya-locales-api/) — The Locales supported for a each measure producer.
- [Avaya Location Profile API](https://apis.io/apis/avaya/avaya-location-profile-api/) — This API is for managing location profiles. These API are expected to be called by an account administrator.
- [Avaya Measure Producers API](https://apis.io/apis/avaya/avaya-measure-producers-api/) — Operations connected to measure producer management.
- [Avaya Media API](https://apis.io/apis/avaya/avaya-media-api/) — This tag is used to upload or download media using signed URI.
- [Avaya Messaging API](https://apis.io/apis/avaya/avaya-messaging-api/) — Send end user messages to the contact center.
- [Avaya Microsoft Teams management API](https://apis.io/apis/avaya/avaya-microsoft-teams-management-api/) — APIs to manage Microsoft Teams element in voice service.
- [Avaya Microsoft Teams SIP Trunks API](https://apis.io/apis/avaya/avaya-microsoft-teams-sip-trunks-api/) — APIs to manage Microsoft Teams SIP Trunk element in voice service.
- [Avaya Organization Structure API](https://apis.io/apis/avaya/avaya-organization-structure-api/) — APIs to manage a customer's organization structure
- [Avaya Outbound Number Routing Rules API](https://apis.io/apis/avaya/avaya-outbound-number-routing-rules-api/) — APIs to manage Outbound Call Number Routing Rules in voice service by an account administrator.
- [Avaya Participant API](https://apis.io/apis/avaya/avaya-participant-api/) — The Participant API from Avaya — 2 operation(s) for participant.
- [Avaya Phone Number API](https://apis.io/apis/avaya/avaya-phone-number-api/) — Management of phone numbers that are the entry point for contact center voice engagements. Phone number can be assigned and released.
- [Avaya Profile API](https://apis.io/apis/avaya/avaya-profile-api/) — A Profile is a grouping of individual features which are provisioned with pre-defined values that can be applied to a User.
- [Avaya Profile Management API](https://apis.io/apis/avaya/avaya-profile-management-api/) — Operations related to profile management: Create, Get, Update, Delete, List profiles.
- [Avaya Provider Dialogs API](https://apis.io/apis/avaya/avaya-provider-dialogs-api/) — When a message for a conversation, represented by providerDialogId, is sent, a corresponding engagement and dialog is either created or existing engagement…
- [Avaya Queue API](https://apis.io/apis/avaya/avaya-queue-api/) — Queue's are used to identify a pool of contact center agents for which Customer engagements can be matched and routed.
- [Avaya Queue Metrics API](https://apis.io/apis/avaya/avaya-queue-metrics-api/) — Metrics associated with a routing queue.
- [Avaya Queues API](https://apis.io/apis/avaya/avaya-queues-api/) — Queue lifecycle management — create, retrieve, update, and delete queues.
- [Avaya Reason Codes API](https://apis.io/apis/avaya/avaya-reason-codes-api/) — Reason codes are a set of codes that agents can select from agent desktop clients to further describe their current activity or state. Reason Codes consist…
- [Avaya Records API](https://apis.io/apis/avaya/avaya-records-api/) — Manage outbound campaign records
- [Avaya Reports API](https://apis.io/apis/avaya/avaya-reports-api/) — A Report is a collection of contact center measurements related to a particular dimension.
- [Avaya Resource Partition API](https://apis.io/apis/avaya/avaya-resource-partition-api/) — Resource Partitions are grouping of any resources like CLID which are used while making outgoing communication. These resource partitions ultimately…
- [Avaya Sessions API](https://apis.io/apis/avaya/avaya-sessions-api/) — Sessions are used to hold context information about the customer and the clients used by the customer. A customer can have multiple active sessions at the…
- [Avaya Signed URI API](https://apis.io/apis/avaya/avaya-signed-uri-api/) — This section is to used to generate signed uri for the respective request.
- [Avaya SIP Trunks API](https://apis.io/apis/avaya/avaya-sip-trunks-api/) — This API is used to get list of all SIP trunk elements and update caller id for an account administrator.
- [Avaya Skills API](https://apis.io/apis/avaya/avaya-skills-api/) — Manage skills and agent/campaigns assignments
- [Avaya Subscriptions API](https://apis.io/apis/avaya/avaya-subscriptions-api/) — Manage subscriptions for digital events.
- [Avaya Sync Aura Entities API](https://apis.io/apis/avaya/avaya-sync-aura-entities-api/) — Set of API to initiate synchronization of data from Aura to AXP admin. These API are expected to be called by an account administrator.
- [Avaya System Manager API](https://apis.io/apis/avaya/avaya-system-manager-api/) — Administration of System Manager. These API are expected to be called by an account administrator.
- [Avaya Timetable API](https://apis.io/apis/avaya/avaya-timetable-api/) — Timetables are a time zone specific schedule of holidays (non-working days) and intervals (working days).
- [Avaya Transcript API](https://apis.io/apis/avaya/avaya-transcript-api/) — Save transcript of a dialog that captures messages exchanged between different participants
- [Avaya Transcription API](https://apis.io/apis/avaya/avaya-transcription-api/) — The Transcription API from Avaya — 2 operation(s) for transcription.
- [Avaya Transcripts API](https://apis.io/apis/avaya/avaya-transcripts-api/) — Endpoints for creating and retrieving transcript messages
- [Avaya User API](https://apis.io/apis/avaya/avaya-user-api/) — Represents a user in the system. A user can be an Agent, Supervisor or an Administrator.
- [Avaya User Password Policy API](https://apis.io/apis/avaya/avaya-user-password-policy-api/) — Represents the set of rules to be followed for the user passwords.
- [Avaya Users API](https://apis.io/apis/avaya/avaya-users-api/) — Manage system users
- [Avaya UX Profile API](https://apis.io/apis/avaya/avaya-ux-profile-api/) — A UX Profile represents a layout that can be applied to a user when using Avaya Workspaces.
- [Avaya Voice Numbers And Extensions API](https://apis.io/apis/avaya/avaya-voice-numbers-and-extensions-api/) — APIs to export the Voice Numbers and Agent Extensions and its associated fields in a CSV file for account administrator.
- [Avaya Voice Plan API](https://apis.io/apis/avaya/avaya-voice-plan-api/) — Represents Voice Plan of configured Communication Managers for Account Administrator. These API are expected to be called by an account administrator.
- [Avaya Workflow Sessions API](https://apis.io/apis/avaya/avaya-workflow-sessions-api/) — The Workflow Sessions API from Avaya — 5 operation(s) for workflow sessions.
- [Avaya Workspaces API](https://apis.io/apis/avaya/avaya-workspaces-api/) — Workspaces is a web-based application that provides a unified agent desktop. This API return the URL details.
- [Avaya Datasets API](https://apis.io/apis/avaya/avaya-datasets-api/) — Manage data sets within campaigns

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Avaya Webhooks](https://apis.io/asyncapis/avaya/avaya-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [avaya-mcp.yml](https://apis.io/servers/avaya/avaya-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Avaya Agentic Access](https://apis.io/agentic-access/avaya/avaya-agentic-access/)

#### Overlays (40)

OpenAPI overlays, including conversational phrasing for each operation.

- [Avaya Axp Admin Account Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-account-overlay/)
- [Avaya Axp Admin Element Inventory Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-element-inventory-overlay/)
- [Avaya Axp Admin Group Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-group-overlay/)
- [Avaya Axp Admin Match Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-match-overlay/)
- [Avaya Axp Admin Timetable Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-timetable-overlay/)
- [Avaya Axp Admin User Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-user-overlay/)
- [Avaya Axp Admin Voice Overlay](https://apis.io/overlays/avaya/avaya-axp-admin-voice-overlay/)
- [Avaya Axp Analytics Historical Data V1 Overlay](https://apis.io/overlays/avaya/avaya-axp-analytics-historical-data-v1-overlay/)
- [Avaya Axp Analytics Historical Data V2 Overlay](https://apis.io/overlays/avaya/avaya-axp-analytics-historical-data-v2-overlay/)
- [Avaya Axp Analytics Producer Management Overlay](https://apis.io/overlays/avaya/avaya-axp-analytics-producer-management-overlay/)
- [Avaya Axp Auth Overlay](https://apis.io/overlays/avaya/avaya-axp-auth-overlay/)
- [Avaya Axp Customer Journey Overlay](https://apis.io/overlays/avaya/avaya-axp-customer-journey-overlay/)
- [Avaya Axp Digital Custom Chat Overlay](https://apis.io/overlays/avaya/avaya-axp-digital-custom-chat-overlay/)
- [Avaya Axp Digital Custom Messaging Overlay](https://apis.io/overlays/avaya/avaya-axp-digital-custom-messaging-overlay/)
- [Avaya Axp Digital Notification Overlay](https://apis.io/overlays/avaya/avaya-axp-digital-notification-overlay/)
- [Avaya Axp Digital Sdk Auth Overlay](https://apis.io/overlays/avaya/avaya-axp-digital-sdk-auth-overlay/)
- [Avaya Axp Digital Signed Media Overlay](https://apis.io/overlays/avaya/avaya-axp-digital-signed-media-overlay/)
- [Avaya Axp Digital Signed Media Uri Overlay](https://apis.io/overlays/avaya/avaya-axp-digital-signed-media-uri-overlay/)
- [Avaya Axp Draft Retrieval Overlay](https://apis.io/overlays/avaya/avaya-axp-draft-retrieval-overlay/)
- [Avaya Axp Draft Save Overlay](https://apis.io/overlays/avaya/avaya-axp-draft-save-overlay/)
- [Avaya Axp Notification Overlay](https://apis.io/overlays/avaya/avaya-axp-notification-overlay/)
- [Avaya Axp Routing Queue Metrics Overlay](https://apis.io/overlays/avaya/avaya-axp-routing-queue-metrics-overlay/)
- [Avaya Axp Transcript Retrieval Overlay](https://apis.io/overlays/avaya/avaya-axp-transcript-retrieval-overlay/)
- [Avaya Axp Transcript Save Overlay](https://apis.io/overlays/avaya/avaya-axp-transcript-save-overlay/)
- [Avaya Infinity Access Token Overlay](https://apis.io/overlays/avaya/avaya-infinity-access-token-overlay/)
- …and 15 more published on APIs.io

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Avaya Authentication](https://apis.io/security/avaya/avaya-authentication/)
- [Avaya Domain Security](https://apis.io/security/avaya/avaya-domain-security/)
- [Avaya Trust Center](https://apis.io/security/avaya/avaya-trust-center/)
- [Avaya Vulnerability Disclosure](https://apis.io/security/avaya/avaya-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Avaya Scopes](https://apis.io/scopes/avaya/avaya-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Avaya Plans Pricing](https://apis.io/plans/avaya/avaya-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Avaya Rate Limits](https://apis.io/rate-limits/avaya/avaya-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.avaya.com/en/)
- [Documentation](https://developers.avayacloud.com/avaya-infinity/docs/introduction)
- [Getting started](https://developers.avayacloud.com/avaya-infinity/docs/quick-start)
- [API reference](https://developers.avayacloud.com/avaya-infinity/reference)
- [Sign up](https://developers.avayacloud.com/avaya-infinity/docs/obtaining-a-client-id-and-secret-from-avaya)
- [Support](https://support.avaya.com/support/en/public)
- [Blog](https://www.avaya.com/en/blogs/)
- [Security](https://support.avaya.com/css/public/documents/100045520)
- [Compliance](https://www.avaya.com/en/trust-center/compliance/)
- [Terms of service](https://www.avaya.com/en/legal/)
- [Privacy policy](https://www.avaya.com/en/privacy/commitment/)
- [GitHub](https://github.com/avaya)
- [Status](https://status.avayacloud.com/)

## API Evangelist rating

**Kin Score 52.5** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 65.3 |
| Contract governance | 18.2 |
| Operational transparency | 36.8 |
| Developer ergonomics | 37.5 |
| Access clarity | 47.4 |

**Agent readiness 40.0** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 41.8** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/avaya/](https://apis.io/providers/avaya/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Avaya: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/avaya/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
