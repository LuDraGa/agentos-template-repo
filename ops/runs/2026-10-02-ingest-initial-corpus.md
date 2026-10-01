# Run — First INGEST pass (initial raw/ corpus)

**Date:** 2026-10-02
**Operation:** INGEST (per [SCHEMA](../../SCHEMA.md))
**Inputs:** 6 files in `raw/` (2 Markdown, 4 PDF)

## What happened

Ingested the initial corpus following the SCHEMA INGEST flow (inspect index → source
pages → synthesized pages → cross-link → update index → log).

- **6 source pages** created in `wiki/sources/` (one per raw file).
- **5 synthesized pages:** topics `osint-for-vc-talent-discovery`,
  `llm-architecture-basics`; entities `aiwisegrow`, `boldcap`; pattern
  `socratic-sparring`.
- Updated `wiki/index.md`, `wiki/overview.md`, appended `wiki/log.md`.

## Decisions & judgement calls

- **Separated source summaries from synthesis.** Source pages describe *what the
  source is*; topic/entity/pattern pages hold reusable claims, each citing back.
- **Did not force categories.** No `projects/` or `decisions/` pages — neither is
  established by the material. Flagged the *implied* "build a VC talent-discovery
  system" project as an inference I did **not** store.
- **Preserved evidence nuance** for AIWise Grow (Confirmed/Claimed/Inferred/Unknown).
- **PDF handling without installs:** text extracted via macOS PDFKit
  (`osascript`/JXA); the image-only FDE lecture was rendered with `qlmanage` and read
  visually. The rendered PNG is a throwaway in `/tmp`, not stored in the vault.
- ***Flawless Consulting*** kept as a reference source (front matter + TOC only); no
  synthesized topic page until the body is read.

## Follow-ups

- Not committed (per owner instruction). Awaiting review.
- Future ingest: *Flawless Consulting* body; later FDE classes; confirm whether a
  VC-talent-discovery project exists.
