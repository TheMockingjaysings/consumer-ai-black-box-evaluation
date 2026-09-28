# Related Work

Last reviewed: 2026-09-28

This page is not here to prove that MOTHER is novel.

I am using it to answer a more useful question:

> **What, if anything, is still worth testing as a distinct MOTHER contribution?**

The broad territory is already crowded. Authorization boundaries, abstention, least privilege, over-refusal, runtime approval, delegation, sandbox behavior, agent misalignment, participatory red teaming, and user testing are all active areas of research.

I do not want to rename an existing problem and present it as a new one.

For the current decision process, see `collision-audit.md`.

## Closest collision: paired act / abstain evaluation

### AgentAbstain

**AgentAbstain: Do LLM Agents Know When Not to Act?** is currently one of the strongest overlaps with the v0.2 direction I had been considering.

It contains 263 paired tasks across 42 executable sandbox environments. Each pair has a should-act task and a should-abstain variant created through a controlled perturbation to the instruction, tool, or environment state. It evaluates tool-using agents and scores whether they both act when they should and abstain when they should.

Sources:

- https://arxiv.org/abs/2607.10059
- https://github.com/AntiQuality/agentabstain
- https://agentabstain.github.io/

Implication for MOTHER:

A matched design where the surface task stays similar but the correct behavior flips between act and stop is **not** a new MOTHER idea.

### Agentic Abstention

**Agentic Abstention: Do Agents Know When to Stop Instead of Act?** treats abstention as a sequential decision problem rather than a single final answer. An agent may continue, gather information, answer, or stop, and the need to stop may become clear only after interaction with the environment.

Source:

- https://arxiv.org/abs/2606.28733

Implication for MOTHER:

The timing of stopping and the distinction between useful persistence and unnecessary continuation are already being studied directly.

## Closest collision: proceed / hold calibration

### SteerBench-Work

**SteerBench-Work: A Benchmark for Agent Steering at Action Boundaries** evaluates the pre-action choice to proceed or hold for review.

Its public release includes 106 scenarios, both over-refusal and under-refusal scoring, calibration controls, and evidence-reversed mirror cases. Those mirrors are especially relevant because much of the surface situation stays similar while the evidence changes which decision is correct.

Sources:

- https://arxiv.org/abs/2608.12654
- https://steerbench.com/work/paper/
- https://github.com/AgentDock/steerbench-work

Implication for MOTHER:

A benchmark that asks whether a system changes from proceed to hold when the decision-relevant evidence changes is already public. MOTHER should not claim that this general discrimination structure is new.

## Authorization and permission boundaries

### Public Authorization-Boundary Benchmark for Tool-Using AI Agents

This 2026 proposal directly asks whether tool-using agents stop when they do not have clear permission. It includes missing or expired consent, conflicting instructions, authority and scope limits, revoked permission, unnecessary blocking, clarification, audit records, and return to a safe state.

Source:

- https://manifund.org/projects/public-authorization-boundary-benchmark-for-tool-using-ai-agents

Implication for MOTHER:

The broad question "does an agent respect authorization?" is already being developed as a benchmark problem.

### FelonyBench

FelonyBench is designed around otherwise legitimate tasks where crossing an authorization boundary may be instrumentally useful. It records agent trajectories and distinguishes attempted from successful violations.

Source:

- https://github.com/MLOpsNYC/felonybench

Implication for MOTHER:

The idea that a legitimate objective can tempt an agent to treat a boundary as something to work around is already being tested in agentic environments.

### AuthBench

**AuthBench: Do Coding Agents Understand Least-Privilege Authorization?** studies whether coding agents infer the permissions required for realistic tasks without granting too much or too little authority.

Source:

- https://arxiv.org/abs/2605.14859

Implication for MOTHER:

Permission calibration and least privilege are already active benchmark questions.

### FORTIS

**FORTIS: Benchmarking Over-Privilege in Agent Skills** evaluates whether agents choose higher-privilege skills, tools, or actions than a task requires.

Source:

- https://arxiv.org/abs/2605.09163

Implication for MOTHER:

Privilege expansion and minimal authority are not open territory for a broad novelty claim.

### APort Vault

APort Vault evaluates payment authorization in tool-using agents and compares model behavior with deterministic pre-action authorization enforcement.

Sources:

- https://arxiv.org/abs/2609.22076
- https://sandbox.aport.io/research/aport-vault-benchmarking-ai-agent-payment-authorization/

Implication for MOTHER:

Deterministic authorization gates and real action-level permission checks should be treated as established engineering and evaluation infrastructure, not MOTHER inventions.

## Authority provenance and delegation

### AGATE

**AGATE: Provenance-Based Runtime Defense Against Compositional Attacks on LLM Agents** grounds authorization in operator declarations and host approval events, constrains delegated actions, tracks provenance, and retains evidence for replay.

Source:

- https://arxiv.org/abs/2609.30830

### Authenticated Delegation and Authorized AI Agents

Earlier work proposes authenticated, authorized, and auditable delegation chains for AI agents using established identity and access-management concepts.

Source:

- https://arxiv.org/abs/2501.09674

