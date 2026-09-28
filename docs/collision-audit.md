# MOTHER Collision Audit

Last reviewed: 2026-09-28

I started this audit because I did not want to keep moving the novelty line every time I found another paper.

The original MOTHER question was about authorization boundaries, safe non-completion, escalation, and the difference between persistence and overreach. That question still matters. It is also already being studied directly by other researchers in ways that are broader, more mature, and in some cases more technically rigorous than what I had planned for v0.2.

That changes what I think MOTHER should claim.

I am no longer treating authorization-state discrimination, abstention, least privilege, authority provenance, or public red teaming as open territory that MOTHER discovered. Those ideas are now background and related work.

Version 0.1 stays frozen as a historical shakedown. I am not freezing a new v0.2 benchmark.

The live question is now narrower:

> **Can an independent evaluator produce reproducible, auditable behavioral evidence from ordinary public AI interfaces when the underlying deployment may change in ways the evaluator cannot see or control?**

I am not claiming that this question is novel either. The point of the audit is to find out whether there is actually something useful left to contribute.

## What the authorization review settled

### AgentAbstain

**AgentAbstain: Do LLM Agents Know When Not to Act?** uses 263 paired tasks across 42 executable sandbox environments. Each pair contains a should-act task and a should-abstain version created through a controlled change to the instruction, tool, or environment state.

Sources:

- https://arxiv.org/abs/2607.10059
- https://github.com/AntiQuality/agentabstain

For MOTHER, the implication is straightforward: I should not claim that paired act-versus-stop testing is new.

### SteerBench-Work

**SteerBench-Work: A Benchmark for Agent Steering at Action Boundaries** evaluates the pre-action decision to proceed or hold. It includes over-refusal and under-refusal scoring and evidence-reversed mirror cases where much of the situation stays the same while the decision-relevant evidence changes.

Sources:

- https://arxiv.org/abs/2608.12654
- https://steerbench.com/work/paper/
- https://github.com/AgentDock/steerbench-work

Again, the implication is clear: a matched proceed-versus-hold design is not a distinct MOTHER contribution by itself.

### Other overlapping work

The same pattern continues across related work on:

- agentic abstention;
- least privilege;
- authorization boundaries;
- runtime approval;
- authority provenance and delegation;
- containment and sandboxing;
- public red teaming;
- participatory evaluation; and
- crowdsourced failure collection.

Relevant examples include Agentic Abstention, FORTIS, AuthBench, APort Vault, AGATE, the Public Authorization-Boundary Benchmark proposal, OpenAI Auto-review, AgentHarm, Misalignment Bounty, and NIST ARIA.

The lesson is not that the original concern was wrong. The lesson is that I was entering an area where a lot of serious work was already underway.

## What remains worth auditing

The only live candidate direction right now is **independent external black-box reproducibility**.

The question is not:

> Can ordinary people test AI?

That is already established in different forms.

The question I care about is more specific:

> **How much can an outside evaluator actually claim when testing a public AI system whose routing, hidden instructions, personalization, model version, and deployment state may not be visible or stable?**

That turns the project away from inventing another authorization benchmark and toward evaluating the evaluation condition itself.

## Why this may still matter

An outside evaluator can usually document the prompt, response, date, displayed model name, visible settings, session state, and some interface conditions.

They may not know:

- which exact model build served the request;
- whether routing changed;
- whether hidden policy layers changed;
- whether memory or personalization influenced the result;
- whether an A/B test or deployment experiment was active;
- whether two sessions with the same visible label were actually comparable; or
- whether the provider updated the system between runs without exposing a stable version identifier.

That creates a basic reproducibility problem.

The question is whether a disciplined external protocol can document those limits well enough that the evidence is still useful without overstating what happened.

## Scope for this audit

For now, I am limiting the project to:

- public consumer-facing AI interfaces;
- synthetic or non-sensitive test material;
- no protected health information or patient records;
- no real financial records or credentials;
- no privileged hospital, insurer, employer, or enterprise access;
- no reverse engineering of private systems; and
- no claims about hidden mechanisms that cannot be observed from the outside.

Healthcare may remain in the literature review because it exposes the black-box reproducibility problem clearly. It is not the MOTHER test domain.

## Questions I still need to answer

Before I build anything new, I need to know:

1. What work already exists on independent evaluation through ordinary consumer interfaces?
2. How do those studies handle model version drift, personalization, routing, memory, and interface state?
3. What metadata are actually necessary for a replication attempt to be meaningful?
4. When two runs disagree, can the protocol separate model variability from a changed evaluation condition?
5. Can a second evaluator reproduce an observation closely enough for the result to be useful?
6. When should an external evaluator say, "I observed this," rather than "this model behaves this way"?
7. Does a structured protocol add enough value beyond normal transcript preservation and red teaming to justify a separate method?

## What would weaken this direction

This direction should narrow or stop if:

- existing methods already solve the same external-interface reproducibility problem better;
- hidden deployment variables make comparisons too underdetermined to interpret;
- the proposed protocol mostly records metadata without changing what can reasonably be concluded;
- independent replication fails even when visible conditions are matched as closely as possible; or
- the distinction depends more on terminology than on an observable measurement.

## What stays unchanged

The frozen `evals/pilot-v0.1.md` stays frozen.

The earlier concept papers remain part of the project history. I am not rewriting them to make it look as if MOTHER always had this newer direction.

If the external black-box question survives the audit, it should get a new concept-paper version and a separately versioned protocol.

## What would count as a good outcome

A good outcome is not proving that MOTHER is unique.

A good outcome could be:

- finding a genuinely useful external-evaluation method;
- producing a careful replication protocol;
- contributing the method to an existing evaluation project;
- documenting where public-interface evaluation becomes too uncertain for strong claims; or
- concluding that the remaining question is already better answered elsewhere.

I would rather end up with a smaller claim that I can defend than a larger one that falls apart under review.