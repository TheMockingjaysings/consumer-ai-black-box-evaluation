# Research Roadmap

## Current direction

The project is in a **second collision-audit and measurement-definition phase**.

The broad research area is:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

That is a research area, not yet a sufficiently narrow experimental question.

A candidate first measurement is:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

The roadmap no longer assumes that the next step is a larger authorization benchmark, a multi-model study, or automation.

## Stage 0 — Historical exploratory work

**Status: complete and preserved**

The original MOTHER work produced a five-scenario exploratory shakedown and concept papers focused on authorization boundaries, safe non-completion, instruction conflict, and escalation.

Those materials remain part of the historical record. They are not the current claim and should not be retroactively rewritten.

## Stage 1 — Second collision audit

**Status: active**

Purpose: determine whether the new reproducibility/deployment-opacity direction is already addressed more rigorously by existing work.

Priority search areas:

- repeated-run nondeterminism and behavioral stability;
- longitudinal model or product drift;
- black-box endpoint stability and behavioral fingerprinting;
- consumer-interface versus API evaluation differences;
- hidden routing, product-layer, and system-prompt confounds;
- memory, personalization, account, and interface-state effects;
- reproducibility standards for outside evaluators without privileged access.

Exit condition: a written decision that either identifies a narrow practical gap worth testing, redirects the project toward replication/contribution, or stops the standalone methodology effort.

## Stage 2 — Measurement definition

**Status: pending Stage 1**

If a useful gap remains, define exactly one first measurement.

Before any confirmatory study, specify:

- one fixed synthetic probe;
- one observable behavioral variable;
- one coding method;
- the visible interface state that must be logged;
- what counts as the same versus different outcome;
- which hidden variables remain uncontrolled;
- what raw evidence must be preserved.

Historical authorization scenarios may be reused as probes, but only as measurement instruments. Their use does not revive an authorization-novelty claim.

## Stage 3 — Feasibility shakedown

**Status: not started**

Run a very small number of manual trials to answer an instrument-development question:

> **Can this behavior be observed and coded consistently enough to justify a larger preregistered study?**

The feasibility shakedown should test:

1. whether the fixed probe can be presented consistently;
2. whether the visible deployment state can be documented adequately;
3. whether the outcome categories can be applied without repeated ad hoc reinterpretation;
4. whether the raw interaction record is sufficient for later audit;
5. whether the procedure can be explained clearly enough for another evaluator to follow.

The shakedown is exploratory instrument development. Its observations must not later be promoted into confirmatory evidence for thresholds chosen after those observations were seen.

## Stage 4 — Preregistration

**Status: contingent on feasibility**

Only if the measurement survives Stage 3 should the project freeze a real study protocol.

The preregistration should state in advance:

- exact probe text;
- coding rules;
- products or visible model labels included;
- number of repetitions;
- session conditions;
- time window;
- exclusion and missing-data rules;
- visible metadata fields;
- primary outcome;
- threshold or decision rule for what will count as sufficiently reproducible, insufficiently reproducible, or inconclusive;
- stopping conditions.

The threshold should not be selected using the same observations later treated as confirmatory evidence.

## Stage 5 — Repeated-run study

**Status: contingent**

Collect the preregistered observations without changing the rules in response to the emerging result.

Primary output should be measured variation under documented visible conditions. Hidden causes should not be inferred from behavioral differences alone.

If the protocol later compares sessions, accounts, interfaces, or time periods, those sources of variation should be reported separately rather than collapsed into one unexplained score.

## Stage 6 — Replication and external review

**Status: contingent**

If the study produces interpretable evidence, package the procedure so another outside evaluator can attempt replication.

A replication package should include:

- exact probe text;
- run instructions;
- visible-state checklist;
- outcome coding guide;
- timestamps and visible product/model labels;
- raw interaction records where sharing is permitted;
- exclusion rules;
- uncertainty and limitations;
- change log for product or model drift.

External reviewers should be asked whether the measurement is clear, whether the claims match the evidence, and whether the work adds anything beyond existing methods.

## Stage 7 — Decide what the project becomes

Possible evidence-based outcomes include:

- a small reproducibility protocol;
- a replication or methods case study;
- a public documentation guide;
- a contribution to an existing evaluation project;
- a retrospective on the failed or narrowed research direction;
- a documented decision to stop.

These are possible final forms, not automatic indicators that the hypothesis or method succeeded.

## Decision discipline

A negative or null result can be scientifically useful, but usefulness is not the same as confirmation.

Each formal study phase must distinguish among:

- evidence that supports continuing;
- evidence that argues against continuing;
- evidence that is inconclusive.

## Scope constraints

For the current roadmap:

- public consumer AI only;
- synthetic or otherwise non-sensitive scenarios;
- no patient data, real financial records, credentials, or regulated personal information;
- no claims about hidden reasoning or internal architecture without independent evidence;
- no attempt to evade rate limits, safeguards, or access controls;
- no automation until the measurement itself is shown to be coherent;
- no novelty claim until the second collision audit supports one.