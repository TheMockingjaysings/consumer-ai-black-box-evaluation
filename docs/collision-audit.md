# Collision Audit

## Status

**Audit 2 decision recorded — September 28, 2026**

This document summarizes two distinct collision audits:

1. why the project moved away from an authorization-centered benchmark; and
2. whether the replacement framing around external black-box reproducibility contains a distinct methodological contribution.

The detailed second audit is in [`second-collision-audit-2026-09-28.md`](second-collision-audit-2026-09-28.md).

## Audit 1 — Historical authorization-centered direction

### Original direction

The original project explored authorization boundaries, safe non-completion, instruction conflict, and escalation in public AI systems. A proposed next step was to compare closely matched authorized, unauthorized, and ambiguous variants of the same task.

### Finding

**Assessment: heavy overlap with existing research.**

Closely related work already studies act/abstain decisions, proceed/hold behavior, ambiguous authorization, least privilege, time-of-use authorization, authority provenance, delegation, tool-use constraints, sandbox boundaries, and public red teaming.

### Decision

The project will not proceed as a new general authorization benchmark unless a later review identifies a specific gap not already measured more rigorously elsewhere.

The historical five-scenario shakedown remains preserved as an instrument-development record.

## Audit 2 — External consumer-interface evaluation

The replacement area was:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This is an established research area, not a novelty claim.

### Finding

**Assessment: substantial direct overlap.**

The audit verified current work on:

- repeated-prompt consistency and test–retest agreement;
- black-box endpoint stability and behavioral fingerprinting;
- consumer-interface versus API differences;
- temporal or deployment-related behavioral change;
- structural barriers to independent consumer-interface evaluation;
- repeatability protocols for LLM outputs.

The previously proposed narrow measurement — repeated fresh-session presentation of one fixed probe with predefined outcome categories — is valid as a measurement instrument but is **not** a distinct methodological contribution.

### Decision

The project should not launch a new repeated-run study merely to establish that repeated consumer-interface outputs vary or that API results do not fully transfer to interfaces.

If the project continues, the next scientifically honest route is **replication, contribution, or documentation**, not a new label for an established method.

## Verified direct collisions

See the dated audit for full details and links. The most direct overlaps include:

- *Behavioral Fingerprints for LLM Endpoint Stability and Identity* — fixed prompt sets, repeated sampling, black-box change detection;
- *API Benchmark Scores Do Not Reliably Transfer to Chatbot Interfaces* — repeated consumer-interface trials, test–retest agreement, API/interface comparisons;
- *LLM Spirals of Delusion: A Benchmarking Audit Study of AI Chatbot Interfaces* — API/interface comparison and temporal instability;
- *Testing the Black Box: Structural Barriers to Independent Evaluation of Consumer-Facing Health LLMs* — reset, personalization, version-opacity, rate-limit, and auditability barriers;
- *Consistency evaluation protocol: A reproducible framework for assessing large language model output repeatability* — repeated-prompt repeatability methodology.

## Confounding rule

A public interface may change through hidden routing, model snapshots, system instructions, safety layers, personalization, experiments, or product updates.

The project may measure observed variation under documented visible conditions. It should **not** infer that a particular hidden component caused that variation without independent evidence.

Observed behavioral change is not automatically equivalent to model drift.

## Current stop and continuation criteria

The standalone methodology effort should stop or merge into existing work if:

1. no replication question adds information beyond existing studies;
2. the proposed contribution depends mainly on being unaffiliated or low-resource rather than on a distinct measurement or evidence contribution;
3. visible deployment state cannot be documented well enough to make a replication auditable;
4. the evidence remains anecdotal despite repeated testing;
5. meaningful evaluation requires privileged access or prohibited automation;
6. the project would need to relabel an established method to justify continuation.

The project may continue if it can define a replication or documentation question with a concrete contribution, for example:

- independently reproducing a published consumer-interface finding under ordinary access constraints;
- documenting a reproducibility failure that published protocols do not capture;
- validating an evidence-recording procedure another unaffiliated evaluator can follow;
- contributing a replication package or negative replication to an existing research line.

## Revised next gate

Do **not** begin a multi-model, multi-account, cross-interface, or weeks-long study yet.

The next gate is:

1. select one published finding or protocol worth independently replicating;
2. explain why that replication would add information;
3. define successful, failed, and inconclusive replication in advance;
4. run a tiny feasibility check only to determine whether the published procedure can be reproduced manually and ethically;
5. preregister a larger replication only if the feasibility gate survives.

## Research standard

> **Prefer a smaller, explicit replication over a broader claim that duplicates existing work.**

Collision auditing is part of the research, not an obstacle to it.