# Pattern — Socratic Sparring

**Sources:** [osint…socratic-sparring](../sources/osint-vc-talent-discovery-socratic-sparring.md)
**Kind:** reusable learning method (human ↔ agent)

A way to build a rigorous mental model by **making explicit claims and testing them**, rather than having the agent explain a topic to you. It preserves the cognitive effort that drives learning (you commit to an answer before seeing the explanation) while using the agent to surface blind spots.

## What it combines
Socratic questioning · first-principles decomposition · binary (True/False) constraint framing · metacognition · active hypothesis testing. The True/False structure forces explicit positions on definitions, boundaries, dependencies, assumptions, trade-offs, and misconceptions. *(from source)*

## Procedure
1. Define a topic or problem.
2. State several **True/False** hypotheses about it.
3. Test: definitions · boundaries · dependencies · prerequisites · misconceptions · build-vs-buy · trade-offs.
4. Explain *why* each hypothesis is correct or incorrect.
5. Identify remaining uncertainty.
6. Generate the next, sharper set of hypotheses.

The agent may suggest blind spots, but the human evaluates each assertion **before** seeing the explanation.

## Reusable prompt
> Act as a Socratic sparring partner. I want to build a rigorous mental model of **[TOPIC]**. Do not immediately explain the whole topic. Instead, help me uncover gaps in my understanding through sharp True/False assertions. Focus on: what the concept actually is; what it is not; prerequisites; dependencies; boundaries; common misconceptions; standard vs custom parts; build vs buy; practical trade-offs; unknown unknowns. Present a small number of assertions at a time. Let me answer first. Then explain where my reasoning is correct, incomplete, or mistaken. Use my answers to generate progressively deeper questions.

## Caveat (from the source's own reflection)
The questions are most valuable when **you** generate them from your own gaps; full delegation to the agent loses some benefit. But identifying your own *unknown unknowns* is hard, so agent augmentation is still useful — aim for the balance, not either extreme.

## Seen in use
This exact method produced the reasoning behind [topics/osint-for-vc-talent-discovery](../topics/osint-for-vc-talent-discovery.md).
