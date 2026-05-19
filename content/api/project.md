---
title: Project (deprecated)
category: api
order: 6
lastUpdated: '2026-05-19'
summary: >-
  Deprecated operation-based project endpoint retained for existing
  integrations.
method: POST
path: /project
scopes:
  - 'projects:write'
deprecated: true
tags:
  - api
  - projects
  - deprecated
---

> **Deprecated.** This endpoint is retained for existing integrations. Use the REST-style [`/projects`](/api-reference/projects) endpoint for new integrations.

The projects endpoint lets you list, create, update, archive, and delete projects from outside the app.

```
POST https://api.donethat.ai/project
```

**Required scope:** `projects:write`

## Request body

The body is JSON. The shape depends on `operation`.

An **empty JSON body** (`{}`) defaults to `{ "operation": "list" }` (active projects only).

```json
{
  "operation": "list" | "create" | "update" | "delete" | "archive",
  "id": "...",
  "name": "...",
  "description": "...",
  "color": "#FFB623",
  "team": "abcTeamIdOrExactName",
  "portfolio": "xyzPortfolioIdOrExactName",
  "private": false,
  "confidential": false,
  "archived": false
}
```

### Operations

- **`list`**: returns your projects. Optional `archived: true` includes archived projects; `false` or omitted returns only active ones.
- **`create`**: `name` is required. Other fields are optional.
- **`update`**: `id` is required. Omit any field to leave it unchanged; pass `null` or `""` to clear a string field.
- **`delete`**: not supported via the API (returns an error). Use **`archive`** instead.
- **`archive`**: `id` is required. Optional `archived` defaults to `true`; pass `false` to unarchive. (On `list`, `archived` filters which projects are returned.)

### Common fields

- `id` - required for `update`, `delete`, `archive`. Use a project id from a `list` response.
- `name` - required for `create`.
- `description` - free-form string.
- `private`, `confidential` - booleans.
- `team`, `portfolio` - optional. Pass either an id, or an exact display name (trimmed, case-sensitive) for a team you belong to or a portfolio you can use. On `update`, omit to leave unchanged; `null` or `""` clears.
- No top-level `status` field.

### Allowed `color` values

When set, `color` must be exactly one of the following hex strings (same palette as [`/projects`](/api-reference/projects)):

`#FFB623`, `#4BC0C0`, `#6C63FF`, `#FF4590`, `#32D74B`, `#FFD166`, `#845EC2`, `#00C2FF`, `#FF6B6B`, `#00B8A9`, `#FF9F1C`, `#F9F871`, `#EF5DA8`, `#4ECDC4`, `#00BBF9`, `#FF9671`, `#FCBAD3`, `#A6E3E9`, `#FFCB77`, `#D65DB1`

Other limits: `name` and `color` strings are capped at **100** characters; `description` at **2000** characters.

## Responses

| Operation | Success shape |
| :--- | :--- |
| `list` | `{ "success": true, "projects": [ ... ] }` |
| `create`, `update` | `{ "success": true, "message"?: string, "projectId"?: string }` |
| `delete`, `archive` | `{ "success": true, "message"?: string }` |

Failures return `{ "success": false, "error": "..." }` with HTTP 4xx.

## Examples

List active projects:

```json
{
  "operation": "list"
}
```

List including archived:

```json
{
  "operation": "list",
  "archived": true
}
```

Create:

```json
{
  "operation": "create",
  "name": "My project",
  "description": "...",
  "color": "#FFB623",
  "team": "abcTeamIdOrExactName",
  "portfolio": "xyzPortfolioIdOrExactName"
}
```
