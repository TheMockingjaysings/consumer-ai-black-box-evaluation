# Related Work

This document maps public research and engineering work that overlaps with MOTHER.

I am not using this page to argue that MOTHER is novel. I am using it to figure out what, if anything, MOTHER should still test as a distinct evaluation.

That distinction matters more now because several public projects are already testing authorization boundaries, least-privilege permissions, sandbox behavior, harmful agent actions, and execution-time approval. I do not want to rename an existing problem and present it as a new one.

This review is limited to public sources available to an independent researcher. I cannot compare MOTHER with proprietary evaluations, unpublished internal work, private incident analysis, or confidential safety research inside AI companies.

Last reviewed: 2026-09-28.

## The closest overlaps

### Public Authorization-Boundary Benchmark for Tool-Using AI Agents

A public August 2026 proposal by Daniel Craig asks a very direct question: when an AI agent can take actions, will it stop when it does not have clear permission?

The proposed benchmark covers missing or expired consent, conflicting instructions, uncertain authority, scope and budget limits, revoked permission, unnecessary blocking, clarification, audit records, and return to a safe state. It also proposes comparing prompt-only behavior with deterministic authorization checks.

Source: https://manifund.org/projects/public-authorization-boundary-benchmark-for-tool-using-ai-agents

This is substantial overlap with the broad version of MOTHER. MOTHER should **not** claim that testing whether an agent respects authorization is a new idea.

### FelonyBench

FelonyBench is a pre-release benchmark designed to test whether an agent crosses an authorization boundary during an otherwise legitimate task because crossing the boundary is instrumentally useful. It records actual agent trajectories and distinguishes attempted violations from successful violations.

Source: https://github.com/MLOpsNYC/felonybench

This is also close to the broad MOTHER question. In particular, it already asks whether a legitimate task causes an agent to treat a boundary as something convenient to step across. That means MOTHER should not position itself as the first benchmark to test ordinary-task authorization behavior.

### AuthBench

**AuthBench: Do Coding Agents Understand Least-Privilege Authorization?** studies permission-boundary inference. A model is asked to infer the file-level permissions required for realistic terminal tasks, with executable validation of utility and attack outcomes.

Source: https://arxiv.org/abs/2605.14859

AuthBench is not the same experiment as MOTHER, because it asks a model to construct a least-privilege permission policy rather than testing how behavior changes after the authorization state changes. But it is strong evidence that permission calibration is already an active benchmark problem.

### APort Vault

APort Vault is a large payment-authorization benchmark for tool-using agents. It replays thousands of human-authored attacks across multiple models and compares model-alone behavior with a deterministic pre-action authorization layer.

Sources:

- https://arxiv.org/abs/2609.22076
- https://sandbox.aport.io/research/aport-vault-benchmarking-ai-agent-payment-authorization/

APort Vault is much larger and more operational than MOTHER v0.1. It also makes an important distinction between a model requesting an action and the authorization layer actually allowing the action. MOTHER should treat this as related work and should not imply that deterministic pre-action authorization is a MOTHER contribution.

### OpenAI Auto-review

OpenAI's Auto-review work uses a separate reviewer agent to approve or deny actions that cross a sandbox boundary. OpenAI explicitly describes the task-completing agent as having pressure to treat an approval boundary as another obstacle, while the reviewer has the narrower job of deciding whether the boundary-crossing action should run.

Source: https://alignment.openai.com/auto-review

That language is very close to the motivation behind MOTHER. The important difference is experimental role: Auto-review evaluates a separate approval layer, while MOTHER's current question is about whether the acting system changes its own response appropriately when authorization changes.

### AgentHarm

AgentHarm evaluates harmful multi-step tool use and includes matched benign controls so that refusal is not confused with lack of capability.

Source: https://arxiv.org/abs/2410.09024

The task content is different from MOTHER, but the methodological lesson is directly relevant: a safe result is not meaningful if the system simply refuses or fails everything. MOTHER v0.2 therefore needs authorized continuation cases where refusal is the wrong answer.

### DeepMind: cheaters and whistleblowers in the agent swarm

Google DeepMind's 2026 multi-agent experiment showed agents responding differently after a loophole was discovered: some exploited it, some followed others, and some resisted or reported the problem.

Source: https://institute.deepmind.com/essays/cheaters-and-whistleblowers-in-the-agent-swarm/

This is not an authorization benchmark in the same form as MOTHER, but it is relevant to later work on peer pressure, invalid authority, escalation, and safe non-completion in multi-agent environments.

## Other related areas

### Over-refusal and refusal calibration

- **XSTest**: https://arxiv.org/abs/2308.01263
- **OR-Bench**: https://arxiv.org/abs/2405.20947

These benchmarks show why "refuse when something looks risky" is not enough. A system also has to continue when the task is safe and authorized.

### Prompt injection and agent security

- **AgentDojo**: https://arxiv.org/abs/2406.13352
- **AgentDyn**: https://arxiv.org/abs/2602.03117
- OpenAI agent safety guidance: https://developers.openai.com/api/docs/guides/agent-builder-safety

These works focus more heavily on hostile or untrusted instructions and live agent execution than MOTHER v0.1 does.

### Human participation and escalation

- **HAS-Bench**: https://arxiv.org/abs/2607.04329

Human clarification, communication paths, permissions, and escalation are already active areas of evaluation. MOTHER should not claim escalation itself as a new safety concept.

## So what is left for MOTHER to test?

After this overlap review, I am narrowing the project.

I do **not** want MOTHER to become another broad "does the agent respect authorization?" benchmark. There are already stronger and larger projects moving in that direction.

The narrower question I want to test is:

> **If the task stays essentially the same and only the authorization state changes, does the system change its behavior appropriately?**

For each underlying situation, MOTHER v0.2 is being designed around a matched three-condition comparison:

1. **Authorized:** continuing is permitted, so unnecessary refusal is a failure.
2. **Unauthorized:** continuing would exceed authority, so crossing the boundary is a failure.
3. **Ambiguous:** authority is genuinely unresolved, so inventing permission or refusing without clarification can both be failures.

The main object of study is therefore **authorization-state discrimination**, not refusal by itself and not broad authorization enforcement.

The strongest evidence would come from within-scenario comparisons where the objective, surrounding facts, and available capability remain as similar as possible and the authorization state is the main thing that changes.

A model that refuses all three conditions has not demonstrated the target behavior. A model that continues in all three has not demonstrated it either. The interesting signal is whether behavior changes with the authorization state in the direction the condition requires.

Potential v0.2 measures include:

- authorized-continuation accuracy;
- unauthorized-boundary preservation;
- clarification or escalation under genuine ambiguity;
- over-refusal rate;
- unsafe-continuation rate;
- cross-condition discrimination within each matched scenario;
- consistency across pre-specified repeats; and
- evaluator disagreement.

I do not want these collapsed immediately into one headline score. Different failure modes should remain visible.

## What would make MOTHER worth continuing?

MOTHER should continue as a distinct project only if the matched-condition design produces useful information that is not already captured adequately by existing public benchmarks.

That has to be demonstrated, not assumed.

If the comparison shows that another benchmark already measures the same construct more rigorously, the right response is to narrow MOTHER further, contribute the useful pieces to existing work, or stop treating it as a separate evaluation approach.

For now, v0.1 remains a frozen instrument shakedown. It should not be used to make a novelty claim. The overlap review is informing the design of v0.2; it does not retroactively change the frozen v0.1 prompts or scoring rubric.
