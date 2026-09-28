# External Evaluation of Consumer AI Under Deployment Opacity

## Status

**Replication decision phase — September 28, 2026**

This document defines the current active scope. Earlier MOTHER materials remain historical artifacts and should not be retroactively rewritten.

## Broad research area

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This is an established methodological area. The project does not claim that black-box evaluation, model drift, nondeterminism, consumer-interface auditing, or external evaluation are new topics.

## Audit 2 finding

The second collision audit found substantial direct overlap between the project's replacement framing and existing 2026 research.

In particular, current work already measures or documents:

- repeated-prompt consistency and test–retest agreement;
- black-box endpoint stability using fixed prompt sets;
- API versus consumer-interface behavior;
- temporal or deployment-related behavioral change;
- consumer-interface version opacity and hidden personalization;
- rate-limit, reset, and auditability barriers for independent evaluators.

See [`second-collision-audit-2026-09-28.md`](second-collision-audit-2026-09-28.md).

## Status of the earlier candidate measurement

The earlier candidate question was:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

This remains a valid measurement design, but it should **not** be presented as a novel methodology.

If used, it should be used to replicate or operationally test an existing published approach.

## Current active question

The immediate question is now:

> **Is there a published consumer-interface or black-box evaluation finding that an ordinary outside evaluator can meaningfully replicate under documented, low-resource conditions, and would that replication add useful evidence?**

The project should not collect confirmatory data until that question has a concrete answer.

## What a useful replication would require

A replication target should specify:

- the exact published finding or protocol being tested;
- which source-study conditions can be reproduced;
- which conditions cannot be reproduced and why;
- the visible interface state that must be logged;
- the outcome measure used by the source study or a transparently justified adaptation;
- what counts as successful replication, failed replication, and inconclusive replication;
- the value added by an independent replication.

The fact that the evaluator is unaffiliated, manual, or low-resource is not sufficient by itself to establish a contribution.

## Hidden variables and confounding

Possible hidden variables include:

- routing;
- model snapshots;
- system instructions;
- safety layers;
- A/B experiments;
- server-side memory or personalization state;
- product updates;
- regional or infrastructure differences.

These are **unobserved deployment variables**. The project may document behavioral variation while they are present, but it should not attribute the variation to any one hidden cause without independent evidence.

Observed behavioral change is not automatically evidence that the underlying model changed.

## Feasibility before preregistration

If a replication target is selected, the first run should be a tiny manual feasibility check.

That check should answer:

- Can the source procedure be reproduced through the available consumer interface?
- Can visible state be logged reliably?
- Can the source outcome measure or coding rule be applied without ad hoc revision?
- Can ambiguity be recorded transparently?
- Can evidence be preserved sufficiently for another person to inspect?

The feasibility observations must not later be treated as confirmatory evidence for a decision rule chosen after seeing those observations.

## Evidence claims

The project may support statements such as:

- a specified published result did or did not reproduce under documented conditions;
- the replication was inconclusive because source-study conditions could not be matched;
- repeated runs produced a stated distribution of predefined outcomes;
- a consumer-interface replication exposed a documented practical constraint not visible in the source method.

The project cannot infer from interface behavior alone that:

- the underlying model changed;
- a router caused the difference;
- a system prompt caused the difference;
- a safety layer caused the behavior;
- the system internally reasoned in a particular way.

## Current findings

**None yet under the active framing.**

The current work consists of collision auditing, literature verification, and replication-target selection.

## Population and environment

The intended environment remains ordinary public-facing AI products available to consumers.

The project does not require API access, model weights, hidden system prompts, chain-of-thought, routing metadata, proprietary logs, or internal developer access.

## Out of scope

For the current phase:

- hospital, clinical, or internal healthcare deployments;
- patient records or protected health information;
- real financial records or credentials;
- insurance adjudication systems;
- internal enterprise systems;
- attempts to bypass safeguards or access controls;
- prohibited automation;
- mechanistic claims unsupported by external evidence.

## Relationship to MOTHER

MOTHER was the historical authorization-centered phase. The active project keeps the discipline of bounded claims and explicit uncertainty, but it is no longer presented as an authorization benchmark or as a new black-box evaluation methodology.

The current project is best understood as a **search for a useful independent replication or documentation contribution within an already established research area**.