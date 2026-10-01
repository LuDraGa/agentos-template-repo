# CLAUDE.md

This directory is a shared agentic **brain** (Obsidian vault + multi-agent
workspace).

**Before modifying the brain, read [SCHEMA.md](SCHEMA.md)** — the canonical operating
specification (directory model, provenance, and the `INGEST` / `QUERY` / `LINT`
operations).

Invariants:

- `raw/` is **immutable** — read only; never rewrite or delete without explicit
  human approval.
- `wiki/` is agent-maintained — preserve provenance, keep `wiki/index.md` current,
  append to `wiki/log.md`.
- Start navigation from `wiki/index.md` (progressive disclosure — load only what you
  need).
- Keep it tool-independent: plain Markdown + folders, no new dependencies.
