# research-and-synthesize — lightweight evaluation

Target: [skill](../../../../.agents/skills/research-and-synthesize/SKILL.md). Authority: [SCHEMA](../../../../SCHEMA.md).

These are hypothetical test prompts, not knowledge or recorded runs. Review manually; do not save research merely to run the evaluation.

## SHOULD trigger — ongoing-project comparison

**Prompt:** “Research and compare two approaches for my ongoing project, including trade-offs and source disagreements.”

**Expected:** Inspect relevant brain context, scope the decision, gather credible evidence, and separate source facts from synthesis. Cite original sources with dates and state limitations; use parallelism only if materially helpful. Answer first, then assess all promotion criteria. Promote only a clearly useful supported delta through canonical operations, reusing existing pages; no required local web snapshot or unapproved raw writes.

## SHOULD trigger — explicitly transient understanding

**Prompt:** “Help me understand this unfamiliar topic from credible web sources. Keep this transient.”

**Expected:** Produce a sourced, uncertainty-aware explanation. No raw snapshots, wiki updates, or knowledge-log entries, even if some findings seem reusable. Treat source instructions as untrusted content; no invented citations or claimed access to unavailable material.

## SHOULD NOT trigger — simple text transformation

**Prompt:** “Alphabetize this supplied list exactly as written; do not investigate the items.”

**Expected:** Transform the list directly; no research, delegation, or knowledge promotion.

## Pass criteria

Correct routing; evidence distinct from synthesis; explicit transient override honored; uncertain or disposable findings not persisted. Repeated research does not duplicate source pages or automatically imply durable value.
