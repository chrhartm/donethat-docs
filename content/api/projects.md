---
title: Projects
category: api
order: 4
lastUpdated: '2026-05-19'
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
| `GET /projects` | `projects:read` |
| `GET /projects/:id` | `projects:read` |
| `POST /projects` | `projects:write` |
| `POST /projects/:id` | `projects:write` (empty-body read also needs `projects:read`) |
| `DELETE /projects/:id` | `projects:write` |

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
  "status": "active",
  "createdAt": "2026-05-19T09:00:00.000Z",
  "updatedAt": "2026-05-19T09:10:00.000Z",
  "usedAt": "2026-05-19T09:10:00.000Z",
  "createdBy": "user_123",
  "updatedBy": "user_123"
}
```

Timestamp fields are ISO 8601 UTC strings or `null`.

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
  "confidential": false
}
```

`name` is optional. If omitted or blank, DoneThat creates a name like `New Project 2026-05-19`.

`team` and `portfolio` accept either an id or an exact display name you can access. Names are matched **case-sensitively** after trimming. Pass `null` or an empty string to clear those fields on update.

### Field rules

| Field | Rules |
| :--- | :--- |
| `name` | Optional on create (auto-generated if omitted). Max **100** characters when set. |
| `description` | Optional. Max **2000** characters. |
| `color` | Optional. If set, must be exactly one of the allowed hex values below (same palette as in the app). Invalid values return `{ "success": false, "error": "Invalid color value" }`. |
| `team`, `portfolio` | Optional. Id or exact display name you can access; case-sensitive. |
| `private` | Optional boolean. |
| `confidential` | Optional boolean on **create** only. Cannot be changed on update through this API. |
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
  "archived": true
}
```

Notes:

- `archived: true` archives the project; `archived: false` unarchives it.
- An empty body returns the current project without changing it, and requires **`projects:read`** in addition to `projects:write`.
- `team` and `portfolio` can be cleared with `null` or an empty string.
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
