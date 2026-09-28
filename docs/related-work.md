# Related Work

## Purpose

This document tracks work that constrains, overlaps with, or may make the project unnecessary.

It is not a novelty-defense document. Its purpose is to identify collisions early enough that the project can narrow, replicate, contribute elsewhere, or stop.

## Historical collision

The original MOTHER framing centered on authorization boundaries, safe non-completion, instruction conflict, and escalation.

A broader literature review found substantial overlap with existing work on:

- act versus abstain decisions;
- proceed versus hold decisions;
- paired or mirrored cases where small condition changes reverse the correct action;
- least-privilege permission inference;
- ambiguous authorization;
- time-of-use or commit-time authorization;
- authority provenance and delegation;
- sandbox and execution boundaries;
- public and participatory red teaming.

That overlap is sufficient to reject a broad novelty claim for the authorization-centered direction.

## Active research area

The current broad area is:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This is not currently treated as a novel research question. It is a broad area that still requires a second collision audit.

## Candidate first measurement

If the second collision audit leaves a useful practical gap, the first candidate measurement is:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

This narrows the initial dependent variable to repeated behavioral outcome consistency.

A historical authorization scenario may be used as a fixed probe, but authorization is not the claimed contribution in that experiment.

## Closely overlapping themes already identified

### Agent abstention and proceed/hold decisions

Recent work evaluates whether agents should act, abstain, proceed, or hold under changing conditions. Some designs use near-matched cases so that always-acting and always-refusing policies both fail.

**Implication:** a three-condition authorization design is not enough to establish a distinct benchmark contribution.

### Authorization, least privilege, and permission inference

Existing work studies whether agents infer appropriate permissions, respect authorization constraints, or request more authority than a task requires.

**Implication:** the project should not claim to have discovered the need for authorization-sensitive behavior.

### Commit-time authorization and authority provenance

Existing research examines whether authorization remains valid when a durable action is actually executed and where delegated authority originates.

**Implication:** changing authorization state or tracing authority provenance is not a clean novelty lane by itself.

### Public and participatory red teaming

Outside contributors and public competitions are already used to discover model and agent failures.

**Implication:** independent participation is not itself a research contribution.

## Second collision audit — priority topics

The active literature pass should now focus on the replacement framing rather than collect more general authorization papers.

Priority topics:

1. repeated-run nondeterminism in LLM outputs;
2. behavioral stability and drift over time;
3. black-box endpoint stability and behavioral fingerprinting;
4. external auditing of continuously changing AI systems;
5. consumer-interface versus API evaluation differences;
6. hidden routing and product-layer confounds;
7. memory and personalization effects on reproducibility;
8. cross-session, cross-account, and cross-interface replication;
9. evaluation under hidden or changing model-version identity;
10. documentation standards for black-box behavioral evidence.

The central question is not whether each topic exists. It is whether existing work already provides a practical protocol sufficiently close to the one this project proposes.

## Named works already identified during the earlier audit

The earlier collision audit identified several works or research lines relevant to the historical authorization framing and to independent evaluation, including:

- **AgentAbstain**;
- **SteerBench-Work**;
- **AuthBench**;
- **APort Vault**;
- **FORTIS**;
- work on **Agentic Abstention**;
- **AGATE** and related authority-provenance/delegation work;
- **Temporary Authority, Permanent Effects: Commit-Time Authorization for LLM Agents**;
- **A Framework for Formalizing LLM Agent Security**;
- **Testing the Black Box: Structural Barriers to Independent Evaluation of Consumer-Facing Health LLMs**;
- public-competition work on indirect prompt injection;
- socio-technical red-teaming research;
- **NIST ARIA** and related evaluation programs.

This remains a working map rather than a complete bibliography. Sources should be verified and read closely before they support a formal claim.

## Claim discipline

The project should not say:

- “No one has studied this.”
- “The project discovered authorization-boundary failure.”
- “Black-box evaluation from consumer interfaces is new.”
- “Run-to-run variation means the underlying model changed.”
- “A visible model label uniquely identifies a stable deployment.”
- “Any negative result validates the project.”

The strongest defensible statement at present is:

> **The project is investigating whether one narrowly defined behavioral measurement can be collected reproducibly from ordinary public AI interfaces despite hidden deployment variables, and whether that practical measurement adds anything useful beyond existing methods.**

## Standard for continuing

The project should proceed to a formal repeated-run study only if:

1. the second collision audit leaves a useful practical gap;
2. one observable dependent variable can be defined clearly;
3. a small feasibility shakedown shows that the procedure and coding are coherent; and
4. the formal study can be preregistered with a fixed decision rule.

If those conditions are not met, the correct next step is to narrow, replicate existing work, contribute elsewhere, or stop.