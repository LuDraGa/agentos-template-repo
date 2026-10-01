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
| `ops/evals/` | Lightweight regression examples and rubrics for agent/skill/routing/memory improvements. | Grows over time. |
| `.agents/skills/` | Shared reusable instructions; one `SKILL.md` per skill. Thin adapters defer to this specification. | Changes require user approval. |

---

## Canonical system definitions

- **Tool:** a primitive executable action.
- **Skill:** reusable instructions and knowledge for performing one responsibility well.
- **Workflow:** orchestration of multiple steps, tools, skills, or agents.
- **Capability:** a user-facing ability composed from tools, skills, workflows, and/or agents.
- **Agent:** an executor with a particular model, context, tools, and role.

## Knowledge promotion rule

Normal work and research are **transient by default**: use information to complete the
current task first, then decide whether it merits durable storage. This applies to
“research X,” “help me understand X,” “compare X and Y,” and “work through this project.”
The user need not normally ask to ingest material.

Promote a result into the brain only when it is clearly reusable beyond the immediate
task, relevant to an ongoing project, goal, domain, or recurring activity, sufficiently
supported and provenanced, and useful enough to justify future retrieval. If uncertain,
do not persist it. Explicit instructions override this rule: “remember” / “preserve this”
means persist when safe and appropriate; “keep this transient” means do not persist.

User-provided source files normally enter the `raw/` and provenance path. When durable
web research is justified, preserve source identity, URL, date, and useful provenance;
create a local raw snapshot only when useful and appropriate. Do not save routine,
disposable research indiscriminately.

Promotion does not waive approval boundaries: any addition to `raw/` still requires
explicit approval; a direct request to ingest/preserve a named source authorizes its
addition, not overwriting or deleting existing material. If approval is absent, ask
before adding it. Qualifying web findings may use a source page with the original URL
and dates instead of a local snapshot. Reuse existing source/knowledge pages; a
no-change repeat should not create duplicate pages or an INGEST/QUERY log entry.
Record meaningful promotions through the canonical operations below.

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
   source material via a `wiki/sources/` page pointing into `raw/`, or to the original
   web source when no snapshot is warranted, wherever reasonably possible. If a
   claim has no source, say so explicitly.
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
  `raw/` (if retained), a short summary, and which wiki pages derive from it. For web
  sources include the original URL, accessed date, and publication/update date when
  available; if no snapshot is kept, state that explicitly.
- **Cross-linking:** source pages link to the pages they support; derived pages link
  back to their sources and to related pages.

---

## Operations

### INGEST — fold new source material into the brain, with provenance

1. Confirm the source in `raw/` (text) or `raw/assets/` (binary), or obtain approval
   before placing it there. If it came from `inbox/`, obtain approval to move it into
   `raw/` first (never leave canonical source in `inbox/`). For web findings, apply
   the knowledge-promotion rule: an identified original URL may suffice without a
   local snapshot.
2. Inspect `wiki/index.md` and related wiki pages to see what already exists.
3. Create or update the source's page in `wiki/sources/` (origin, source location,
   summary, provenance per the conventions above).
4. Create or update the relevant `topics/` / `entities/` / `projects/` /
   `decisions/` / `patterns/` pages with claims drawn from the source.
5. Add cross-links between the source page and the pages it supports, and between
   related pages.
6. Update `wiki/index.md` (and `wiki/overview.md` if coverage changed materially).
7. Append an `INGEST` entry to `wiki/log.md`.

Once a source is stored in `raw/`, ingest only reads it; never rewrite its content.

### QUERY — answer using the brain, with provenance

1. Read `wiki/index.md` first.
2. Locate the relevant pages; follow links as needed.
3. Consult `raw/` sources directly when verification is necessary.
4. Answer **with provenance** (cite the source / wiki pages used).
5. Apply the knowledge-promotion rule before filing knowledge back into the wiki;
   keep index/overview current and log meaningful changes. For project state based
   on direct user decisions, identify them as user-provided (with date/context),
   separate open questions from agreed facts, and use a QUERY entry. New external
   sources follow INGEST. Do **not** dump one-off answers or transient results into
   the wiki.

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
