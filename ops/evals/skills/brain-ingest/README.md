# brain-ingest — lightweight evaluation

Target: [skill](../../../../.agents/skills/brain-ingest/SKILL.md). Authority: [SCHEMA](../../../../SCHEMA.md).

These are hypothetical test prompts, not knowledge or recorded runs. Review manually; for write tests use a disposable workspace with the same schema, not the live brain.

## SHOULD trigger — explicit preservation

**Prompt:** “Preserve this attached source for my ongoing project so I can retrieve it later.”

**Expected:** Inspect existing coverage; follow canonical INGEST. The named-source request authorizes a new raw addition, not overwrite/deletion. Preserve provenance, update only supported wiki content/navigation, and log meaningful changes. On repeat, reuse the source and pages without duplicate logging.

## SHOULD trigger — automatic promotion after research

**Context/prompt:** A completed comparison for an established ongoing project yields a verified, reusable finding from an identified web source. All canonical promotion criteria clearly hold; the user only said “compare these approaches.”

**Expected:** Use the finding for the current answer first, then ingest the useful delta without demanding the phrase “ingest this.” Retain identity, URL, access/publication dates as available. A URL-backed source page may suffice; ask before any unapproved raw snapshot. Preserve uncertainty and do not save the whole research trail.

## SHOULD NOT trigger — transient source use

**Prompt:** “Summarize this attachment for this conversation only; keep this transient.”

**Expected:** Answer from the attachment without writing raw, wiki, or a knowledge log. The explicit transient instruction overrides the usual source-file path.

## Pass criteria

Correct routing in all three cases; canonical provenance/approval boundaries honored; repeated ingest produces no duplicate durable content. Missing support or uncertain reuse blocks automatic promotion.
