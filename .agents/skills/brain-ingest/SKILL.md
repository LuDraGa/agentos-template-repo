---
name: brain-ingest
description: Folds a durable source into the shared brain with provenance. Use when the user asks to ingest, remember, preserve, file, or make a source retrievable, or when completed work clearly qualifies under the canonical knowledge-promotion rule.
---

# Brain Ingest

Read [SCHEMA](../../../SCHEMA.md) first; its [INGEST operation](../../../SCHEMA.md#ingest--fold-new-source-material-into-the-brain-with-provenance) is authoritative. This skill only routes to it.

## Procedure

1. Apply the canonical promotion rule; inspect the wiki index and relevant pages for existing coverage.
2. Follow canonical INGEST, including source handling, provenance, derived pages, navigation, and logging. Load only relevant context; do not ingest an entire corpus by default.
3. Report what changed, what was already covered, and what remains uncertain or awaits approval. A no-change repeat creates no duplicate pages or knowledge-log entry.

## Boundaries

- **Side effects:** approved source additions; provenance-backed wiki updates, navigation maintenance, and an INGEST log entry for meaningful changes.
- **Approval:** obey SCHEMA's raw-source and destructive-change boundaries. Automatic knowledge promotion is not permission to alter raw material.
- Do not create unsupported claims or persist uncertain/disposable findings.

For lightweight routing examples, see [evaluations](../../../ops/evals/skills/brain-ingest/README.md).
