---
name: brain-query
description: Answers a question from the shared brain with traceable provenance and calibrated uncertainty. Use when the user asks what the brain knows, requests a knowledge-base answer, or needs verification against stored sources.
---

# Brain Query

Read [SCHEMA](../../../SCHEMA.md) first; follow its [QUERY operation](../../../SCHEMA.md#query--answer-using-the-brain-with-provenance). This skill is only its routing adapter.

## Procedure

1. Start at the wiki index; load relevant linked pages and verify against original sources when necessary.
2. Answer with citations, distinguishing source facts, inference, missing evidence, and conflicts. Do not fill gaps with invented knowledge.
3. Apply the canonical promotion rule afterward. Reuse existing pages if promotion adds something meaningful; otherwise remain read-only.

## Boundaries

- **Side effects:** none by default; qualifying promotions follow canonical QUERY/INGEST, navigation, and logging rules.
- **Approval:** promotion never overrides raw-source or destructive-change approval requirements; respect explicit transient-only instructions.

For lightweight routing examples, see [evaluations](../../../ops/evals/skills/brain-query/README.md).
