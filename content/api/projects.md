---
title: Projects
category: api
order: 4
lastUpdated: '2026-08-07'
summary: >-
  List, read, create, update, and archive DoneThat projects through the REST
  API.
method: GET / POST / DELETE
path: /projects
scopes:
  - 'projects:read'
  - 'projects:write'
tags:
  - api
  - projects
---

The projects endpoint lets you list, read, create, update, and archive DoneThat projects.

```
GET    https://api.donethat.ai/projects
GET    https://api.donethat.ai/projects/:id
POST   https://api.donethat.ai/projects
POST   https://api.donethat.ai/projects/:id
DELETE https://api.donethat.ai/projects/:id
```

Updates use `POST` (not `PATCH` or `PUT`). Unsupported methods return `405` with `{ "success": false, "error": "Method Not Allowed" }`.

## Authentication

Pass your API key in the `x-api-key` header.

| Route | Required scope |
| :--- | :--- |
| `GET /projects` | `projects:read` (or `projects:write`) |
| `GET /projects/:id` | `projects:read` (or `projects:write`) |
| `POST /projects` | `projects:write` |
| `POST /projects/:id` | `projects:write` |
| `DELETE /projects/:id` | `projects:write` |

Keys with `projects:write` may call all `/projects` routes above. Use `projects:read` alone for read-only integrations.

## Project object

Returned as `project` (single) or in the `projects` array (list):

```json
{
  "id": "project_123",
  "name": "Customer onboarding",
  "description": "Implementation work for new customers",
  "color": "#FFB623",
  "portfolioId": null,
  "teamId": "team_123",
  "private": false,
  "confidential": false,
  "contributorIds": null,
  "status": "active",
  "createdAt": "2026-05-19T09:00:00.000Z",
  "updatedAt": "2026-05-19T09:10:00.000Z",
  "usedAt": "2026-05-19T09:10:00.000Z",
  "createdBy": "user_123",
  "updatedBy": "user_123"
}
```

Timestamp fields are ISO 8601 UTC strings or `null`.

`contributorIds` limits **who can log time** to a team project. `null`, which is the default, means every member of the team can log time to it. An empty array means nobody can; a non-empty array allows only those users.

It never affects visibility: the whole team still sees the project in listings, reports, and goals either way.

