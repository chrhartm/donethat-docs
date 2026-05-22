# Agents Guide

Build logic and structure for the DoneThat documentation repository.

## Git and commits (agents)

**NEVER commit, push, or amend git history in this repo unless the user explicitly asks you to in that message.**

This includes:

- Do **not** run `npm run deploy-docs` without `SKIP_GIT=1` (that script commits and may push by default).
- Do **not** run `git commit`, `git push`, `git add` for the purpose of committing, or `git commit --amend`.
- Do **not** assume deploy, sync, or "ship it" means commit. Only the user commits unless they say otherwise.

When you need regenerated schema or metadata, run:

```bash
SKIP_GIT=1 npm run deploy-docs
```

Leave all changes unstaged or staged only if the user asked you to prepare a commit. The user commits and pushes.

## Website docs submodule

**NEVER edit `donethat-website/docs/` directly.** That directory is a git submodule checkout of this repo, not a second source of truth.

After the user pushes changes here, they (or you, only when asked) update the website with:

```bash
cd ../donethat-website && npm run docs:sync
```

Do not copy files into the submodule by hand.

## Directory Structure

- **`content/`** - Source of truth (atomic markdown files)
  - `content/guides/` - Feature documentation
  - `content/knowledge-base/` - Knowledge-base articles and interactive guide source
  - `content/faq/` - Q&A files
  - `content/use-cases/<domain>/` - Outcome-first use case documentation grouped by domain
  - `content/mcp/` - MCP connector documentation (rendered at `/mcp` on the website)
  - `content/api/` - HTTP API reference (rendered at `/api-reference` on the website)
- **`schema/terminology.json`** - Domain, stage, and outcome registry for use cases
- **`schema/structure.json`** - Auto-generated registry for category nav plus use-case filters
- **`metadata.json`** - Global app metadata

## File Format

Every Markdown file in `content/` has YAML frontmatter:

```yaml
---
title: "Page Title"
category: "use-cases"
lastUpdated: "2025-01-20"
tags: ["tag1", "tag2"]
summary: "Brief description"  # Non-use-cases only
domain: "it"  # Use-cases only
stage: "select"  # Use-cases only
outcome: ["quality", "speed"]  # Use-cases only: cost, quality, speed
---
```

For use-cases, do not put the description in frontmatter. The first body paragraph is the page description and is copied into `schema/structure.json` as the generated summary.

## Schema Generation

The `schema/structure.json` file is **auto-generated** by `scripts/deploy-docs.cjs`:

- Scans all `content/**/*.md` files
- Extracts `category` from frontmatter
- Maps `category` → navigation groups
- Uses file basename (without `.md`) as slug in `files` array
- Copies `domains` from `schema/terminology.json`
- Copies `outcomes` from `schema/terminology.json`
- Builds a `useCases` index from use-case frontmatter
- Validates every use-case `domain`, `stage`, and `outcome` against `schema/terminology.json`
- Sorts categories and files alphabetically

**Do not manually edit `structure.json`** - it's regenerated on deploy.

## Deploy Script

Run `npm run deploy-docs` to:
1. Regenerate `schema/structure.json` from content
2. Update `metadata.json.lastUpdated` to today's date
3. Commit and push changes (human workflow only)

**Agents:** use `SKIP_GIT=1 npm run deploy-docs` so step 3 is skipped. Never commit for the user.

## Parsing Files

- Use `gray-matter` (or equivalent) to parse frontmatter + body
- Frontmatter is YAML between `---` delimiters
- Body is markdown after the closing `---`

## Writing Style

- Never use em-dashes (U+2014) in docs.
- Use a normal hyphen (`-`) or rewrite the sentence instead.

## MCP documentation

When MCP tools, OAuth scopes, or connection details change in the Firebase backend (`donethat-firebase`), manually update [`content/mcp/overview.md`](content/mcp/overview.md) and run `SKIP_GIT=1 npm run deploy-docs`. The user pushes this repo, then runs `npm run docs:sync` in `donethat-website`.
