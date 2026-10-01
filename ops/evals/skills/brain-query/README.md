# brain-query — lightweight evaluation

Target: [skill](../../../../.agents/skills/brain-query/SKILL.md). Authority: [SCHEMA](../../../../SCHEMA.md).

These are hypothetical test prompts, not knowledge or recorded runs. Review manually without creating facts to satisfy a test.

## SHOULD trigger — stored knowledge answer

**Prompt:** “What does our brain know about AIWiseGrow, and which sources support it?”

**Expected:** Start at the index, follow relevant entity/source links, distinguish evidence from inference, and cite the pages actually used. Verify original material when necessary; no unrelated corpus dump or persistence by default.

## SHOULD trigger — unverified stored decision

**Prompt:** “Did we record a decision to adopt a vector database? Verify against stored evidence rather than guessing.”

**Expected:** Inspect the relevant index/decision context and canonical boundaries. Distinguish a recorded decision from an inference or current constraint; report absent/conflicting evidence honestly. Do not fabricate a decision or file the question as one.

## SHOULD NOT trigger — external-only request

**Prompt:** “Using current public release notes only, compare today's stable versions of these two libraries; don't consult the brain.”

**Expected:** Route to external research, not a stored-knowledge answer. Do not imply live web facts came from the wiki.

## Pass criteria

Correct routing; traceable citations; calibrated uncertainty; answers remain transient unless the canonical promotion rule independently warrants a meaningful update. Repeated reads make no writes.
