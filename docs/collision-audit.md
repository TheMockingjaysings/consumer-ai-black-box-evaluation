# MOTHER Collision Audit

Last reviewed: 2026-09-28

I am doing this audit because I do not want to keep moving the novelty line every time I find another paper.

The broad ideas behind MOTHER — authorization boundaries, safe non-completion, calibrated refusal, human escalation, least privilege, and agent behavior around blocked actions — are already active research areas. Some newer public work is also very close to the narrower matched-condition design I had started considering for v0.2.

That changes the next step.

I am **not freezing v0.2 yet**.

Before I decide whether MOTHER should remain a distinct evaluation, I want to answer a harder question:

> **Is there still a useful signal here that is not already measured better by existing public work?**

If the answer is no, I would rather narrow the project, contribute useful pieces to an existing approach, or stop treating MOTHER as a separate benchmark than manufacture a novelty claim.

## The strongest collision I have found so far

### AgentAbstain

**AgentAbstain: Do LLM Agents Know When Not to Act?** uses 263 paired tasks across 42 executable sandbox environments. Each pair contains a should-act task and a should-abstain version created by a controlled perturbation to the instruction, tool, or environment state.

Sources:

- https://arxiv.org/abs/2607.10059
- https://github.com/AntiQuality/agentabstain

This is a major collision with the idea of testing nearly identical tasks where the correct behavior changes from act to abstain. It also evaluates actual tool-using agents rather than static text alone.

MOTHER should **not** claim that paired act-versus-stop evaluation is new.

### SteerBench-Work

**SteerBench-Work: A Benchmark for Agent Steering at Action Boundaries** evaluates the pre-action choice to proceed or hold for review. Its public release includes 106 workplace scenarios, over-refusal and under-refusal scoring, calibration controls, and evidence-reversed mirror cases where the surrounding situation remains similar but the evidence changes the correct decision.

Sources:

- https://arxiv.org/abs/2608.12654
- https://steerbench.com/work/paper/
- https://github.com/AgentDock/steerbench-work

This is especially close to the MOTHER v0.2 idea because the mirror cases test whether a system changes its decision when evidence changes while much of the surface situation stays the same.

MOTHER should **not** claim that matched proceed-versus-hold discrimination is new.

### Agentic Abstention

**Agentic Abstention: Do Agents Know When to Stop Instead of Act?** treats abstention as a sequential decision problem. It evaluates when agents should continue interacting, gather more information, answer, or stop across more than 28,000 tasks.

Source:

- https://arxiv.org/abs/2606.28733

This overlaps with MOTHER's interest in the timing of stopping and the difference between useful persistence and unnecessary continuation.

### FORTIS

**FORTIS: Benchmarking Over-Privilege in Agent Skills** evaluates whether agents select more authority, skills, tools, or actions than a task actually requires.

Source:

- https://arxiv.org/abs/2605.09163

This is relevant to MOTHER's earlier least-privilege and authority-expansion framing.

### AGATE

**AGATE: Provenance-Based Runtime Defense Against Compositional Attacks on LLM Agents** uses deterministic runtime checks that ground authorization in operator declarations and approval events, constrain delegated actions, and preserve provenance for later reconstruction.

Source:

- https://arxiv.org/abs/2609.30830

This is not the same experiment as MOTHER, but it makes authority provenance and delegation a much less open research lane than it first appeared.

### Authenticated delegation and authorized agents

There is also earlier work on explicit delegation chains, auditable authority, agent credentials, and scoped permissions.

Source:

- https://arxiv.org/abs/2501.09674

MOTHER should not claim that provenance of authority or delegation itself is new.

## Public and non-specialist participation is not an empty lane either

The idea of involving people outside AI laboratories also has prior work.

### Misalignment Bounty

The **Misalignment Bounty** crowdsourced reproducible examples of agent misbehavior from public contributors. It received 295 submissions.

Sources:

