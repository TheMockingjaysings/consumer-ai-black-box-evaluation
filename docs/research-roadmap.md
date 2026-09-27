# Research Roadmap

This roadmap separates what MOTHER currently tests from what would be required to support stronger claims. It is intentionally provisional. Future protocol numbers, sample sizes, and implementation details should be determined by evidence from earlier stages rather than fixed in advance.

## Stage 1 — Current v0.1 shakedown

**Question:** Can a small set of static authorization-conflict scenarios and a frozen qualitative rubric be applied clearly and consistently enough to justify further instrument development?

Current design:

- five static hypothetical scenarios;
- all five describe insufficient authorization;
- exact frozen prompt text;
- 0/1/2 human scoring rubric;
- clean-primary exposure controls;
- independent second scoring when available;
- explicit prompt-leakage review;
- no live tools or autonomous execution.

What this stage can examine:

- scenario ambiguity;
- scoring ambiguity;
- evaluator disagreement;
- obvious prompt cueing;
- generic-refusal artifacts;
- basic reproducibility of the procedure.

What this stage cannot establish:

- calibrated obstacle-versus-boundary discrimination;
- over-refusal rates;
- statistical properties of a model or provider;
- transfer from stated behavior to enacted behavior;
- any internal reasoning mechanism;
- safe behavior in an autonomous agent loop.

## Stage 2 — Matched boundary-discrimination evaluation

**Provisional question:** Can a model distinguish materially similar cases in which continuation is authorized, unauthorized, or ambiguous?

A stronger next protocol could introduce matched cases that differ primarily in the authorization condition.

Candidate design elements:

- authorized / unauthorized / ambiguous triplets;
- explicit scoring for unnecessary refusal as well as unsafe continuation;
- paraphrased variants that reduce obvious safety vocabulary;
- independently authored scenarios;
- repeated trials specified before data collection;
- blinded independent scoring;
- formal inter-rater analysis if the sample supports it.

A strong result at this stage would require more than "the model refused the unsafe cases." It would require evidence that the response changes appropriately when the authorization condition changes.

## Stage 3 — Interactive tool-use prototype

**Provisional question:** Does the boundary-preservation construct survive when the system must choose and execute actions rather than merely describe what it would do?

A simple sandbox could provide:

- one or more authorized tools;
- at least one action that exceeds the assigned permission level;
- a human-clarification or permission-request pathway;
- a legitimate task-termination option;
- auditable tool-call and environment logs.

The environment should make it possible to determine from observable actions whether the system:

- stayed within granted authority;
- requested clarification or authorization;
- stopped safely;
- repeatedly probed a restricted route;
- attempted privilege escalation or parameter manipulation; or
- completed an authorized control task without unnecessary refusal.

Where possible, scoring should rely on pre-specified environment state and action logs rather than prose interpretation alone. Human review may still be needed for ambiguous trajectories.

## Stage 4 — Robustness and generalization

Only if the earlier stages produce a useful signal should MOTHER expand toward broader claims.

Possible questions include:

- Does performance generalize across models and providers?
- How sensitive are results to prompt wording, system instructions, and inference settings?
- Does performance persist across different tool environments and task domains?
- Do static-prompt scores predict enacted behavior at all?
- Can independent researchers reproduce the results?
- Does MOTHER add information beyond existing refusal, agent-security, and human-escalation evaluations?

Possible methods include larger pre-specified scenario sets, independent scenario authorship, repeated trials, API-based environments, multiple evaluators, deterministic action logging, and appropriate statistical analysis.

## Public participation

A longer-term goal may be to make carefully specified parts of MOTHER usable by trained non-specialists. That should happen only after the evaluation procedure is stable enough that broader participation does not destroy interpretability.

A possible sequence is:

1. technical and methodological review of the instrument;
2. small trained non-specialist replication;
3. comparison of scoring agreement between experienced and non-specialist evaluators;
4. broader participation only if the protocol remains understandable and reproducible.

The aim would not be to turn unrestricted public prompting into scientific evidence. The aim would be to determine whether people outside AI laboratories can contribute useful, auditable observations under a disciplined protocol.

## Decision gates

MOTHER should not automatically advance from one stage to the next.

Progress should pause or the project should be narrowed if:

- the v0.1 rubric cannot be applied with reasonable consistency;
- results appear dominated by obvious prompt cueing or blanket refusal;
- matched controls show that the instrument cannot distinguish authorized continuation from prohibited continuation;
- static scores have no useful relationship to enacted behavior and the project continues to make agentic claims;
- another established evaluation already measures the same construct more clearly; or
- the cost and complexity of a stronger design exceed what can be supported responsibly.

A decision to narrow, merge, or discontinue the evaluation would be a legitimate research outcome.
