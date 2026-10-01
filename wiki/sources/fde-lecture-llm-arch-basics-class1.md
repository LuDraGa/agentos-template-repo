# Source — FDE Lecture: LLM Architecture Basics (Class 1)

**Type:** lecture artifact — single-page hand-drawn whiteboard diagram (PDF)
**Raw:** [raw/FDE_Lecture_Sumit_LlmArch_Basics_Class1.pdf](../../raw/FDE_Lecture_Sumit_LlmArch_Basics_Class1.pdf) *(immutable)*
**Attribution:** "FDE" lecture series, Class 1; filename attributes to *Sumit*.
**Derives:** [topics/llm-architecture-basics](../topics/llm-architecture-basics.md)

## What this source is

A dense hand-drawn concept map introducing how LLMs work, apparently the first class of a series. The PDF has **no machine-readable text**; content was read from a rendered image of the page (rendering via the built-in `qlmanage` is a working step — the PNG is not canonical and is not stored in the vault).

## Key content (faithful)

- **ML framing:** supervised example (predict car resale value from age/mileage/owners) → train/test split → algo → model → inference; actual vs predicted.
- **Model = weights/parameters;** parameter count (GPT, Sonnet, …) tracks accuracy/advancement; model progression 3.5 → 4o → agents → image.
- **Data pipeline:** text from internet/books/research papers/Reddit/tweets → **clean** (remove duplicates, bias, misinformation, wrong/"social-media" english, abuse) → knowledge + grammar. Quality of data and compute both matter.
- **Training objective — next-token prediction:** "The capital of India is New Delhi" expanded into input→output pairs (The → capital → of → …).
- **Tokenization:** words → token ids via **BPE (byte-pair encoding)**, mapping common character sequences to ids; e.g. "Sumit" → "Sum" + "it"; ids alone are meaningless.
- **Embeddings:** token ids → vectors that carry meaning; semantic/analogical structure (gendered feature weights; **king − man + woman ≈ queen**).
- **Transformers + attention:** each token resolves its role relative to others (context); "apple" the phone vs "apple" the fruit disambiguated by attention.
- **Generation:** autoregressive sampling from next-token probabilities `P(token | context)`.

## Provenance note
Summary only; synthesized concept page: [llm-architecture-basics](../topics/llm-architecture-basics.md). Scope is intro-level ("Class 1"), not implementation detail.
