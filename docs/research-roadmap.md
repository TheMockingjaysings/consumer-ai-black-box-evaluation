# Research Roadmap

This roadmap separates the historical v0.1 work from the question I am actually investigating now.

The biggest change as of September 28, 2026 is that I am **not building v0.2 as another authorization benchmark**.

The authorization-focused literature review found too much direct overlap with existing work for that to be a comfortable claim. The next stage is therefore not “build a bigger benchmark.” It is to find out whether there is a useful external black-box evaluation problem left to study.

## Stage 1 — Frozen v0.1 shakedown

Version 0.1 remains a five-scenario static authorization shakedown.

It was designed to test whether the prompts, scoring rubric, exposure controls, and evaluator workflow were usable enough to learn from.

It does not establish a new authorization construct. It does not test live agents, tool use, or enacted behavior. It also cannot measure calibrated over-refusal because all five scenarios involve insufficient authorization.

The frozen v0.1 protocol stays unchanged.

## Stage 1.5 — Collision audit

This stage changed the project.

The original question overlapped heavily with work such as AgentAbstain, SteerBench-Work, Agentic Abstention, AuthBench, FORTIS, APort Vault, AGATE, the Public Authorization-Boundary Benchmark proposal, OpenAI Auto-review, AgentHarm, Misalignment Bounty, and participatory red-teaming research.

That review answered one important question for me: **MOTHER should not keep positioning itself as a new general authorization benchmark.**

The remaining audit is now focused on one narrower possibility:

> **Can an independent evaluator produce reproducible, auditable behavioral evidence from ordinary public AI interfaces when the deployment may change in ways the evaluator cannot see or control?**

See `collision-audit.md` and `external-black-box-scope.md`.

## Stage 2 — External black-box reproducibility audit

This is the current working stage.

The goal is not to prove that black-box evaluation is new. It is to test how much an outside evaluator can reliably claim under real public-interface conditions.

Questions include:

- How repeatable are nominally identical runs?
- What changes between fresh and continuing sessions?
- How much do visible memory or personalization states matter?
- Can another evaluator reproduce the same observation?
- What happens when the displayed model name stays the same but the behavior changes over time?
- Which metadata are essential for interpreting a replication failure?
- When is provider-side opacity too large for a strong comparison?

A future protocol may record:

- provider and displayed model name;
- visible version information;
- interface and platform;
- date, time, and timezone;
- fresh versus continuing session state;
- visible memory or personalization state;
- project or workspace context;
- visible reasoning or inference settings;
- tool, browsing, and connector state;
- exact prompt and complete response;
- retry or regeneration status;
- evaluator notes and score; and
- known deviations from the intended condition.

Unknown values stay unknown.

## Stage 3 — Small replication study, only if Stage 2 survives

If the literature audit shows that this question is still worth testing, the next step should be small.

A sensible first study would use a limited set of synthetic prompts across repeated public-interface runs and at least one second evaluator.

The point would be to test the method itself:

- can the visible conditions be documented consistently;
- can repeated runs be compared without overclaiming equivalence;
- can another evaluator follow the same procedure;
- can disagreements be explained or at least bounded; and
- does the protocol improve the quality of the claim compared with simply saving a transcript?

I do not want a large benchmark until that basic question is answered.

## Stage 4 — Broader replication, if justified

Only if the small study produces a useful signal should the project expand across more models, providers, interfaces, dates, or evaluators.

Possible questions include:

- How much reproducibility differs by provider or interface?
- How quickly do public results drift over time?
- Are some forms of personalization easier to control than others?
- Can the same observation survive across different accounts or platforms where testing is ethically and contractually permitted?
- Can trained non-specialists follow the protocol reliably?
- What kinds of claims remain defensible when the underlying deployment cannot be fully identified?

## Public participation

Public participation is not the novelty claim.

Crowdsourced red teaming and participatory evaluation already exist.

If MOTHER eventually involves outside contributors, the question should be whether a structured protocol helps different people produce **comparable, bounded evidence** from public interfaces—not whether ordinary people are allowed to test AI.

## Scope constraints

For the current direction:

- use public consumer-facing interfaces only;
- use synthetic or non-sensitive material;
- do not use patient records, protected health information, real financial records, credentials, or private institutional data;
- do not rely on privileged hospital, insurer, employer, or enterprise access;
- do not infer hidden mechanisms from response text;
- do not assume a displayed model label proves a stable deployment state.

Healthcare can remain part of the literature review. It is not the test domain.

## Decision rules

MOTHER should pause, narrow, merge into existing work, or stop if:

- the literature already answers the external-interface reproducibility question more rigorously;
- provider-side opacity makes the resulting evidence too ambiguous to interpret;
- the protocol adds paperwork but does not improve what can reasonably be concluded;
- independent replication repeatedly fails under closely matched visible conditions;
- the method depends on inaccessible assumptions about hidden deployment state; or
- the project can defend itself only through branding or wording differences.

A decision to narrow, contribute to an existing method, publish a replication protocol, or discontinue the project as a separate benchmark would all be legitimate outcomes.