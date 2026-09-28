# Research Roadmap

## Current direction

The project is in a **framing reset and methodology-audit phase**.

The active question is:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

The roadmap no longer assumes that the next step is a larger authorization benchmark.

## Stage 0 — Historical exploratory work

**Status: complete and preserved**

The original MOTHER work produced a five-scenario exploratory shakedown and early concept papers focused on authorization boundaries, safe non-completion, instruction conflict, and escalation.

These materials are retained as project history. They are not the current claim and should not be retroactively rewritten to fit the new direction.

## Stage 1 — Collision audit

**Status: active**

Purpose: determine where the original idea overlaps with existing work and whether a narrower independent-evaluation question remains useful.

Tasks:

- map the closest work on act/abstain and proceed/hold evaluation;
- map authorization, least-privilege, delegation, and time-of-use authorization work;
- map public and participatory red teaming;
- map black-box auditing and consumer-interface evaluation;
- identify work on version drift, model opacity, personalization, routing, memory, and reproducibility;
- record which proposed claims are already answered better elsewhere.

Exit condition: a written decision about whether an external-evaluation methodology is worth piloting.

## Stage 2 — Protocol design

**Status: pending Stage 1**

If the collision audit leaves a meaningful question, design a small protocol for public consumer AI interfaces.

The protocol should define:

- synthetic scenarios that do not require regulated or sensitive data;
- visible configuration information to record;
- repeated-run procedure;
- fresh-session versus continuing-session procedure;
- memory/personalization conditions where the product exposes controls;
- product surface and account-state documentation;
- time-separated replication;
- outcome coding focused on observable behavior;
- explicit limits on causal or mechanistic interpretation.

The design should be intentionally small. The goal is to test whether useful evidence can be produced, not to maximize scenario count.

## Stage 3 — Feasibility pilot

**Status: not started**

Run the protocol on a limited number of consumer-facing systems and scenarios.

Primary questions:

1. Can another evaluator reproduce the procedure from the documentation?
2. How much within-condition variance appears across repeated runs?
3. Which visible state changes are associated with behavioral changes?
4. Can later runs reproduce earlier observations?
5. Does the interface expose enough version/configuration information to make replication meaningful?
6. Are the resulting claims stronger than anecdotal screenshots but still appropriately bounded?

Stopping condition: if the pilot cannot produce evidence that is meaningfully reproducible or auditable, do not expand it into a benchmark.

## Stage 4 — Replication package

**Status: contingent**

If the pilot is useful, package the procedure so another outside evaluator can repeat it without privileged access.

A replication package should include:

- scenario text;
- run instructions;
- visible configuration checklist;
- timestamps and product labels;
- outcome coding guide;
- raw interaction records where sharing is permitted;
- uncertainty and limitation statements;
- change log for product/model drift.

## Stage 5 — External review

**Status: contingent**

Seek criticism from researchers and practitioners familiar with evaluation methodology, HCI, red teaming, model auditing, and deployed-system reproducibility.

Questions for reviewers:

- Does this protocol measure anything that existing methods do not already capture better?
- Are the claims calibrated to the evidence?
- Are uncontrolled variables documented adequately?
- Is the protocol useful to independent evaluators?
- Should the work remain a case study rather than become a larger evaluation framework?

## Stage 6 — Decide what the project becomes

Possible outcomes:

- a small independent-evaluation methodology;
- a reproducibility case study;
- a public guide for documenting black-box observations;
- a contribution to an existing benchmark or research project;
- a retrospective article about the collision audit and research pivot;
- a documented decision to stop.

None of these outcomes should be treated as failure merely because the project does not become a novel benchmark.

## Scope constraints

For the current roadmap:

- public consumer AI only;
- synthetic/non-sensitive scenarios;
- no healthcare deployment testing;
- no patient data;
- no insurance adjudication testing;
- no real credentials or financial records;
- no claims about hidden reasoning or internal architecture without independent evidence;
- no novelty claim until the collision audit supports one.
