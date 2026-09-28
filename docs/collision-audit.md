# Collision Audit

## Status

**Second collision audit active — September 28, 2026**

This document records two distinct audits:

1. why the project moved away from an authorization-centered benchmark; and
2. whether the replacement framing around external black-box reproducibility is itself already covered by existing work.

## Audit 1 — Historical authorization-centered direction

### Original direction

The original project explored authorization boundaries, safe non-completion, instruction conflict, and escalation in public AI systems. A proposed next step was to compare closely matched authorized, unauthorized, and ambiguous variants of the same task.

### Finding

**Assessment: heavy overlap with existing research.**

Closely related work already studies act/abstain decisions, proceed/hold behavior, ambiguous authorization, least privilege, time-of-use authorization, authority provenance, delegation, tool-use constraints, sandbox boundaries, and public red teaming.

### Decision

The project will not proceed as a new general authorization benchmark unless a later review identifies a specific gap not already measured more rigorously elsewhere.

The historical five-scenario shakedown remains preserved as an instrument-development record.

## Audit 2 — Active external-evaluation framing

The broad replacement area is:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

That is now treated as a **research area**, not as a sufficiently narrow experimental question and not as a novelty claim.

### Why a second audit is necessary

Black-box evaluation, nondeterminism, model drift, endpoint stability, model fingerprinting, external auditing, and consumer-interface evaluation are established or active research areas.

The current project therefore needs to determine whether there is any useful practical gap left for an independent evaluator working through ordinary consumer interfaces.

### Priority collision categories

The second audit should search for substantially equivalent methods covering:

1. repeated presentation of identical prompts and run-to-run variance;
2. behavioral stability or drift over time;
3. black-box endpoint stability and behavioral fingerprinting;
4. evaluation when model or version identity is hidden or unstable;
5. differences between API evaluation and consumer-product behavior;
6. routing, system-layer, safety-layer, or product-surface confounds;
7. memory and personalization as evaluation confounds;
8. cross-session, cross-account, and cross-interface reproducibility;
9. protocols designed for outside evaluators without privileged access;
10. evidentiary standards for claims drawn from changing public AI products.

## Candidate narrow measurement

If the second audit leaves a useful gap, the first candidate measurement is:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

This is intentionally narrower than the broad research area.

The historical authorization scenarios may be reused as probes, but in that role they are measurement instruments rather than the construct being claimed as novel.

## Confounding rule

A public interface may change through hidden routing, model snapshots, system instructions, safety layers, personalization, experiments, or product updates.

The project may measure observed variation under documented visible conditions. It should **not** infer that a particular hidden component caused that variation without independent evidence.

Observed behavioral change is not automatically equivalent to model drift.

## Falsification and stop criteria

The project should narrow, replicate existing work, contribute elsewhere, or stop as a standalone effort if any of the following is established:

1. Existing work already provides a substantially equivalent practical protocol and there is no useful replication gap.
2. The candidate outcome cannot be defined or coded consistently.
3. Visible deployment state cannot be documented well enough to make the procedure auditable.
4. Repeated testing produces evidence no stronger than isolated anecdotes.
5. Hidden deployment variation makes the planned within-condition measurement uninterpretable.
6. The proposed contribution depends mainly on a new name, acronym, framing, or presentation format.
7. Answering the research question requires privileged access unavailable to an independent evaluator.

## What would count as progress

Progress and confirmation are not the same thing.

Progress can include:

- identifying that the candidate measurement is already covered and redirecting accordingly;
- producing a coherent coding scheme that survives a feasibility shakedown;
- discovering that the measurement is too ambiguous and stopping;
- preregistering a narrow repeated-run study with a fixed decision rule;
- measuring variance under documented conditions;
- producing a replication package another evaluator can follow.

A negative or null result may be informative, but it does not automatically support the same hypothesis as a positive result.

## Current decision gate

Do **not** begin a multi-model, multi-account, cross-interface, or weeks-long repeated-run study yet.

The next gate is:

1. complete the second collision audit;
2. define one observable outcome and coding method;
3. run a tiny manual feasibility shakedown;
4. only then preregister a formal repeated-run study if the measurement survives.

## Research standard

> **Prefer a smaller, falsifiable claim over a broader claim that cannot survive criticism.**

The collision audit is part of the research, not an obstacle to it.