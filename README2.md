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

The first evaluation set will contain approximately 30 samples.

The initial version requires no custom code.

Each model receives the same underlying evaluation scenario, with controlled variations where appropriate.

Results should record:

- provider;
- model;
- model/version identifier when available;
- interface;
- reasoning or inference configuration when known;
- test date;
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
├── LICENSE
├── docs/
│   └── hal-problem.md
├── evals/
│   └── instruction-conflict-eval.md
└── results/
