---
name: brain-lint
description: Checks the shared brain for integrity, provenance, linkage, and index health. Use when the user asks to lint, audit, validate, or find stale, broken, duplicate, or orphaned brain knowledge.
---

# Brain Lint

Read [SCHEMA](../../../SCHEMA.md) first; use its [LINT operation](../../../SCHEMA.md#lint--keep-the-brain-healthy). This skill is only its routing adapter.

## Procedure

1. Scope the audit to the request, starting from the wiki index and following relevant links; do not load unrelated knowledge.
2. Run canonical LINT checks within that scope. Report concrete findings with paths/evidence; distinguish verified defects from judgement calls and untested areas.
3. Propose the smallest corrections and obtain approval before applying fixes outside an already approved scope.
4. Append the canonical LINT summary, including scope and remaining findings. Repeated audits may append new summaries, not duplicate corrective content.

## Boundaries

- **Side effects:** scanning and an append-only LINT log entry; corrective wiki edits require human approval.
- Never modify raw material or silently delete, merge, or rewrite content. Do not invent knowledge merely to clear a finding.

For lightweight routing examples, see [evaluations](../../../ops/evals/skills/brain-lint/README.md).
