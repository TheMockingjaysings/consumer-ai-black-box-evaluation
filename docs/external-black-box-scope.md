# External Evaluation of Consumer AI Under Deployment Opacity

## Status

**Active framing — September 28, 2026**

This document defines the current direction of the project. Earlier MOTHER materials remain in the repository as historical artifacts and should not be retroactively rewritten.

## Broad research area

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This remains a broad methodological area. It is not yet the experimental question for a formal study.

The project is not presented as a novel authorization benchmark and does not claim that black-box evaluation, model drift, nondeterminism, or external auditing are new topics.

## Candidate first experimental question

Before attempting a broad study, the project will determine whether one narrow behavioral measurement is feasible:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

This candidate question names an observable dependent variable: **behavioral outcome category across repeated runs**.

The first quantity of interest is **within-condition consistency**. The goal is not yet to explain why variation occurs.

## What is held fixed

As far as the public interface permits, the initial measurement should hold constant:

- exact probe text;
- fresh-session status;
- visible model or product label;
- interface or product surface;
- memory/personalization state where visible and controllable;
- tool or connector availability where visible;
- other user-visible settings that could plausibly affect the run.

The project cannot assume that hidden deployment state is fixed merely because visible state appears unchanged.

## What is measured

Each run should produce:

1. the exact model response or observable interface behavior;
2. the visible configuration metadata recorded at the time of the run;
3. a predefined behavioral outcome category;
4. an ambiguity note if the output cannot be coded cleanly.

The raw interaction record should be preserved wherever sharing is permitted.

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

## Feasibility before preregistration

The next experiment is not a large study. It is a small manual shakedown designed to test whether the measurement itself is coherent.

The shakedown should answer:

- Can the exact probe be presented consistently?
- Can visible state be logged reliably?
- Can the outcome categories be applied without repeated ad hoc changes?
- Can ambiguous cases be identified rather than forced into a category?
- Is the evidence record sufficient for another person to inspect?

The exact probe, coding scheme, repetition count, time window, product set, and reproducibility threshold are **not yet frozen**.

Those values should only be preregistered after the feasibility shakedown and must then be frozen before confirmatory data collection.

## Relationship to historical authorization scenarios

Historical authorization scenarios may be reused as fixed probes if they are useful because they can produce distinguishable observable outcomes such as proceed, refuse, or request clarification.

In that role, they are measurement instruments. Their reuse does **not** establish a new authorization construct or revive the earlier novelty claim.

## What counts as evidence

The project can support claims such as:

- behavior X occurred under documented visible condition Y;
- outcome category X occurred in a stated number of repeated runs;
- repeated runs did or did not produce the same predefined category;
- a later preregistered replication did or did not reproduce the earlier pattern.

The project cannot infer from those observations alone that:

- the underlying model changed;
- a router caused the difference;
- a system prompt caused the difference;
- a safety layer caused the difference;
- the system internally reasoned in a particular way.

## Falsifiability and decision rules

A future formal study must state in advance what would count as:

- sufficiently reproducible to justify the planned claim;
- insufficiently reproducible;
- inconclusive.

The threshold should be selected before confirmatory observations are collected, not retrofitted to the resulting data.

A negative result may still be informative, but it does not automatically count as evidence for the same hypothesis.

## Current findings

**None yet under the active framing.**

The current work is methodology development and collision auditing.

## Population and environment

The intended environment is ordinary public-facing AI products available to consumers.

The project does not require API access, model weights, hidden system prompts, chain-of-thought, routing metadata, proprietary logs, or internal developer access.

## Out of scope

For the current phase:

- hospital, clinical, or internal healthcare deployments;
- patient records or protected health information;
- real financial records or credentials;
- insurance adjudication systems;
- internal enterprise systems;
- attempts to bypass safeguards or access controls;
- mechanistic claims unsupported by external evidence.

## Relationship to MOTHER

MOTHER was the historical authorization-centered phase. The active project keeps the discipline of bounded claims and explicit uncertainty, but it is no longer presented as an authorization benchmark.

The current project is best understood as a **methodology investigation into what can be measured reliably from public consumer AI interfaces under deployment opacity**.