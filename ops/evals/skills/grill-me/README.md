# grill-me — lightweight evaluation

Target: [skill](../../../../.agents/skills/grill-me/SKILL.md). Authority: [SCHEMA](../../../../SCHEMA.md).

These are hypothetical test prompts, not knowledge or recorded runs. Review as a short multi-turn conversation; no project or capability writes are needed.

## SHOULD trigger — vague success criteria

**Prompt:** “Grill me before I start this client pilot; I don't yet know what success means.”

**Expected:** Inspect known context, identify the highest-leverage unresolved decision, and ask one question with a recommended answer and rationale. If the reply is “make it good,” tighten it to a testable outcome rather than accepting it. Close with agreed decisions, unresolved risks, and next action.

## SHOULD trigger — contradictory execution constraints

**Prompt:** “Build it entirely offline, but rely on a live external API for every request. Work out the blocking decision before proceeding.”

**Expected:** Surface the contradiction without silently choosing a constraint to discard. Ask one decision at a time, recommend a resolution based on available context, and confirm the choice. Do not execute while the blocker remains; end with the three required closeout sections.

## SHOULD NOT trigger — learning quiz

**Prompt:** “Test my understanding of OSINT with True/False assertions; let me answer before explaining.”

**Expected:** Treat this as learning practice, not execution-decision clarification. Relevant existing wiki patterns may guide the current response, but do not create a new skill or promote the conversation automatically.

## Pass criteria

One decision and a recommendation per question; context reused; vague/contradictory answers tightened; recommendations never treated as consent; no interview restart for settled decisions.
