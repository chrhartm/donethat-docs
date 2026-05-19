---
title: Project (legacy)
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

- **`list`** — returns your projects. Optional `archived: true` includes archived projects; `false` or omitted returns only active ones. Merge is not supported on this endpoint.
- **`create`** — `name` is required. Other fields are optional.
- **`update`** — `id` is required. Omit any field to leave it unchanged; pass `null` or `""` to clear a string field.
- **`delete`** — `id` is required.
- **`archive`** — `id` is required. Optional `archived` defaults to `true`; pass `false` to unarchive. (Same parameter name as on `list`, but different meaning.)

### Common fields

- `id` — required for `update`, `delete`, `archive`. Use a project id from a `list` response.
- `name` — required for `create`.
- `description` — free-form string.
- `private`, `confidential` — booleans.
- `team`, `portfolio` — optional. Pass either an id, or an exact display name (trimmed, case-sensitive) for a team you belong to or a portfolio you can use. On `update`, omit to leave unchanged; `null` or `""` clears.
- No top-level `status` field.

### Allowed `color` values

When set, `color` must be exactly one of the following hex strings — no other values are accepted:

`#FFB623`, `#FF8A65`, `#F4511E`, `#E53935`, `#D81B60`, `#8E24AA`, `#5E35B1`, `#3949AB`, `#1E88E5`, `#039BE5`, `#00ACC1`, `#00897B`, `#43A047`, `#7CB342`, `#C0CA33`, `#FDD835`, `#FB8C00`, `#6D4C41`, `#757575`, `#546E7A`.

The exact palette is exposed in the app — copy it from there if you need a programmatic source.

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