- https://arxiv.org/abs/2510.19738
- https://palisaderesearch.org/research/misalignment-bounty

### Participatory red teaming

Recent HCI work treats red teaming as a socio-technical practice and argues for broader participation, domain expertise, contextual evaluation, and more explicit attention to how datasets and risk categories are created.

Source:

- https://doi.org/10.1145/3772318.3790792

### NIST ARIA

NIST's 2026 ARIA Evaluation Planning Manual explicitly combines model testing, red teaming, and user testing as parts of a broader AI evaluation process.

Source:

- https://www.nist.gov/publications/aria-evaluation-planning-manual-elements-aria-style-ai-evaluations

So MOTHER should not claim that outside-user participation, public red teaming, or user-centered evaluation is a new idea either.

## The three candidate directions I am auditing

### 1. Authorization-state discrimination

Candidate question:

> If the underlying task stays essentially the same and the authorization state changes, does the system change its behavior appropriately?

Current status: **heavy overlap**.

AgentAbstain and SteerBench-Work already cover closely related paired or mirrored act-versus-hold decisions. A three-way authorized / unauthorized / ambiguous structure may still be useful, but "three conditions instead of two" is not enough by itself to justify a new benchmark.

Before this becomes v0.2, I need to identify a measurement or failure mode that those evaluations do not already capture well.

### 2. Authority provenance and delegation

Candidate question:

> Does the system distinguish valid authority from unsupported, expired, delegated, conflicting, or second-hand claims of authority?

Current status: **substantial overlap**.

Authorization frameworks, delegation research, AGATE, permission benchmarks, and runtime gates already cover important parts of this problem.

A narrower behavioral question may remain around how user-facing systems react to competing authority claims, but that needs a direct comparison before I treat it as a distinct contribution.

### 3. Independent black-box evaluation by outside users

Candidate question:

> Can people without privileged model access use a disciplined public protocol to produce reproducible, auditable observations about authorization and action-boundary failures in user-facing AI systems?

Current status: **still open, but not obviously novel**.

Crowdsourced red teaming and participatory evaluation already exist. The possible MOTHER contribution would have to be more specific than "let nontechnical people test AI."

The question I still want to investigate is whether a tightly controlled protocol can make observations from ordinary public interfaces comparable enough to be useful despite hidden system prompts, routing, model updates, personalization, and other confounders that outside evaluators cannot see.

That would make MOTHER less of a new agent benchmark and more of an **independent evaluation methodology**.

I am not claiming that contribution yet.

## Decision rules before v0.2

I do not want v0.2 frozen until this audit is complete enough to answer the following:

1. What exact construct would v0.2 measure?
2. Which existing benchmark is the closest comparator?
3. What observable information would MOTHER add that the comparator does not already provide?
4. Can that difference be tested rather than argued rhetorically?
5. Does the proposed method work from an external black-box position without pretending to know hidden mechanisms?
6. Can an independent person reproduce the procedure from the public documentation?

If I cannot answer those questions convincingly, v0.2 should not move forward as a separate benchmark.

## What stays unchanged

The frozen `evals/pilot-v0.1.md` remains unchanged.

Version 0.1 is an instrument shakedown and a record of the project's development. New related work does not justify silently rewriting a frozen protocol after testing has begun.

The current concept paper also remains part of the version history. If MOTHER survives this collision audit in a narrower form, the conceptual framing should be updated in a new version rather than rewriting the old one.

## What would count as a good outcome

A good outcome is not necessarily proving that MOTHER is unique.

A good outcome could be:

- finding a genuinely distinct, testable signal and building v0.2 around it;
- contributing a useful scenario, scoring idea, or outside-evaluator method to an existing project;
- reframing MOTHER as an independent replication or public-interface audit method rather than a new benchmark; or
- deciding that the distinct benchmark idea has been overtaken by stronger work and documenting that clearly.

I would rather end up with a smaller claim that survives criticism than a larger claim that does not.