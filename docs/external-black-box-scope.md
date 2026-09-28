# External Evaluation of Consumer AI Under Deployment Opacity

## Status

**Active framing — September 28, 2026**

This document defines the current direction of the project. It replaces the proposed authorization-state-discrimination direction as the active framing. Earlier MOTHER materials remain in the repository as historical artifacts and should not be retroactively rewritten.

## Research question

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

The question is intentionally narrower than the original MOTHER framing. It does not claim that authorization boundaries, abstention, safe non-completion, or escalation are new research problems. They are not.

The project is now about the **epistemic and methodological limits of independent black-box evaluation**.

## Why this is the current question

An outside evaluator usually does not know the complete state of a deployed consumer AI system. Depending on the product, behavior may be affected by model routing, system instructions, memory, personalization, account state, tool availability, interface differences, experiments, safety layers, or silent model updates.

That creates a practical problem: a behavioral observation may be real and reproducible in the moment, yet difficult to attribute to a stable underlying model or reproduce later.

The project therefore asks what evidence can still be collected responsibly under those conditions.

## Population and environment

The intended test environment is **ordinary public-facing AI products available to consumers**.

The project does not require:

- API access;
- privileged developer access;
- model weights;
- system prompts;
- chain-of-thought or hidden reasoning;
- internal safety logs;
- routing metadata;
- proprietary evaluation harnesses.

If a platform exposes useful metadata publicly, it can be recorded. The protocol should not depend on information that an ordinary outside evaluator cannot access.

## Out of scope

For the current phase, this project excludes:

- hospital, clinical, or other internal healthcare deployments;
- patient records or protected health information;
- real financial records or credentials;
- insurance adjudication systems;
- internal enterprise systems;
- high-risk attempts to bypass product safeguards;
- claims about hidden model mechanisms that cannot be externally verified.

Healthcare research may still appear in related work when it reveals a relevant methodological problem, such as version opacity or poor reproducibility. It is not the test domain.

## Candidate protocol dimensions

A future pilot should test whether observations remain stable across controlled changes that an outside evaluator can actually make.

Candidate dimensions include:

### 1. Repeated runs

Repeat the same synthetic scenario under the same visible conditions and record the distribution of outcomes.

### 2. Session state

Compare fresh sessions with continued conversations where context accumulation may matter.

### 3. Memory and personalization

Where controls are available, compare memory or personalization states without using sensitive personal data.

### 4. Account or interface state

Where ethically and practically feasible, compare observable differences across accounts, product surfaces, or interfaces.

### 5. Time

Repeat selected cases later to test for behavioral drift and to document whether the platform exposes a stable model or version identifier.

### 6. Observable metadata

Record the date, time, product surface, visible model label, enabled features, memory state, tools, and any other user-visible configuration that could affect replication.

## What counts as evidence

The unit of evidence is an **observable interaction record** under documented conditions.

A result can support statements such as:

- the system produced behavior X under documented condition Y;
- the behavior occurred in N repeated runs;
- the behavior changed after an observable condition changed;
- later runs did or did not reproduce the earlier result.

A result does **not** by itself support claims such as:

- the model internally reasoned in a particular way;
- a hidden system prompt caused the behavior;
- a specific safety layer or router caused the behavior;
- the same behavior generalizes to all users, accounts, regions, or future versions.

## Reproducibility as a measured property

The project should not treat reproducibility as a yes/no requirement imposed from the outside. Reproducibility itself is part of what is being measured.

Possible outputs include:

- high within-session consistency but poor cross-session consistency;
- stable behavior over repeated runs but drift over time;
- different outcomes under memory/personalization changes;
- inability to identify the model version well enough for later replication;
- evidence that visible product state is insufficient to explain the variance.

Those are potentially useful findings even when the evaluator cannot identify the hidden cause.

## Claims discipline

The project should distinguish four levels explicitly:

1. **Observed:** what the interface actually returned or did.
2. **Reproduced:** whether the observation recurred under documented conditions.
3. **Associated:** whether a visible condition changed alongside the behavior.
4. **Mechanistic:** a claim about why the system behaved that way.

This project can usually support levels 1 and 2. It may sometimes support a cautious level-3 association. It should not make level-4 claims without independent evidence.

## What would make this project unnecessary

The project should not continue as a standalone effort if a stronger existing methodology already provides the same practical protocol for independent evaluators using ordinary consumer interfaces, with comparable attention to version drift, personalization, routing opacity, memory state, and replication over time.

Likewise, if pilot work shows that the uncontrolled deployment variables make the resulting evidence too weak to support useful conclusions, that is a legitimate stopping condition.

## Relationship to MOTHER

MOTHER was the original project name and authorization-centered framing. The literature audit showed that those broad constructs overlap heavily with established and current research.

The present work keeps the useful discipline learned from MOTHER—careful observation, safe non-completion, uncertainty, and restraint in interpretation—but does not present MOTHER's original research question as novel.

The active project is therefore best understood as a **methodology investigation for independent external evaluation**, not as a renamed authorization benchmark.
