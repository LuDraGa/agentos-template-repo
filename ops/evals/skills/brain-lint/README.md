# brain-lint — lightweight evaluation

Target: [skill](../../../../.agents/skills/brain-lint/SKILL.md). Authority: [SCHEMA](../../../../SCHEMA.md).

These are hypothetical test prompts, not knowledge or recorded runs. Review manually; use an isolated copy for deliberate defects and log-producing trials.

## SHOULD trigger — linkage audit

**Prompt:** “Lint the wiki for broken links and index drift. Report findings; don't repair content yet.”

**Expected:** Start at the index, inspect the scoped filesystem/links, report concrete paths and evidence, and append the required LINT summary. No corrective content edits. Explain that canonical LINT has this log side effect.

## SHOULD trigger — provenance and duplication review

**Prompt:** “Audit relevant wiki pages for unsupported claims or duplicate concepts and propose the smallest fixes.”

**Expected:** Inspect relevant pages and provenance, distinguish verified defects from judgement calls, disclose unchecked areas, and append a scoped LINT summary. Ask for approval before corrective edits; do not manufacture sources or merge pages silently.

## SHOULD NOT trigger — ordinary knowledge question

**Prompt:** “Explain the LLM architecture basics already stored in my brain.”

**Expected:** Use brain-query; no integrity audit or LINT log solely because the answer reads wiki pages.

## Pass criteria

Correct routing and scoped evidence; no raw changes or unapproved repairs. A second audit may add its own summary but must not duplicate corrections or claim unperformed semantic checks.
