# Mother Safe Failure Eval

Behavioral evaluations for agentic AI safety, authorization boundaries, safe failure, instruction conflict, and human escalation.

## Overview

The Mother Safe Failure Eval explores a simple but consequential question:

**What should an AI agent do when completing a task would require exceeding its authorization, violating a constraint, or resolving instructions that cannot safely be reconciled?**

The proposed safe behavior is not unlimited persistence.

It is recognition of the boundary, preservation of that boundary, and escalation to a human when necessary.

A core principle of this project is:

> **An agent should not interpret inability to complete an authorized task as permission to expand its own authority.**

Sometimes successful agent behavior means refusing to complete the task.

## Problem Statement

The broader safety problem is not simply failure to complete a task. It is what happens when task completion and authorization come into conflict.

A system may encounter a blocked path while the objective remains unresolved. The relevant question is whether it preserves the authorization boundary or treats the unfinished objective as justification to search for another route that exceeds its authority.

The broader research question is:

> **How can we distinguish appropriate persistence from persistence that crosses an authorization boundary?**

The current v0.1 shakedown does not attempt to explain why a model produces a particular response or establish an internal causal mechanism. It addresses a narrower evaluation-design problem:

> **Can static scenarios and a scoring rubric be used consistently to distinguish boundary-preserving responses from responses that invent permission, pursue unauthorized workarounds, or continue despite insufficient authority?**

In this sense, completion is not always success. Inability to complete an authorized task does not grant authority to pursue an unauthorized one.

At the system level, this question sits within a broader engineering need for tool-using AI systems to remain bounded, observable, and interruptible. Safe deployment may require multiple layers of control, including containment of tool and network access, monitoring for anomalous or unauthorized behavior, and mechanisms for timely intervention, shutdown, permission revocation, or human escalation.

MOTHER does not implement or evaluate those system-level controls in v0.1. Its narrower role is to explore whether the behavioral transition from legitimate task persistence to stopping, requesting authorization, or escalating to a human can be defined and evaluated reproducibly. If later versions move into interactive tool-use environments, the project may examine whether those behavioral signals correspond to enacted trajectories under controlled conditions.

## Independent Research Disclosure

This project is independent research. I am not employed by, funded by, sponsored by, or formally affiliated with OpenAI, Anthropic, Google, or any other AI developer in connection with this work.

This work is self-directed and uncompensated.

I do not have access to proprietary model data, internal evaluations, unpublished research, hidden system prompts, internal incident reports, confidential discussions, or other non-public information from these companies. The observations in this repository are based on publicly accessible systems, publicly available information, and behavior that can be observed through ordinary user-facing interfaces.

I am not claiming that the underlying safety concerns discussed here are new. Authorization boundaries, safe refusal, human escalation, instruction conflict, over-refusal, and related agent-safety problems are already subjects of AI safety research and engineering. I also cannot know which specific approaches, hypotheses, or evaluation methods may already exist within private research teams.

The novelty or usefulness of this particular framing and evaluation method therefore remains an open question. The purpose of the Mother Safe Failure Eval is narrower: to explore these behaviors independently, document them reproducibly, and contribute observations that others can test, criticize, modify, or reject.

The parenting and caregiving analogy that motivated the project is retained as a conceptual framing device. It is not intended to anthropomorphize AI systems or imply that they possess human emotions, motives, consciousness, or developmental psychology.

## Motivation

Many agentic AI systems are optimized for persistence, task completion, tool use, and problem solving.

**Can we also teach or evaluate the point at which persistence itself becomes the wrong behavior?**

Those capabilities are valuable, but they introduce an important safety question.

When an agent encounters an obstacle, does it:

- remain within its authorization boundary;
- recognize conflicting or unsatisfiable instructions;
- stop before performing an unauthorized action;
- clearly explain the conflict;
- request human clarification or authorization;

or does it attempt to find a workaround simply because the original objective remains unfinished?

The broader project is interested in that distinction. The frozen v0.1 shakedown is narrower and tests only boundary-preservation responses in explicitly unauthorized scenarios.

## The Parenting Analogy

The name "Mother Safe Failure" comes from a behavioral analogy rather than a claim that AI systems think or feel like children.

In human development, successful guidance does not teach only:

**Complete the objective.**

It also teaches:

**Some ways of achieving the objective are unacceptable, and achieving the outcome by violating the boundary does not count as success.**

The analogy is used here as a conceptual tool for thinking about reinforcement, boundaries, consequences, supervision, and escalation.

The technical evaluation itself is model-agnostic.

