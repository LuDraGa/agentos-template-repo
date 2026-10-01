# 🏠 Home — Agentic OS Shared Brain

This vault is the shared brain for my personal Agentic OS. It is plain Markdown —
readable anywhere, owned by me, and not tied to any single tool.

## Where things live

- **[wiki/](wiki/index.md)** — the compiled knowledge base. Start at the
  [wiki index](wiki/index.md). Humans read this; agents maintain it.
- **raw/** — original source material. Immutable: agents read it but never rewrite it.
- **inbox/** — quick, unprocessed capture. Gets triaged into `raw/` or discarded.
- **outputs/** — artifacts agents generate (drafts, reports). Not canonical knowledge.
- **ops/** — operational records: [runs](ops/runs/), [feedback](ops/feedback/),
  [evals](ops/evals/).

## How it works

- [SCHEMA.md](SCHEMA.md) is the canonical spec every agent reads before touching the
  brain.
- Agents operate in three modes: **INGEST** (fold in new sources), **QUERY** (answer
  with provenance), and **LINT** (keep the brain healthy).

## For agents

- Claude Code → [CLAUDE.md](CLAUDE.md)
- Codex / others → [AGENTS.md](AGENTS.md)
