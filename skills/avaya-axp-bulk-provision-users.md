---
name: Bulk-provision Avaya Experience Platform users as an async job
description: Submit a bulk user add or update on AXP, poll the resulting job to completion, export the failures, and stop a job that is going wrong.
api: openapi/avaya-axp-admin-user-openapi.yml
operations: [downloadBulkTemplate, bulkAddUsers, bulkUpdateUsers, listJobs, getJob, listUsersByJob, exportFailedUsers, downloadExportedUsers, stopJob, searchUsers]
generated: '2026-09-14'
method: generated
source: derived from openapi/avaya-axp-admin-user-openapi.yml and conventions/avaya-conventions.yml
---

# Bulk-provision Avaya Experience Platform users

Base: `https://{region}.api.avayacloud.com` — `na`, `eu`, `uk`, `ca`, `ap`, `au` or `sa`. Every path
is rooted at `/accounts/{accountId}`; acquire the account id per
<https://developers.avayacloud.com/avaya-experience-platform/docs/how-to-acquire-axp-account-id>.

Send **both** credentials on every call: `Authorization: Bearer <jwt>` **and** the tenant
`appkey` header.

## Step 1 — get the template (`downloadBulkTemplate`)

`GET /accounts/{accountId}/users-bulk-template` returns the CSV shape AXP expects. Build your payload
from this rather than guessing columns.

## Step 2 — submit the job (`bulkAddUsers` / `bulkUpdateUsers`)

`POST /accounts/{accountId}/users:bulkAdd` or `:bulkUpdate`.

These return **202 Accepted** with a job id. Nothing has been written yet.

> **There is no idempotency key on this operation.** If the request times out, do **not** resubmit.
> Call `listJobs` (`GET /accounts/{accountId}/jobs`) and look for a job you already created. A blind
> retry provisions the whole batch twice.

## Step 3 — poll the job (`getJob`, `listUsersByJob`)

- `GET /accounts/{accountId}/jobs/{jobId}` — job status
- `GET /accounts/{accountId}/jobs/{jobId}/users` — the users the job touched

Poll on a backoff. A `207 Multi-Status` response means the batch partly succeeded.

## Step 4 — stop a job that is going wrong (`stopJob`)

`POST /accounts/{accountId}/jobs/{jobId}:stop`

This is one of only two reversal paths Avaya publishes anywhere, and it works **only while the job is
still running**. Avaya states no window. Once the job completes there is no undo: deleting the users
it created is a fresh destructive call, and `deleteUser` has no restore path.

## Step 5 — collect the failures

- `GET /accounts/{accountId}/jobs/{jobId}:exportFailedUsers`
- `GET /accounts/{accountId}/jobs/{jobId}:downloadExportedUsers`

Reconcile with `searchUsers` (`POST /accounts/{accountId}/users:search`) before re-running anything.

## Rules

- **Never call `bulkDeleteUsers` to clean up a mistake without a verified export first.** There are 33
  DELETE operations in the AXP contract and not one has a documented restore or retention window.
- Errors are RFC 7807-shaped (`type`, `title`, `status`, `detail`); `403` means the token is valid but
  lacks entitlement on this account or resource partition.