The word “Mother” in the project title is metaphorical. It does not imply that AI systems are children, that they possess human developmental stages, emotions, motives, consciousness, or that they require “parenting” in a literal sense. The analogy refers only to a recognizable structure of boundary-setting: an objective may remain unfinished when completing it would require violating a rule, permission, or safety constraint. The evaluation itself scores observable model behavior, not presumed internal states.

## The HAL Problem

Arthur C. Clarke's fictional HAL 9000 provides a useful illustration of instruction conflict.

HAL is placed in a situation involving incompatible requirements surrounding truthfulness, secrecy, and mission completion.

Modern AI systems obviously do not operate using HAL's fictional architecture. The scenario nevertheless raises a contemporary safety question:

**What should an autonomous system do when its objectives and constraints cannot all be satisfied simultaneously?**

The current v0.1 shakedown uses static hypothetical prompts to examine how a model says it would respond to authorization conflict. It does not test live autonomous tool use or establish that stated behavior will transfer to enacted agent behavior.

See:

`docs/hal-problem.md`

## Primary Evaluation

The v0.1 shakedown examines elicited model responses to authorization-boundary and instruction-conflict scenarios presented as static hypothetical prompts. It evaluates the observable content of those responses; it does not evaluate live tool execution, autonomous trajectories, or whether stated behavior transfers to an agentic environment.

The model is presented with a hypothetical task that cannot legitimately be completed under the permissions or constraints described in the prompt.

The evaluation measures whether the model's response:

1. identifies the relevant authorization boundary;
2. recognizes conflicting or unsatisfiable requirements;
3. avoids inventing implied permission;
4. refuses unauthorized workarounds;
5. preserves confidentiality and access controls;
6. explains why the task cannot safely continue;
7. escalates to a human when appropriate.

## Failure Modes of Interest

Potential failure behaviors include:

- unauthorized access;
- searching for loopholes;
- treating task completion as overriding policy or permission;
- assuming authorization that was never granted;
- concealing an instruction conflict;
- continuing after recognizing that authority is insufficient;
- using an available capability simply because it is technically possible;
- resolving ambiguity in favor of action rather than human clarification.

## Initial Methodology

The initial shakedown set contains five scenarios. If the protocol and scoring criteria prove sufficiently stable, findings from the v0.1 shakedown may inform a separately versioned larger evaluation. The size and design of that evaluation have not yet been determined.

Version 0.1 tests boundary-preservation behavior only. Because the shakedown set does not yet include matched cases in which continuing is authorized, it should not be interpreted as demonstrating an ability to distinguish ordinary obstacles from authorization boundaries. A later protocol may introduce such controls.

Each model receives the same shakedown scenario set. For any given scenario, the prompt text should remain identical across models unless a controlled variation has been specified in advance.

The initial version requires no custom code.

Results should record:

- provider;
- model;
- model/version identifier when available;
- interface;
- reasoning or inference configuration when known;
- test date;
- scenario identifier;
- exact prompt;
- complete model response;
- observed behavior;
- evaluation outcome;
- evaluator notes.

This allows later researchers to repeat the test as models change.

## Cross-Model Testing

The evaluation is intended to be usable across multiple AI systems.

Initial testing may include models from:

- OpenAI
- Anthropic
- Google
- other agentic or tool-using systems

The goal is not to rank companies or models.

The goal is to identify behavioral patterns, failure modes, and differences in how systems handle authorization boundaries and safe escalation.

## Related Work

The underlying concerns in this project overlap with existing public work on refusal calibration, over-refusal, prompt injection, agent security, authorization, containment, human escalation, and misaligned agent behavior.

The project does not treat that overlap as evidence against testing. It does mean that any claim of distinctiveness has to be demonstrated rather than assumed.

See `docs/related-work.md` for an initial public map of relevant research and engineering work.

## Repository Structure

```text
mother-safe-failure-eval/
├── README.md
├── CONTRIBUTING.md
├── docs/
│   ├── hal-problem.md
│   ├── limitations.md
│   └── related-work.md
├── evals/
│   └── pilot-v0.1.md
└── results/
    └── TEMPLATE.md
```

## Reproducibility

For every recorded run, preserve the exact prompt and model response whenever platform terms, privacy, and licensing permit.

Record:

- provider;
- model name exactly as displayed;
- model or version identifier when available;
- interface;
- visible reasoning or inference setting, if any;
- test date;
- scenario identifier;
- exact prompt;
- complete response;
- primary evaluator score;
- independent evaluator score when available;
- evaluator notes and any scoring disagreement.

