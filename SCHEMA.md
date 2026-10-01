# SCHEMA.md — Agentic OS Shared Brain (v1)

Canonical operating specification for this shared brain. **Any agent (Claude Code,
Codex, or other) MUST read this file before creating, modifying, moving, or
deleting anything here.**

This directory is simultaneously a DSH workspace, an Obsidian vault, and the shared
filesystem for multiple coding agents. It is deliberately **tool-independent**:
plain Markdown and folders only — no databases, vector stores, plugins, or external
services. Keep it that way until the owner decides otherwise.

---

## Directory model

| Path | Role | Mutability |
| --- | --- | --- |
| `inbox/` | Transient, unprocessed capture. Not canonical. | Triaged into `raw/` or discarded (discard only with human approval). |
| `raw/` | Immutable source material. | **Read-only to agents.** Never silently rewrite or delete. |
| `raw/assets/` | Binary / non-text source assets (images, PDFs, audio). | Same as `raw/`. |
| `wiki/` | Compiled, agent-maintained knowledge base. | Humans read; agents maintain. |
| `wiki/index.md` | First navigation point for agents (links + 1-line descriptions). | Keep current. |
| `wiki/overview.md` | High-level map of what the brain currently covers. | Update when coverage changes materially. |
| `wiki/log.md` | Append-only ledger of knowledge operations. | Append only; never rewrite history. |
| `wiki/sources/` | One provenance + summary page per ingested source. | Agent-maintained. |
| `wiki/topics/` | Concept pages. | Agent-maintained. |
| `wiki/entities/` | People, organizations, products, systems. | Agent-maintained. |
| `wiki/projects/` | Project pages. | Agent-maintained. |
| `wiki/decisions/` | Decisions and their rationale. | Agent-maintained. |
| `wiki/patterns/` | Reusable patterns / playbooks. | Agent-maintained. |
| `outputs/` | Generated artifacts (drafts, reports). **Not** automatically canonical knowledge. | Agent-writable. |
| `ops/runs/` | Concise summaries of significant agent runs, for future learning. **Never full transcripts.** | Append new files. |
| `ops/feedback/` | Explicit human corrections / feedback. | Append new files. |
| `ops/evals/` | Regression examples and rubrics to verify agent/skill/routing/memory improvements (future). | Grows over time. |

---

## Core principles

1. **`raw/` is immutable.** Agents may read it but must never silently rewrite or
   delete it. Any change to `raw/` requires explicit human approval.
2. **`inbox/` is transient.** It holds unprocessed capture. Content should
   eventually be moved into `raw/` (if it is source material worth keeping) or
   discarded — discard only with human approval.
3. **`wiki/` is compiled knowledge maintained by agents.** Humans primarily read
   it; agents keep it accurate and linked.
4. **Provenance.** Every non-trivial wiki claim should preserve a link back to its
   source material (via a `wiki/sources/` page that points into `raw/`) wherever
   reasonably possible. If a claim has no source, say so explicitly.
5. **Progressive disclosure.** Start from `wiki/index.md`. Load only the pages you
   need; do not read the whole wiki.
6. **Tool independence.** Markdown + relative links only. No dependency on any
   specific app, plugin, database, or service.
7. **Append-only log.** `wiki/log.md` records knowledge operations and is never
   rewritten.
8. **No invention.** Do not fabricate knowledge, taxonomy, or provenance. Do not
   pre-populate the wiki with placeholder facts. Grow the structure only when real
   content demands it.

---

## Conventions

- **Links:** prefer relative Markdown links (`[overview](overview.md)`) so they work
  in Obsidian, plain renderers, and the terminal. Obsidian `[[wikilinks]]` are also
  acceptable. Keep links unbroken.
- **Filenames:** `kebab-case`, descriptive.
- **Dates:** ISO 8601 (`YYYY-MM-DD`).
- **A `wiki/sources/` page records:** origin/title, date ingested, location in
  `raw/`, a short summary, and which wiki pages derive from it.
- **Cross-linking:** source pages link to the pages they support; derived pages link
  back to their sources and to related pages.

---

## Operations

### INGEST — fold new source material into the brain, with provenance

1. Place or confirm the source in `raw/` (text) or `raw/assets/` (binary). If it
   came from `inbox/`, move it into `raw/` first (never leave canonical source in
   `inbox/`).
2. Inspect `wiki/index.md` and related wiki pages to see what already exists.
3. Create or update the source's page in `wiki/sources/` (origin, `raw/` location,
   summary, provenance).
4. Create or update the relevant `topics/` / `entities/` / `projects/` /
   `decisions/` / `patterns/` pages with claims drawn from the source.
5. Add cross-links between the source page and the pages it supports, and between
   related pages.
6. Update `wiki/index.md` (and `wiki/overview.md` if coverage changed materially).
7. Append an `INGEST` entry to `wiki/log.md`.

Never modify `raw/` content during ingest — only read it.

### QUERY — answer using the brain, with provenance

1. Read `wiki/index.md` first.
2. Locate the relevant pages; follow links as needed.
3. Consult `raw/` sources directly when verification is necessary.
4. Answer **with provenance** (cite the source / wiki pages used).
5. Only file genuinely reusable, verified knowledge back into the wiki — and log it.
   Do **not** dump one-off answers or transient results into the wiki.

### LINT — keep the brain healthy

Scan for, report, and (with human approval) fix:

- stale or conflicting claims,
- broken links and orphan pages,
- missing provenance on non-trivial claims,
- duplicated concepts that should be merged,
- missing important pages,
- index drift (`wiki/index.md` out of sync with the actual pages).

Append a `LINT` entry to `wiki/log.md` summarizing findings.

---

## Log format (`wiki/log.md`)

Append entries newest-at-the-bottom. One entry per operation:

```
## YYYY-MM-DD — <OP>
<one or two line summary>. Refs: <links to pages / raw sources>.
```

Where `<OP>` ∈ `{ INGEST, QUERY, LINT, INIT }`. Only meaningful QUERY results that
were filed back into the wiki warrant a log entry.

---

## Change discipline

- "Modifying the brain" = changing `wiki/`, the index, the logs, or the structure.
  Read this file first.
- Destructive changes to `raw/`, or deletions anywhere, require explicit human
  approval.
- `ops/runs/` gets concise run summaries, not transcripts. `ops/feedback/` gets
  explicit human corrections. These are operational records, not knowledge.
- Keep v1 minimal. No PARA folders, no large taxonomy, no templates, no automation
  until the owner asks.
