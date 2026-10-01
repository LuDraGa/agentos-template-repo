# Topic — LLM Architecture Basics

**Sources:** [fde-lecture-llm-arch-basics-class1](../sources/fde-lecture-llm-arch-basics-class1.md)
**Scope:** intro-level ("Class 1") conceptual overview — the pipeline, not implementation detail.

How a large language model is built and runs, end to end:

1. **Model = learned weights (parameters).** Parameter count broadly tracks capability/advancement across model generations.
2. **Data → cleaning.** Text is collected (internet, books, research papers, forums) then cleaned — remove duplicates, bias, misinformation, malformed/"social-media" english, and abuse — to leave knowledge + grammar. Both data quality and compute matter.
3. **Training objective = next-token prediction.** Text is turned into input→output continuation pairs (e.g. "The capital of India is" → "New Delhi"), training the model to predict the next token autoregressively.
4. **Tokenization.** Text → token ids via **byte-pair encoding (BPE)**, which maps common character sequences to ids (e.g. "Sumit" → "Sum" + "it"). Token ids alone carry no meaning.
5. **Embeddings.** Token ids map to vectors that encode meaning; semantically/analogically structured so that relationships hold in vector space — the canonical example **king − man + woman ≈ queen**.
6. **Transformers + attention.** Each token computes its role relative to the others, giving context-dependent meaning (e.g. "apple" the phone vs "apple" the fruit, disambiguated by the surrounding words).
7. **Generation.** Output is produced autoregressively by sampling from next-token probabilities `P(token | context)`.

*All claims above trace to the single [FDE lecture](../sources/fde-lecture-llm-arch-basics-class1.md) (a hand-drawn whiteboard; read from a rendered image).* Deeper mechanics await later classes in the series, which are not yet ingested.
