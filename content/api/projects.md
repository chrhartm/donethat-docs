---
title: Projects
category: api
order: 4
lastUpdated: '2026-05-19'
summary: >-
  List, read, create, update, archive, and delete DoneThat projects through the
  REST API.
method: GET / POST / DELETE
path: /projects
scopes:
  - 'projects:read'
  - 'projects:write'
tags:
  - api
  - projects
---

The projects endpoint is the current REST-style API for managing DoneThat projects.

```
GET    https://api.donethat.ai/projects
GET    https://api.donethat.ai/projects/:id
POST   https://api.donethat.ai/projects
POST   https://api.donethat.ai/projects/:id
DELETE https://api.donethat.ai/projects/:id
```

## Authentication

Pass your API key in the `x-api-key` header.

| Route | Required scope |
| :--- | :--- |
| `GET /projects` | `projects:read` |
| `GET /projects/:id` | `projects:read` |
| `POST /projects` | `projects:write` |
| `POST /projects/:id` | `projects:write` |
| `DELETE /projects/:id` | `projects:write` |

## Project object

```json
{
  "id": "project_123",
  "name": "Customer onboarding",
  "description": "Implementation work for new customers",
  "color": "#1E88E5",
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
[
  {
    "id": "project_123",
    "name": "Customer onboarding",
    "description": null,
    "color": "#1E88E5",
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
```

## Read one project

```
GET /projects/:id
```

Returns one project object. The API only returns projects owned by you or accessible through an active team membership.

## Create a project

```
POST /projects
```

Request body:

```json
{
  "name": "Customer onboarding",
  "description": "Implementation work for new customers",
  "color": "#1E88E5",
  "team": "team_123_or_exact_team_name",
  "portfolio": "portfolio_123_or_exact_portfolio_name",
  "private": false,
  "confidential": false
}
```

`name` is optional. If omitted or blank, DoneThat creates a name like `New Project 2026-05-19`.

`team` and `portfolio` accept either an id or an exact display name you can access. Pass `null` or an empty string to clear those fields on update.

The response status is `201` and the body is the created project object.

## Update or archive a project

```
POST /projects/:id
```

Send any subset of editable fields:

```json
{
  "name": "Customer onboarding v2",
  "description": "",
  "color": "#43A047",
  "team": null,
  "portfolio": null,
  "private": true,
  "confidential": false,
  "archived": true
}
```

Notes:

- `archived: true` archives the project; `archived: false` unarchives it.
- An empty body performs an access-checked read of the current project.
- `team` and `portfolio` can be cleared with `null` or an empty string.
- Omit a field to leave it unchanged.

The response is the updated project object.

## Delete a project

```
DELETE /projects/:id
```

Response:

```json
{
  "id": "project_123",
  "deleted": true
}
```

## Example

```bash
curl -X POST "https://api.donethat.ai/projects" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{
       "name": "Customer onboarding",
       "color": "#1E88E5"
     }'
```

## Errors

This endpoint returns bare error objects:

```json
{
  "error": "API key missing required scope: projects:read"
}
```
