# Topic — OSINT for VC Talent Discovery

**Sources:** [osint…socratic-sparring](../sources/osint-vc-talent-discovery-socratic-sparring.md) *(primary)* · [boldcap-eir-ai-builder-jd](../sources/boldcap-eir-ai-builder-jd.md) · [aiwisegrow-company-profile](../sources/aiwisegrow-company-profile.md) *(applied example)*

Using **Open-Source Intelligence** — gathering and analysing publicly available information — to **source and screen early-stage, research-based founders** before they actively raise, where conventional profiles (e.g. LinkedIn) are thin.

## What OSINT is (and isn't)
A concept/methodology, **not** a database, library, or single tool. As a field it has standardized frameworks, intelligence cycles, and verification practices. *(from [osint-src])*

## Discovery signals & sources
- **Sources:** Google Scholar, GitHub / Hugging Face, patent databases, research grants, university/research-lab ecosystems, technical communities.
- **Screening signals:** peer/expert engagement, quality of public technical work, open-source collaboration history, academic credibility, affiliations, project/company history, public risk indicators. *(from [osint-src])*

## Design constraints for a sourcing/screening system
- Strong **public signals** are what make OSINT viable for this problem.
- Those signals are **non-standard for very-early research founders** and must be discovered experimentally per domain.
- **OSINT alone is insufficient** — a real system also needs CRM, scoring/ranking, ML/NLP, data pipelines, and proprietary heuristics.
- **Build-vs-buy:** buy the commodity data infrastructure; concentrate custom effort on differentiated signal discovery, scoring/ranking, and workflow integration. *(all from [osint-src])*

## In practice
- [BoldCap](../entities/boldcap.md)'s "Talent Radar" and deal-sourcing agenda are a direct instance of this topic. *(from [boldcap JD])*
- The [AIWise Grow company profile](../sources/aiwisegrow-company-profile.md) is a worked example of OSINT applied to **company/founder diligence** — note its explicit Confirmed/Claimed/Inferred/Unknown evidence labelling, a reusable discipline for any OSINT output.

## Related method
The author reasoned about this topic using [socratic-sparring](../patterns/socratic-sparring.md) — a useful companion when the signals themselves are unknown and must be surfaced.

[osint-src]: ../sources/osint-vc-talent-discovery-socratic-sparring.md
[boldcap JD]: ../sources/boldcap-eir-ai-builder-jd.md