Responses always return `contributorIds` as user ids or `null`. Writes additionally accept handles and email addresses (see [Field rules](#field-rules)).

## List projects

```
GET /projects
```

Query parameters:

| Parameter | Type | Default | Notes |
| :--- | :--- | :--- | :--- |
| `sort` | string | `createdAt` | Sort key, descending. One of `createdAt`, `updatedAt`, `usedAt`. |
| `includeArchived` | boolean | `false` | Pass `true` to include archived projects. |

Response:

```json
{
  "success": true,
  "projects": [
    {
      "id": "project_123",
      "name": "Customer onboarding",
      "description": null,
      "color": "#FFB623",
      "portfolioId": null,
      "teamId": null,
      "private": false,
      "confidential": false,
      "contributorIds": null,
      "status": "active",
      "createdAt": "2026-05-19T09:00:00.000Z",
      "updatedAt": "2026-05-19T09:00:00.000Z",
      "usedAt": "2026-05-19T09:00:00.000Z",
      "createdBy": "user_123",
      "updatedBy": "user_123"
    }
  ]
}
```

## Read one project

```
GET /projects/:id
```

Returns `{ "success": true, "project": { ... } }`. The API only returns projects owned by you or accessible through an active team membership.

## Create a project

```
POST /projects
```

Request body:

```json
{
  "name": "Customer onboarding",
  "description": "Implementation work for new customers",
  "color": "#FFB623",
  "team": "team_123_or_exact_team_name",
  "portfolio": "portfolio_123_or_exact_portfolio_name",
  "private": false,
  "confidential": false,
  "contributorIds": ["christoph", "ana@example.com"]
}
```

`name` is optional. If omitted or blank, DoneThat creates a name like `New Project 2026-05-19`.

`team` and `portfolio` accept either an id or an exact display name you can access. Names are matched **case-sensitively** after trimming. Pass `null` or an empty string to clear those fields on update.

`contributorIds` accepts `null`, or user ids, handles, or email addresses in any mix; each entry is resolved to a user id in the response. Every entry must resolve to an active member of the project's team. Pass `null` to let the whole team log time, or `[]` to let nobody log time.

### Field rules

| Field | Rules |
| :--- | :--- |
| `name` | Optional on create (auto-generated if omitted). Max **100** characters when set. |
| `description` | Optional. Max **2000** characters. |
| `color` | Optional. If set, must be exactly one of the allowed hex values below (same palette as in the app). Invalid values return `{ "success": false, "error": "Invalid color value" }`. |
| `team`, `portfolio` | Optional. Id or exact display name you can access; case-sensitive. |
| `private` | Optional boolean. |
| `confidential` | Optional boolean on **create** only. Cannot be changed on update through this API. |
| `contributorIds` | Optional `null` or array of user ids, handles, or email addresses. Only valid on **team** projects. Every entry must be an active member of that team. `null` permits everyone; `[]` permits nobody; omit to leave unchanged. Set to `null` automatically if the project moves to a different team or to personal scope. |
| `archived` | Only on `POST /projects/:id`. `true` archives, `false` unarchives. |

### Allowed `color` values

When provided, `color` must be exactly one of:

`#FFB623`, `#4BC0C0`, `#6C63FF`, `#FF4590`, `#32D74B`, `#FFD166`, `#845EC2`, `#00C2FF`, `#FF6B6B`, `#00B8A9`, `#FF9F1C`, `#F9F871`, `#EF5DA8`, `#4ECDC4`, `#00BBF9`, `#FF9671`, `#FCBAD3`, `#A6E3E9`, `#FFCB77`, `#D65DB1`

Response status `201`:

```json
{
  "success": true,
  "project": {
    "id": "project_123",
    "name": "Customer onboarding",
    "status": "active"
  }
}
```

(Other fields match the [Project object](#project-object) above.)

## Update or archive a project

```
POST /projects/:id
```

Send any subset of editable fields:

```json
{
  "name": "Customer onboarding v2",
  "description": "",
  "color": "#32D74B",
  "team": null,
  "portfolio": null,
  "private": true,
  "contributorIds": ["christoph", "ana@example.com"],
  "archived": true
}
```

Notes:

- `archived: true` archives the project; `archived: false` unarchives it.
- An empty body returns the current project without changing it (requires `projects:write`, which includes read access).
- `team` and `portfolio` can be cleared with `null` or an empty string.
- `contributorIds` replaces the whole list; send `null` to let the whole team log time, or `[]` to let nobody log time.
- Changing `team` without also sending `contributorIds` sets it to `null`, because the previous contributors may not belong to the new team.
- `confidential` cannot be changed through this API.
- Omit a field to leave it unchanged.

Response: `{ "success": true, "project": { ... } }`.

## Delete a project

```
DELETE /projects/:id
```

**Not supported.** The API returns `403`:

```json
{
  "success": false,
  "error": "Deleting projects is not available through the API."
}
```

Use `archived: true` on `POST /projects/:id` to archive instead.

## Example

```bash
curl -X POST "https://api.donethat.ai/projects" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{
       "name": "Customer onboarding",
       "color": "#FFB623"
     }'
```

## Errors

```json
{
  "success": false,
  "error": "API key missing required scope: projects:read"
}
```

Validation failures return `400` with a message naming the offending value:

| Error | Cause |
| :--- | :--- |
| `No user matches "<entry>"; use a user id, handle, or email address` | A `contributorIds` entry matched no DoneThat account. |
| `Contributor <userId> is not an active member of the team` | The user exists but isn't on the project's team. |
| `Contributors can only be set on team projects` | `contributorIds` was sent for a personal project. |
| `contributorIds must be null or an array of user ids, handles, or email addresses` | The field was neither `null` nor an array. |
