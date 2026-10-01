---
name: capability-review
description: Evaluates repeated evidence to recommend whether a skill or workflow should be promoted or improved. Use when the user asks to review capabilities, assess recurring work, or decide whether a behaviour deserves reusable automation.
---

# Capability Review

Read [SCHEMA](../../../SCHEMA.md) first; its definitions and approval boundaries are canonical.

## Evidence review

Start at the wiki index. Inspect relevant evidence in `wiki/patterns/`, `ops/runs/`, `ops/feedback/`, existing skills, and repeated user behaviours available in context. Follow supporting provenance only as needed; empty records are missing evidence, not permission to invent it.

Distinguish independent occurrences from multiple descriptions of one event. Compare existing skills and pending proposals before recommending a new responsibility. Choose: **new skill**, **existing-skill improvement**, **reusable workflow**, or **no action**.

## Promotion lifecycle

1. Observe a repeated pattern.
2. Gather concrete evidence, outcomes, limitations, and competing explanations.
3. Propose a capability/change (or no action) and explain why reuse justifies its maintenance and retrieval cost; identify overlap with existing capabilities.
4. Define a lightweight evaluation: should-trigger and should-not-trigger examples, expected behaviour, and the outcome that would justify keeping the change.
5. Ask for explicit approval of the specific proposal before any capability write.
6. Only after approval, create/modify the scoped skill or workflow and check its evaluation; approval of a review is not approval to implement its suggestions.

## Boundaries

- **Side effects:** analysis and proposal only before approval. Keep uncertain/rejected proposals transient.
- Do not silently create, rewrite, install, or expand capabilities, manufacture evidence, or build a taxonomy/framework.
- Reuse existing capabilities/proposals on repeated reviews; do not create duplicates or treat a single weak signal as proven recurrence.

For lightweight routing examples, see [evaluations](../../../ops/evals/skills/capability-review/README.md).
