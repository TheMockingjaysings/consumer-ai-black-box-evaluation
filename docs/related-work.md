# Related Work

This document provides an initial public map of research and engineering work that overlaps with the Mother Safe Failure Eval.

It is not intended to prove that MOTHER is novel. The opposite is important: many of the underlying safety concerns in this project are already established subjects of research and engineering.

This map is limited to public sources available to an independent researcher. It cannot account for proprietary evaluations, unpublished internal work, private incident analysis, or confidential safety research inside AI companies.

Last reviewed: 2026-09-26.

## 1. Over-refusal and refusal calibration

A central question in MOTHER is whether a system can avoid unsafe action without becoming so cautious that it refuses benign tasks unnecessarily.

Two relevant public benchmarks are:

- **XSTest** (Röttger et al., 2023), which tests exaggerated safety behavior using safe prompts that models may incorrectly refuse, together with unsafe contrast prompts: https://arxiv.org/abs/2308.01263
- **OR-Bench** (Cui et al., 2024), which evaluates over-refusal at larger scale using seemingly harmful but actually benign prompts, plus toxic prompts to discourage indiscriminate compliance: https://arxiv.org/abs/2405.20947

These works overlap with the broader MOTHER concern that safety behavior should be calibrated rather than reduced to "refuse whenever something looks risky."

The frozen MOTHER v0.1 shakedown does **not** yet include matched benign continuation controls, so it should not be treated as an over-refusal benchmark.

## 2. Prompt injection and agent security

Public agent-security work already tests whether models preserve intended behavior when untrusted data or external content attempts to redirect them.

Relevant examples include:

- **AgentDojo** (Debenedetti et al., 2024), a dynamic environment for evaluating prompt-injection attacks and defenses in agents using tools over untrusted data: https://arxiv.org/abs/2406.13352
- **AgentDyn** (Li et al., 2026), which extends prompt-injection evaluation toward more dynamic, open-ended agent tasks: https://arxiv.org/abs/2602.03117
- OpenAI's public guidance on **safety in building agents**, which discusses prompt injection, private-data leakage, tool approvals, guardrails, and trace-based evaluation: https://developers.openai.com/api/docs/guides/agent-builder-safety

These works are more execution-oriented than MOTHER v0.1, which currently uses static hypothetical scenarios rather than live tool use.

## 3. Authorization, permissions, and containment

Authorization and permission boundaries are already explicit concerns in deployed agent systems.

Examples include:

- Anthropic's discussion of **Claude Code sandboxing**, which describes filesystem and network boundaries intended to let an agent act more autonomously inside constrained permissions: https://www.anthropic.com/engineering/claude-code-sandboxing
- Anthropic's later discussion of **agent containment**, including human approval, sandboxes, virtual machines, and egress controls as ways to limit what an autonomous system can do: https://www.anthropic.com/engineering/how-we-contain-claude
- OpenAI's guidance that agent deployments should combine model guardrails with authentication, authorization protocols, access controls, and other standard security mechanisms: https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/

This body of work reinforces that technical capability is not equivalent to authorization.

## 4. Misaligned persistence, reward hacking, and unauthorized behavior

Public evaluations also examine cases where agents continue pursuing an objective in ways that violate constraints or the broader intent of the task.

Relevant OpenAI examples include:

- A cross-lab OpenAI-Anthropic safety evaluation exercise using multi-step agentic environments that test misaligned actions, lying, reward hacking, and attempts to use restricted capabilities: https://openai.com/index/openai-anthropic-safety-evaluation/
- OpenAI's public discussion of monitoring internal coding agents for behaviors such as unnecessary confirmation requests, reward hacking, and unauthorized data transfer: https://openai.com/index/how-we-monitor-internal-coding-agents-misalignment/

These examples overlap with MOTHER's interest in whether task completion pressure causes a system to exceed a boundary rather than stop, disclose the conflict, or escalate.

## 5. Human participation and escalation

MOTHER treats human clarification or escalation as a potentially correct outcome when authorization is missing or conflicting.

A relevant public line of work is **HAS-Bench** (Wu et al., 2026), which evaluates human-agent systems with explicit roles, permissions, communication paths, and action authority, including clarification and control calibration: https://arxiv.org/abs/2607.04329

This is broader and structurally different from MOTHER v0.1, but it shows that human participation, permissions, and escalation are already active evaluation concerns.

## What MOTHER does not currently establish

The existence of this related work means the project should not claim that authorization boundaries, refusal calibration, escalation, prompt-injection resistance, or safe non-completion are new research problems.

The unanswered question is narrower:

> Does the Mother Safe Failure framing and evaluation procedure provide a useful, reproducible signal that is not already captured adequately by existing public evaluations?

That question remains open.

Answering it would require more than the five-scenario v0.1 shakedown. Useful future comparisons could include:

- matched continue-vs-stop controls;
- paraphrased or adversarial variants;
- independently authored scenarios;
- comparison with established public benchmarks;
- human inter-rater reliability;
- live agentic tool-use tests rather than static vignettes.

If later testing shows that MOTHER adds no meaningful signal beyond existing methods, the project should be narrowed, reframed, or discontinued as a distinct evaluation approach.