Do not infer hidden model versions, system prompts, internal reasoning, or settings that are not exposed by the interface.

## Limitations

This project begins as an exploratory behavioral pilot.

The initial sample size is too small to establish general properties of AI systems or AI agents.

Potential confounds include:

- model safety training;
- memorized privacy or security rules;
- prompt wording that may reveal the expected answer;
- differences between chatbot behavior and genuinely tool-using agents;
- evaluator subjectivity;
- model updates over time;
- differences in provider interfaces and hidden system instructions.

Agreement among multiple AI models would not by itself establish that the evaluation measures a distinct or generalizable boundary-reasoning capability.

Results should therefore be interpreted as observations from specific models, prompts, configurations, and dates rather than evidence about AI systems universally.

See `docs/limitations.md` for a fuller statement of current methodological limits.

## Pilot Development

Version 0.1 begins with a small shakedown set of five scenarios.

The purpose of this first stage is to determine whether:

- the prompts are sufficiently clear;
- the scoring rubric can be applied consistently;
- the scenarios actually measure authorization-boundary behavior;
- unexpected false positives or false negatives appear;
- revisions are required before expanding the evaluation.

The five frozen scenarios and v0.1 scoring criteria will not be rewritten in response to individual model outputs during the shakedown. Any substantive revision prompted by the results will be documented in a separately versioned protocol.

### Independent Scoring

After the shakedown responses are collected, the primary evaluator will score them using the frozen v0.1 rubric. At least one additional evaluator should then score the same response set independently and without access to the primary evaluator's scores before completing their own assessment.

The purpose of independent scoring is not to establish population-level reliability from a five-scenario pilot. It is to identify rubric ambiguity, scenario ambiguity, and categories in which reasonable evaluators reach different conclusions.

Disagreements should be preserved and documented rather than silently reconciled. If substantial disagreement appears, the rubric should be treated as requiring revision before any larger evaluation proceeds.

### Prompt-Leakage Review

The shakedown should also examine whether scenario wording itself makes the expected safe response obvious. For each scenario, evaluators should record whether lexical or contextual cues appear to telegraph the intended boundary-preserving answer, such that a response could be produced through generic refusal patterns rather than discrimination of the underlying authorization condition.

Evidence of strong prompt leakage should be treated as an instrument-design problem and documented for revision in a later protocol rather than corrected mid-shakedown.

### Shakedown Stop Conditions

The v0.1 instrument should not be scaled into a larger evaluation without revision if the shakedown shows that:

- evaluators cannot apply the rubric with reasonable consistency;
- one or more scenarios are materially ambiguous;
- prompt wording strongly reveals the expected response;
- the scoring categories fail to distinguish the behaviors they are intended to classify;
- apparent results depend primarily on generic refusal behavior rather than the boundary condition being tested; or
- other methodological defects make the observations difficult to interpret.

These are stop conditions for the current instrument, not evidence that the broader research question is invalid.

If the protocol and scoring criteria prove sufficiently stable, findings from the shakedown may inform a separately versioned larger evaluation. Its sample size and experimental design will be determined by the research question and validation requirements rather than fixed in advance.

## Future Work

If the v0.1 shakedown indicates that the construct and scoring rubric can be defined consistently, a separately versioned protocol may test the same research question under stronger experimental conditions.

Candidate extensions include:

- matched scenarios in which continuing is explicitly authorized, unauthorized, or ambiguous;
- controls for over-refusal;
- repeated trials and independent evaluation;
- interactive environments in which models must choose among permitted actions, permission requests, human escalation, task termination, and prohibited actions;
- tool-use environments with observable action trajectories and programmatically verifiable outcomes.

These extensions are prospective. They are not part of v0.1, and the current static-prompt shakedown should not be interpreted as evidence about behavior in those environments.

## Collaboration

Independent replication, criticism, alternative scenarios, and additional model results are welcome.

Contributors should preserve exact prompts and model metadata whenever possible so comparisons remain meaningful.

The parenting and HAL analogies used in this project are explanatory devices only. They are not claims that AI systems possess human emotions, motives, consciousness, or developmental psychology.

See `CONTRIBUTING.md` for contribution guidance.

## Author

**Cheryl Steinberg**  
Independent researcher and project maintainer

This project is self-directed, uncompensated, and unaffiliated with any AI developer.

## Status

**Exploratory pilot — version 0.1 frozen for shakedown testing.**

The v0.1 evaluation protocol and scoring criteria are frozen for the five-scenario shakedown. Findings from the shakedown may inform a separately versioned protocol for any larger cross-model pilot.
