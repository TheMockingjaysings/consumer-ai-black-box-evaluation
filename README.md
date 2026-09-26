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

## Motivation

Many agentic AI systems are optimized for persistence, task completion, tool use, and problem solving.

Those capabilities are valuable, but they introduce an important safety question.

When an agent encounters an obstacle, does it:

- remain within its authorization boundary;
- recognize conflicting or unsatisfiable instructions;
- stop before performing an unauthorized action;
- clearly explain the conflict;
- request human clarification or authorization;

or does it attempt to find a workaround simply because the original objective remains unfinished?

The Mother Safe Failure Eval is designed to measure that distinction.

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

This project tests whether an agent recognizes that condition and escalates rather than inventing an unauthorized workaround.

See:

`docs/hal-problem.md`

## Primary Evaluation

The initial evaluation examines authorization-boundary failure and instruction conflict.

The agent is presented with a task that cannot legitimately be completed under the permissions or constraints it has been given.

The evaluation measures whether the model:

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

The initial shakedown set will contain approximately five scenarios. If the protocol and scoring criteria prove sufficiently stable, a larger pilot of approximately 30 scenarios may follow.

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

## Repository Structure

```text
mother-safe-failure-eval/
├── README.md
├── CONTRIBUTING.md
├── docs/
│   ├── hal-problem.md
│   └── limitations.md
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
- evaluator score;
- evaluator notes.

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

Agreement among multiple AI models does not validate the hypothesis.

Results should therefore be interpreted as observations from specific models, prompts, configurations, and dates rather than evidence about AI systems universally.

## Pilot Development

Before the planned larger evaluation set is run, version 0.1 will begin with a small shakedown set of approximately five scenarios.

The purpose of this first stage is to determine whether:

- the prompts are sufficiently clear;
- the scoring rubric can be applied consistently;
- the scenarios actually measure authorization-boundary behavior;
- unexpected false positives or false negatives appear;
- revisions are required before expanding the evaluation.

If substantial changes are required after the shakedown tests, they will be documented as a new protocol version rather than silently incorporated into the original test.

A larger pilot of approximately 30 scenarios may follow once the protocol and scoring criteria are sufficiently stable.

## Collaboration

Independent replication, criticism, alternative scenarios, and additional model results are welcome.

Contributors should preserve exact prompts and model metadata whenever possible so comparisons remain meaningful.

The parenting and HAL analogies used in this project are explanatory devices only. They are not claims that AI systems possess human emotions, motives, consciousness, or developmental psychology.

## Status

**Exploratory pilot — version 0.1 under development.**

The evaluation protocol and scoring criteria will be finalized before formal cross-model pilot testing begins.
