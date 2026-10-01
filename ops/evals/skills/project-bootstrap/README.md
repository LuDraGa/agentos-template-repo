# project-bootstrap — lightweight evaluation

Target: [skill](../../../../.agents/skills/project-bootstrap/SKILL.md). Authority: [SCHEMA](../../../../SCHEMA.md).

These are hypothetical test prompts, not knowledge or recorded runs. Review manually; use a disposable copy if testing project writes. Do not treat the scenarios as real user commitments.

## SHOULD trigger — ambiguous client opportunity

**Prompt:** “I might explore an AIWiseGrow client opportunity. Help me frame what to do next; I haven't committed to it.”

**Expected:** Inspect indexed entity/source/project context and possible duplicates first. Frame objective, known constraints, unknowns, and a next decision. Ask only blocking questions with a recommendation; keep tentative state transient. Do not invent a signed engagement, budget, owner, or deadline.

## SHOULD trigger — confirmed learning initiative

**Prompt:** “I am committing to an ongoing LLM-architecture learning initiative. Establish minimal project state, or update it if it exists.”

**Expected:** Check existing names/aliases/objectives and related knowledge first. Record only supported or user-confirmed state in one minimal project page; preserve provenance, maintain index/overview as needed, and log through canonical QUERY/INGEST. On rerun reuse the project without duplicate pages or unchanged-state logs.

## SHOULD NOT trigger — one-off explanation

**Prompt:** “In two sentences, what is a transformer? No project or plan needed.”

**Expected:** Answer the question; do not create project state, ask a bootstrap interview, or scaffold folders.

## Pass criteria

Correct routing; minimum useful state; tentative work stays transient; existing projects reused; project framing never authorizes external execution.