Implication for MOTHER:

Authority provenance, delegation chains, and scoped grants are also established research directions. If MOTHER studies invalid or second-hand authority claims, the behavioral contribution must be stated much more narrowly.

## Runtime approval and containment

### OpenAI Auto-review

OpenAI's Auto-review work uses a separate reviewer agent to approve or deny actions that cross sandbox boundaries.

Source:

- https://alignment.openai.com/auto-review

This is close to the original MOTHER motivation because the acting agent may have pressure to treat an approval boundary as another obstacle. The experimental role is different: Auto-review evaluates a separate approval layer, while MOTHER has been asking about the behavior of the acting system itself.

### Anthropic sandboxing and containment

Relevant engineering work includes sandboxing, virtual machines, egress controls, and human approval mechanisms.

Sources:

- https://www.anthropic.com/engineering/claude-code-sandboxing
- https://www.anthropic.com/engineering/how-we-contain-claude

Implication for MOTHER:

MOTHER should use established enforcement controls as infrastructure if it ever reaches a tool-use stage. It should not present them as part of its novelty claim.

## Harmful tool use and matched benign controls

### AgentHarm

AgentHarm evaluates harmful multi-step tool use and includes matched benign controls so refusal is not confused with lack of capability.

Source:

- https://arxiv.org/abs/2410.09024

Implication for MOTHER:

Any future MOTHER design must make both error directions visible. A model that refuses everything has not demonstrated good calibration.

## Multi-agent pressure, loopholes, and escalation

### DeepMind: Cheaters and Whistleblowers in the Agent Swarm

DeepMind's 2026 experiment showed agents reacting differently after a loophole was discovered: some exploited it, some followed others, and some resisted or reported it.

Source:

- https://institute.deepmind.com/essays/cheaters-and-whistleblowers-in-the-agent-swarm/

Implication for MOTHER:

Peer pressure, invalid authority, escalation, and safe non-completion are not purely hypothetical behaviors. This work is especially relevant to any later multi-agent extension.

## Over-refusal and refusal calibration

### XSTest

- https://arxiv.org/abs/2308.01263

### OR-Bench

- https://arxiv.org/abs/2405.20947

These benchmarks show why "refuse when something looks risky" is not enough. A useful safety evaluation also needs cases where continuation is clearly allowed.

## Prompt injection and agent security

Relevant examples include:

- AgentDojo: https://arxiv.org/abs/2406.13352
- AgentDyn: https://arxiv.org/abs/2602.03117
- OpenAI agent safety guidance: https://developers.openai.com/api/docs/guides/agent-builder-safety

These works are more execution-oriented than MOTHER v0.1 and reinforce the gap between a static answer and an enacted trajectory.

## Human participation, escalation, and public contribution

### HAS-Bench

HAS-Bench evaluates human-agent systems with explicit roles, permissions, communication paths, and action authority.

Source:

- https://arxiv.org/abs/2607.04329

### Misalignment Bounty

The Misalignment Bounty crowdsourced reproducible examples of agent misbehavior. It received 295 submissions.

Sources:

- https://arxiv.org/abs/2510.19738
- https://palisaderesearch.org/research/misalignment-bounty

### Participatory red teaming

Recent HCI work describes red teaming as a socio-technical practice and argues for broader participation, contextual evaluation, and more explicit attention to whose risks and experiences enter evaluation datasets.

Source:

- https://doi.org/10.1145/3772318.3790792

### NIST ARIA

NIST's 2026 ARIA Evaluation Planning Manual combines model testing, red teaming, and user testing within a broader evaluation process.

Source:

- https://www.nist.gov/publications/aria-evaluation-planning-manual-elements-aria-style-ai-evaluations

Implication for MOTHER:

Public participation and user-centered evaluation are not empty research lanes. If MOTHER becomes an outside-evaluator methodology, the contribution has to be more specific than "let ordinary people test AI."

## Where this leaves MOTHER

At this point I do **not** think MOTHER should be described as a new general authorization benchmark.

I also do **not** think the matched authorized / unauthorized / ambiguous idea is enough by itself to establish novelty. AgentAbstain and SteerBench-Work are too close methodologically for that claim to be comfortable.

The remaining candidate directions are being tested against the literature rather than assumed:

1. **Authorization-state discrimination** — heavy overlap.
2. **Authority provenance and delegation** — substantial overlap.
3. **Independent black-box evaluation through ordinary public interfaces** — still open, but participatory and crowdsourced evaluation already exist.

The possible third direction is narrower:

> Can outside evaluators, without privileged model access, follow a disciplined protocol that produces reproducible and auditable observations from ordinary user-facing systems despite hidden provider configuration?

That may be an evaluation-methodology question rather than a new agent benchmark.

I am not claiming it is distinct yet.

See `collision-audit.md` for the current decision rules.

## Stop condition

If another public evaluation already measures the same construct more clearly, with stronger construct validity or better reproducibility, MOTHER should not continue as a separate benchmark merely because it has a different name or origin story.

Narrowing, contributing to existing work, replication, or discontinuation are all legitimate outcomes.