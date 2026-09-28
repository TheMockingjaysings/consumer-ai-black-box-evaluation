# Research Roadmap

## Current direction

The project has completed a second collision audit.

**Current status: replication decision phase.**

The audit found substantial direct overlap with existing 2026 work on repeated-prompt consistency, test–retest agreement, black-box endpoint stability, consumer-interface/API differences, and structural barriers to independent consumer-interface evaluation.

The detailed record is in [`second-collision-audit-2026-09-28.md`](second-collision-audit-2026-09-28.md).

The roadmap therefore no longer treats a repeated fixed-probe consumer-interface study as a possible new methodology.

## Stage 0 — Historical exploratory work

**Status: complete and preserved**

The original MOTHER work produced a five-scenario exploratory shakedown and concept papers focused on authorization boundaries, safe non-completion, instruction conflict, and escalation.

Those materials remain part of the historical record. They are not the current claim and should not be retroactively rewritten.

## Stage 1 — Authorization collision audit

**Status: complete**

Finding: heavy overlap with existing authorization, abstention, least-privilege, delegation, commit-time authorization, and public red-teaming research.

Decision: retire the general authorization-benchmark novelty claim.

## Stage 2 — External-evaluation collision audit

**Status: complete enough for a decision**

Finding: substantial direct overlap with existing work on:

- repeated-run consistency and test–retest agreement;
- black-box endpoint stability and behavioral fingerprinting;
- API versus consumer-interface evaluation;
- deployment/version opacity and temporal change;
- structural barriers faced by independent evaluators.

Decision: do not claim a new black-box repeatability method. Treat the earlier candidate measurement as a replication or feasibility instrument only.

## Stage 3 — Replication target selection

**Status: active**

Select one published finding or protocol for which an independent replication through ordinary consumer access could add useful information.

The selection should answer:

1. What exact published claim or measurement is being replicated?
2. Why does an unaffiliated, low-resource replication add evidence rather than merely repeat the paper?
3. Which conditions from the published method can and cannot be reproduced?
4. What would count as successful replication, failed replication, and inconclusive replication?
5. Can the work be performed manually and ethically without evading safeguards, rate limits, or access controls?

If no useful target survives this step, the standalone project should stop or become a documentation/retrospective resource.

## Stage 4 — Tiny feasibility check

**Status: contingent on Stage 3**

Run only enough manual trials to determine whether the selected published procedure can be implemented under ordinary consumer-interface constraints.

The feasibility check should test:

- whether the required visible state can be documented;
- whether the prompt or probe can be presented consistently;
- whether the published outcome coding can be reproduced or adapted transparently;
- whether ambiguous cases can be recorded rather than forced into a category;
- whether evidence can be preserved well enough for later audit.

These exploratory observations must not later be promoted into confirmatory evidence for thresholds chosen after seeing them.

## Stage 5 — Preregistered replication

**Status: contingent**

Only if the feasibility check succeeds should the project freeze a replication protocol.

The preregistration should state in advance:

- exact source study and target claim;
- exact prompt/probe text;
- products or visible model labels included;
- number of repetitions;
- session conditions;
- time window;
- visible metadata fields;
- coding rules;
- exclusion and missing-data rules;
- primary replication outcome;
- successful, failed, and inconclusive replication criteria;
- stopping conditions.

## Stage 6 — Analysis and replication package

**Status: contingent**

Report the result as a replication, not as a newly invented benchmark.

The package should include:

- the source study being replicated;
- exact procedure and deviations from the source method;
- visible-state checklist;
- raw interaction records where sharing is permitted;
- coding guide;
- uncertainty and limitations;
- reasons a replication was successful, failed, or inconclusive;
- any product/version changes observed during the study.

## Stage 7 — Decide what the project becomes

Possible evidence-based outcomes include:

- a small independent replication study;
- a low-resource replication protocol;
- a public evidence-recording guide;
- a contribution to an existing evaluation project;
- a retrospective on the research reset and collision audits;
- a documented decision to stop.

These are possible final forms, not automatic indicators that the project succeeded scientifically.

## Decision discipline

A negative or null result can be useful, but usefulness is not confirmation.

Each formal study must distinguish among:

- successful replication;
- failed replication;
- inconclusive replication.

## Scope constraints

For the current roadmap:

- public consumer AI only;
- synthetic or otherwise non-sensitive scenarios;
- no patient data, real financial records, credentials, or regulated personal information;
- no claims about hidden reasoning or internal architecture without independent evidence;
- no attempt to evade rate limits, safeguards, or access controls;
- no prohibited automation;
- no novelty claim for repeated-prompt consistency, consumer-interface auditing, or API/interface divergence.