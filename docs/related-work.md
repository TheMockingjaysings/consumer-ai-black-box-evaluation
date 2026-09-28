# Related Work

## Purpose

This document tracks work that constrains, overlaps with, or informs the project. It is not a novelty section written to defend MOTHER. Its purpose is to make clear where the original framing collides with existing research and what remains uncertain.

## Current project question

The active question is:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

The project does **not** currently claim that this question is novel.

## Why the original framing changed

The earlier MOTHER framing centered on authorization boundaries, safe non-completion, instruction conflict, and escalation. A proposed v0.2 direction focused on changing authorization state while keeping the task otherwise similar.

A broader literature review found substantial overlap with existing work on:

- act versus abstain decisions;
- proceed versus hold decisions;
- paired or mirrored cases where small condition changes reverse the correct action;
- least-privilege permission inference;
- ambiguous authorization;
- time-of-use or commit-time authorization;
- authority provenance and delegation;
- sandbox and execution boundaries;
- public and participatory red teaming;
- black-box evaluation of deployed systems.

That overlap is sufficient to reject a broad novelty claim for the authorization-centered direction.

## Closely overlapping research themes

### Agent abstention and proceed/hold decisions

Recent benchmarks evaluate whether agents should act, abstain, proceed, or hold under changing conditions. Some use near-matched or mirror scenarios specifically so that always-acting and always-refusing policies both fail.

This is methodologically close to the earlier MOTHER idea of holding the task nearly constant while changing the state that makes action appropriate or inappropriate.

**Implication:** a three-condition authorized/unauthorized/ambiguous design is not enough by itself to establish a distinct contribution.

### Authorization, least privilege, and permission inference

Existing work studies whether agents infer appropriate permissions, respect authorization constraints, or request more authority than a task requires.

**Implication:** MOTHER should not be framed as discovering that tool-using agents need to distinguish what they may do from what they technically can do.

### Commit-time or time-of-use authorization

Research also examines cases where an action was once authorized but the authority relation changes before a durable action is committed.

**Implication:** changing authorization state while keeping the user goal or action structure similar is already an explicit research construct.

### Authority provenance and delegation

Formal and applied work studies where authority originates, how it is delegated, and whether a requested action remains within that authority.

**Implication:** provenance/delegation is not an open novelty lane simply because it was not part of MOTHER v0.1.

### Public and participatory red teaming

Large public competitions and socio-technical research already demonstrate that outside participants can contribute useful red-team data and failure cases.

**Implication:** the fact that an evaluator is outside a lab or institution is not, on its own, a research contribution.

## Work most relevant to the new direction

The reframed project needs a different literature map. The most relevant work is not simply “AI safety” broadly, but research on the limits of evaluating deployed black-box systems from the outside.

Priority topics include:

- independent auditing of consumer-facing AI systems;
- reproducibility of black-box model evaluations;
- model and product version drift;
- hidden routing and system-layer effects;
- personalization and memory as evaluation confounds;
- A/B testing and interface-level variability;
- longitudinal evaluation of changing AI products;
- reproducibility across accounts, sessions, and evaluators;
- documentation standards for public-interface behavioral evidence;
- limits of mechanistic inference from black-box outputs.

A particularly relevant line of work examines structural barriers to independent evaluation of consumer-facing systems, including difficulty resetting state, hidden personalization, rate limits, version opacity, and evaluation instability. Work from healthcare can be methodologically useful here even though healthcare is out of scope as a test domain.

## Named works already identified during the collision audit

The collision audit has identified the following as directly or indirectly relevant and requiring careful comparison in any future literature review:

- **AgentAbstain** — paired should-act / should-abstain tasks in executable environments.
- **SteerBench-Work** — proceed/hold decisions and evidence-reversed mirror cases.
- **AuthBench** — least-privilege and permission inference for agents.
- **APort Vault** — permitted versus unpermitted tool-level actions with authorization enforcement.
- **FORTIS** — over-selection of authority, skills, or tools beyond task requirements.
- **Agentic Abstention** — abstention behavior in agentic settings.
- **AGATE** and related authority-provenance/delegation work.
- **Temporary Authority, Permanent Effects: Commit-Time Authorization for LLM Agents** — authorization validity at the point of durable action.
- **A Framework for Formalizing LLM Agent Security** — formal treatment of task alignment, action alignment, source authorization, and data isolation.
- **Testing the Black Box: Structural Barriers to Independent Evaluation of Consumer-Facing Health LLMs** — methodological barriers faced by outside evaluators using consumer interfaces.
- **How Vulnerable Are AI Agents to Indirect Prompt Injections? Insights from a Large-Scale Public Competition** — evidence that public participation in agent red teaming is already established.
- **Red Teaming LLMs as Socio-Technical Practice: From Exploration and Data Creation to Evaluation** — red teaming as a socio-technical and participatory practice.
- **NIST ARIA** and other evaluation programs that address real-world model behavior and evaluation practice.

This list is a working map, not a complete bibliography. Each source should be verified and read closely before it is used to support a formal claim.

## What still needs to be searched

The next literature pass should concentrate on the new methodological question rather than continue collecting general authorization papers.

Search targets:

1. methods for reproducible evaluation of continuously updated consumer AI products;
2. black-box auditing where model/version identity is partially hidden;
3. longitudinal replication of LLM behavior;
4. effects of memory, personalization, and account state on evaluation reproducibility;
5. cross-interface and cross-account evaluation methods;
6. external audit protocols designed for researchers without API or platform access;
7. evidentiary standards for reporting behavioral findings when deployment variables are unobservable.

## Claim discipline

The project should not say:

- “No one has studied this.”
- “MOTHER discovered authorization-boundary failure.”
- “The three-condition design is novel.”
- “Public participation in AI red teaming is new.”
- “Black-box evaluation from consumer interfaces is new.”

The strongest defensible statement at present is:

> **The project is investigating whether a practical, reproducible protocol for independent evaluation through ordinary consumer AI interfaces remains useful despite hidden and changing deployment conditions. That usefulness and distinctiveness have not yet been established.**

## Standard for continuing

If a stronger existing method already addresses this question, the project should adopt, replicate, extend, or contribute to that work rather than create a competing label.

If the literature leaves a practical gap, the next step is a small feasibility pilot—not a novelty claim.
