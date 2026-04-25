# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an Obsidian-based personal knowledge base built on Andrej Karpathy's LLM Wiki methodology. It is a Markdown-based system, not a traditional software project. There are no build tools, package managers, or test suites. Operations are content workflows triggered by natural language commands.

## Repository Architecture

### Three-Layer System

| Layer | Directory | Owner | Rule |
|---|---|---|---|
| **L1 Raw** | `raw/` | Human writes / LLM reads only | Humans drop source material; LLM must never modify |
| **L2 Wiki** | `wiki/` | LLM writes and maintains / Human reads only | LLM-generated structured Markdown |
| **L3 Schema** | `CLAUDE.md` | Human-LLM co-evolution | Operational blueprint read at session start |

The `wiki/` directory contains:
- `index.md` — master directory of all wiki content
- `log.md` — append-only activity log with timestamps
- `hot.md` — ephemeral working memory (current focus, open questions, recent decisions)
- `overview.md` — high-level vault status and cluster map
- `sources/` — source summaries (one per ingested raw file)
- `concepts/` — ideas, methods, technologies, theories
- `entities/` — people, companies, products, organizations
- `comparisons/` — analytical comparisons across sources
- `syntheses/` — integrated analyses combining multiple concepts

`VAULT-INDEX.md` and `Base-INDEX.md` are human-facing dashboards. `VAULT-INDEX.md` is the primary one.

## Workflow Commands

These are the three operations Claude performs in this repo. They are triggered by the user saying the keyword, not by running shell commands.

### 1. Ingest (`ingest raw/<path>`)

Triggered when the user says `ingest raw/xxx.md`.

Steps:
1. Read the raw file from `raw/`.
2. Create or update the source summary at `wiki/sources/summary-{slug}.md`.
3. Update or create relevant concept pages in `wiki/concepts/` and entity pages in `wiki/entities/`.
4. Mark contradictions if found.
5. Append an entry to `wiki/log.md` with timestamp.
6. Update `wiki/hot.md` if the focus has shifted.
7. **After ingest, commit all changes to Git.** This is mandatory.

A single ingest should touch 5–15 wiki pages.

### 2. Query (direct questions)

Triggered by any direct question.

Steps:
1. Read `wiki/index.md` first to understand the vault structure.
2. Locate relevant pages.
3. Answer with `[[wiki-link]]` citations.
4. If the analysis is valuable and durable, archive it as a new page under `wiki/comparisons/` or `wiki/syntheses/`.

Do not query prematurely — wait until approximately 10 sources have been ingested.

### 3. Lint (`lint` or `health check`)

Triggered when the user says `lint` or `health check`.

Checks:
- Contradictions between pages
- Orphan pages (zero incoming links)
- Missing pages (red links)
- Stale claims (outdated information)
- Cluster health
- Backlink integrity

## Content Standards

### Naming
- Directories: lowercase, kebab-case
- Source summaries: `wiki/sources/summary-{slug}.md`
- Concepts: `wiki/concepts/{Name}.md`
- Entities: `wiki/entities/{Name}.md`

### Links
Use **Obsidian Wikilink syntax** `[[Note Title]]` exclusively. Standard Markdown links `[text](url)` are forbidden for internal links.

### YAML Frontmatter (required on all wiki pages)
```yaml
---
type: source | concept | entity | comparison | synthesis
title: "页面标题"
created: YYYY-MM-DD
updated: YYYY-MM-DD
related: [[页面1]], [[页面2]]
confidence: high | medium | low
---
```

Concept pages may also include `aliases`, `defined_by`, `first_seen`, `sources`, and `status` fields.

### Golden Rules
1. **Humans write `raw/`, LLM writes `wiki/`** — never edit raw files.
2. **No AI diaries or generated "thinking"** in this repository.
3. **Commit to Git after every ingest.**
4. **Single-writer rule** — only one agent writes to `wiki/` at a time.
