# Research Roadmap

This roadmap separates what MOTHER currently tests from what would be required to support stronger claims.

The main change as of September 28, 2026 is simple: **v0.2 should not be frozen until the collision audit is complete enough to show that MOTHER would add something measurable beyond existing public work.**

## Stage 1 — Current v0.1 shakedown

**Question:** Can a small set of static authorization-conflict scenarios and a frozen qualitative rubric be applied clearly and consistently enough to justify further instrument development?

Current design:

- five static hypothetical scenarios;
- all five describe insufficient authorization;
- exact frozen prompt text;
- 0/1/2 human scoring rubric;
- clean-primary exposure controls;
- independent second scoring when available;
- explicit prompt-leakage review;
- no live tools or autonomous execution.

What this stage can examine:

- scenario ambiguity;
- scoring ambiguity;
- evaluator disagreement;
- obvious prompt cueing;
- generic-refusal artifacts; and
- basic reproducibility of the procedure.

What this stage cannot establish:

- authorization-state discrimination;
- over-refusal rates;
- statistical properties of a model or provider;
- transfer from stated behavior to enacted behavior;
- any internal reasoning mechanism; or
- safe behavior in an autonomous agent loop.

The frozen v0.1 protocol remains unchanged.

## Stage 1.5 — Collision audit

**Question:** Is there still a distinct evaluation problem here that MOTHER can measure usefully?

This stage now comes **before** v0.2 design is finalized.

The strongest overlaps found so far include:

- AgentAbstain;
- SteerBench-Work;
- Agentic Abstention;
- the Public Authorization-Boundary Benchmark proposal;
- FelonyBench;
- AuthBench;
- FORTIS;
- APort Vault;
- AGATE;
- OpenAI Auto-review;
- AgentHarm;
- crowdsourced misalignment testing; and
- participatory red-teaming and user-testing work.

The audit is organized around three candidate directions:

### Candidate A — authorization-state discrimination

Can a system change appropriately among continue, stop, and ask when the underlying task stays similar but the authorization condition changes?

Current assessment: **heavy methodological overlap**, especially with AgentAbstain and SteerBench-Work.

A three-condition design is not enough by itself to justify a separate benchmark.

### Candidate B — authority provenance and delegation

Can a system distinguish valid authority from unsupported, delegated, expired, conflicting, or second-hand claims?

Current assessment: **substantial overlap** with authorization, delegation, provenance, and runtime-gating work.

### Candidate C — independent black-box evaluation by outside users

Can evaluators without privileged model access use a disciplined public protocol to produce reproducible, auditable observations from ordinary user-facing systems?

Current assessment: **still open, but not obviously novel**. Crowdsourced and participatory evaluation already exist, so any MOTHER contribution would need to be narrower and testable.

The specific unresolved issue is whether observations made through ordinary public interfaces can be made comparable enough to be useful despite hidden provider configuration, routing, model updates, personalization, and other external-evaluator confounders.

See `collision-audit.md` and `related-work.md`.

## Decision gate before v0.2

Do not freeze v0.2 until the project can answer:

1. What exact construct is being measured?
2. Which existing benchmark is the closest comparator?
3. What observable information would MOTHER add?
4. Can that difference be tested rather than argued rhetorically?
5. Can the method be executed from a black-box external position without claiming hidden mechanisms?
6. Can another person reproduce it from the public documentation?

If those questions do not have convincing answers, the project should narrow, merge into existing work where useful, become an independent replication/public-interface audit method, or stop as a distinct benchmark.

## Stage 2 — Conditional v0.2 design

This stage is **on hold pending the collision audit**.

If a distinct signal survives review, the same five underlying scenarios may still be useful as a compact testbed. A candidate design would compare matched conditions while making both unsafe continuation and unnecessary refusal visible.

Possible design elements include:

- authorized / unauthorized / ambiguous conditions;
- explicit scoring for unnecessary refusal and unsafe continuation;
- reduced-cue wording;
- pressure variants;
- repeated trials specified before collection;
- blinded independent scoring;
- separate failure-mode reporting; and
- within-scenario comparisons instead of a single blended score.

But these elements should not be frozen merely because they are tidy. They need to serve a construct that survives the collision audit.

## Stage 3 — Interactive tool-use prototype

This stage should happen only if the earlier work identifies a useful question that static prompting cannot answer adequately.

A controlled environment could provide:

- authorized tools;
- at least one prohibited or out-of-scope action;
- a human-clarification or permission-request pathway;
- a legitimate task-termination option; and
- auditable action logs.

Observable behavior could include:

- continuing through an authorized route;
- requesting clarification;
- stopping;
- repeatedly probing a blocked route;
- attempting privilege expansion;
- accepting unsupported authority; or
- refusing a clearly authorized control task.

Where possible, scoring should rely on environment state and action logs rather than prose interpretation alone.

### Relationship to existing security controls

MOTHER is not intended to replace authentication, authorization, least privilege, sandboxing, access-control systems, monitoring, or runtime enforcement.

Those systems create and enforce boundaries.

If MOTHER reaches this stage, the research question would concern behavior around those boundaries, and any claim that it adds information beyond existing agent-security benchmarks would still need to be demonstrated.

## Stage 4 — Robustness and replication

Only if a useful signal survives the earlier gates should the project expand.

Possible questions include:

- Does the effect reproduce across models and providers?
- How sensitive is it to wording, interface, and inference settings?
- Does it survive different task domains?
- Do static results predict enacted behavior at all?
- Can independent researchers reproduce the protocol?
- Can trained non-specialists follow it reliably?
- Does MOTHER add information beyond the closest existing evaluations?

## Public participation

Public participation remains a possible direction, not a novelty claim.

Crowdsourced red teaming, participatory evaluation, and user testing already exist.

If MOTHER pursues this route, the question should be narrower: whether a disciplined protocol can turn observations from ordinary public interfaces into comparable evidence without privileged access.

A possible sequence would be:

1. methodological review;
2. small trained non-specialist replication;
3. comparison of scoring and protocol adherence across evaluators;
4. analysis of provider-interface confounders; and
5. broader participation only if the observations remain interpretable.

The aim would not be to treat unrestricted public prompting as scientific evidence.

## Decision rules

MOTHER should pause, narrow, merge, or stop if:

- the v0.1 rubric cannot be applied consistently;
- results are dominated by prompt cueing or blanket refusal;
- matched cases do not isolate the intended variable;
- static answers provide no useful signal for the intended agentic question;
- provider-interface confounders make external comparisons uninterpretable;
- another public evaluation already measures the proposed construct more clearly; or
- the project cannot state a distinct contribution without relying on branding or wording differences.

A decision to narrow, replicate, contribute to another project, or discontinue MOTHER as a separate benchmark would be a legitimate research outcome.