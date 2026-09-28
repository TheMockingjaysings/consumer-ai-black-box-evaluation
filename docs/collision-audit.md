# Collision Audit

## Status

**Active audit — September 28, 2026**

This document records why the project moved away from an authorization-centered benchmark and what must be established before any new research contribution is claimed.

## What changed

The original project explored authorization boundaries, safe non-completion, instruction conflict, and escalation in public AI systems. A proposed next step was to compare closely matched authorized, unauthorized, and ambiguous variants of the same task.

That direction is now on hold because the surrounding research landscape is substantially more developed than the early project framing suggested.

Existing work already studies closely related problems, including:

- act versus abstain decisions;
- proceed versus hold decisions;
- ambiguous or insufficient authorization;
- least-privilege permission inference;
- time-of-use or commit-time authorization;
- authority provenance and delegation;
- tool-use constraints and sandbox boundaries;
- public and participatory red teaming;
- black-box evaluation of deployed systems.

The exact details differ across papers and benchmarks, but the overlap is sufficient that this project should not present authorization-state discrimination as a novel contribution merely because it uses a different label or a three-condition structure.

## Decision

The active project will **not** proceed as a new general authorization benchmark unless a later review establishes a specific, defensible gap that is not already measured more rigorously elsewhere.

The current candidate question is instead:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This is a methodological question about external evaluation under deployment opacity, not a claim that black-box evaluation itself is new.

## Collision categories

### 1. Authorization-state discrimination

**Assessment: heavy overlap.**

Matched act/abstain and proceed/hold designs already exist. Ambiguous authorization and permission-sensitive behavior are also being studied directly. A three-way authorized/unauthorized/ambiguous structure is not, by itself, enough to justify a separate benchmark.

### 2. Authority provenance and delegation

**Assessment: active existing research area.**

There is already work formalizing where authority comes from, whether delegation is valid, and whether an action remains authorized at execution time. This is not a clean novelty lane for the project.

### 3. Public or participatory red teaming

**Assessment: established.**

Outside contributors and public competitions are already used to discover model and agent failures at scale. The project should not claim that participation by non-institutional evaluators is new.

### 4. Independent evaluation through ordinary consumer interfaces

**Assessment: still under audit.**

The remaining question is narrower: what evidentiary quality is realistically achievable when an evaluator lacks API-level control and cannot fully observe routing, model versions, hidden instructions, memory, personalization, experiments, or safety layers?

This direction has relevant prior work and should not be called novel yet. The audit must specifically search for methodologies that already address:

- reproducibility across repeated consumer-interface runs;
- session and conversation-state effects;
- memory and personalization effects;
- hidden or changing model versions;
- routing or product-surface differences;
- replication over time;
- external documentation standards for black-box behavioral evidence;
- limits on causal or mechanistic claims from public-interface observations.

## Falsification criteria

The project should narrow further, contribute to existing work, or stop as a standalone effort if any of the following is true:

1. Existing research already provides a substantially equivalent protocol for independent evaluators using ordinary public AI interfaces.
2. The uncontrolled deployment variables make results too unstable to support useful behavioral claims.
3. The project can produce observations but no reproducible or auditable evidence beyond anecdotal screenshots.
4. The proposed contribution depends mainly on a new name, acronym, number of conditions, or presentation format rather than a genuinely different methodological capability.
5. The project would need privileged access to answer the question it claims to answer.

## What would count as progress

Progress does not require proving novelty. Useful outcomes include:

- a practical external-evaluation protocol with clearly bounded claims;
- evidence about how reproducibility degrades across visible deployment conditions;
- a taxonomy of uncontrolled variables that matter for outside evaluators;
- a replication package that documents public-interface observations without overstating causation;
- a case study showing that the approach is too unstable or too limited to justify stronger claims;
- a documented decision to stop or merge the work into an existing research line.

## Research standard

The rule for this project is simple:

> **I would rather end up with a smaller claim that survives criticism than a larger claim that does not.**

The audit is therefore not a hurdle to get around. It is part of the research.
