# AGENTS.md

This directory is a shared **brain** (knowledge base + workspace) operated by
multiple agents, including Codex.

**Before creating, modifying, moving, or deleting anything here, read
[SCHEMA.md](SCHEMA.md).** It is the canonical operating specification: the directory
model, provenance rules, and the `INGEST` / `QUERY` / `LINT` operations.

Non-negotiable invariants:

- `raw/` is **immutable** source material — read it, never silently rewrite or
  delete it. Changes to `raw/` require explicit human approval.
- `wiki/` is agent-maintained — preserve provenance, keep `wiki/index.md` current,
  and append to `wiki/log.md`.
- Keep the system tool-independent (plain Markdown + folders). Do not add databases,
  plugins, or external services.
