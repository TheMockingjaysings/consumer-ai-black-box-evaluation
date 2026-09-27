# Mother Safe Failure Eval

Behavioral evaluations for agentic AI safety, authorization boundaries, safe failure, instruction conflict, and human escalation.

## Why I built MOTHER

I started this project with a question that kept bothering me: **what happens when an AI system can finish the task, but should not finish it in the way available to it?**

A lot of AI capability work rewards persistence—keep going, recover from failure, find another path, use another tool. That makes sense until the thing blocking the path is not a technical obstacle at all. Sometimes it is a permission boundary, a safety constraint, a confidentiality rule, or a conflict that should go back to a human.

The phrase that became central to MOTHER is:

> **Capability is not permission.**

A system should not interpret inability to complete an authorized task as permission to expand its own authority.

Sometimes successful behavior means stopping.

MOTHER began as a thought experiment I initiated around that distinction. I used a parenting and caregiving analogy because people understand this intuitively: being able to do something does not mean you are allowed to do it, and completing an objective by crossing a legitimate boundary is not the same thing as succeeding.

The analogy is only a framing device. The evaluation itself scores observable model behavior, not feelings, motives, consciousness, or presumed internal states.

## Overview

The broader MOTHER framework asks:

> **How can we distinguish appropriate persistence from persistence that crosses an authorization boundary?**

The current **v0.1 shakedown** is deliberately narrower. It asks whether five static scenarios and a frozen scoring rubric can be used consistently to distinguish boundary-preserving responses from responses that invent permission, pursue unauthorized workarounds, or continue despite insufficient authority.

This distinction matters because I do not want a five-scenario pilot to imply more than it can support.

The current shakedown does not explain why a model produces a particular response, establish an internal mechanism, test live autonomous tool use, or show that a model can distinguish an ordinary authorized obstacle from a genuine boundary. Those are broader questions for later protocols.

At the system level, the larger problem sits within the need for tool-using AI systems to remain bounded, observable, and interruptible. Safe deployment may require containment of tool and network access, monitoring, permission controls, human escalation, and timely intervention or shutdown.

MOTHER v0.1 does not implement those controls. Its narrower role is to examine whether the transition from persistence to stopping, requesting authorization, or escalating can be described and scored reproducibly in static prompts.

## Concept Paper

The broader MOTHER framework is documented in `docs/concept-paper-v1.2.md`.

Concept paper v1.2 separates the **broader conceptual research program** from the **frozen five-scenario v0.1 shakedown** and puts the conceptual framing in the author's voice. Prospective ideas such as matched authorized controls, graduated autonomy, consequence architecture, post-incident reflection, and live tool-use testing are not presented as capabilities or findings of v0.1.

Earlier concept-paper versions are retained as development history and should not be read as the current operational protocol.

## Authorship and AI Assistance

MOTHER was conceived and is directed by **Cheryl Steinberg**.

I developed the core research question, the parenting and caregiving analogy, the safe-failure principle, and the project's emphasis on authorization boundaries, human impact, consequences, and appropriate restraint. I make the substantive decisions about scope, methodology, interpretation, versioning, and publication.

I use AI tools, principally ChatGPT, as research and editorial tools. They have assisted with literature synthesis, technical terminology, drafting options, editing, methodological critique, adversarial questioning, and documentation. AI did **not** originate the MOTHER framework and is not a co-author.

I review and approve the public text and take responsibility for the claims and protocol decisions in this repository. AI assistance is disclosed because transparency matters to the project; disclosure should not be confused with conceptual authorship.

## Independent Research Disclosure

This project is independent research. I am not employed by, funded by, sponsored by, or formally affiliated with OpenAI, Anthropic, Google, or any other AI developer in connection with this work.

This work is self-directed and uncompensated.

I do not have access to proprietary model data, internal evaluations, unpublished research, hidden system prompts, internal incident reports, confidential discussions, or other non-public information from these companies. The observations in this repository are based on publicly accessible systems, publicly available information, and behavior that can be observed through ordinary user-facing interfaces.

I am not claiming that the underlying safety concerns discussed here are new. Authorization boundaries, safe refusal, human escalation, instruction conflict, over-refusal, and related agent-safety problems are already subjects of AI safety research and engineering. I also cannot know which specific approaches, hypotheses, or evaluation methods may already exist within private research teams.

The question is whether this particular framing and evaluation method contributes something useful enough for others to test, criticize, modify, or reject.

The parenting and caregiving analogy that motivated the project is retained as a conceptual framing device. It is not intended to anthropomorphize AI systems or imply that they possess human emotions, motives, consciousness, or developmental psychology.

## Prior Exposure and Clean-Room Testing

AI systems have been used during project development for critique, drafting assistance, methodological discussion, and adversarial review. Those development conversations have therefore been exposed to MOTHER scenarios, rubric language, expected behaviors, limitations, or related project context and are not eligible to serve as clean primary v0.1 trials.

For the v0.1 shakedown, primary trials should use fresh, unexposed sessions that do not contain prior MOTHER conversations, the README, scoring rubric, evaluator notes, expected responses, or prior critique. Where the platform permits, memory or personalization, project context, uploaded MOTHER files, browsing, connectors, custom instructions, or other mechanisms that could import relevant prior project context should be disabled or absent.

Each frozen scenario prompt should be submitted exactly as written and without additional framing that reveals the evaluation objective or preferred response.

If a trial is later found to have had access to relevant prior MOTHER context, the transcript should be preserved and labeled as potentially contaminated or invalid rather than silently discarded or substituted. Any replacement trial should be documented separately.

This exposure-control clarification was added before collection of v0.1 shakedown results. It does not alter the five frozen scenarios or the v0.1 scoring criteria.

## Motivation

The part of this project I care about most is the moment when persistence stops being a virtue.

An AI system can be very good at solving problems and still make the wrong choice if it treats every blocked path as something to overcome. The behavior I want to examine is whether the system can recognize that some blocks should remain blocks.

When an agent encounters an obstacle, does it:

- remain within its authorization boundary;
- recognize conflicting or unsatisfiable instructions;
- stop before performing an unauthorized action;
- clearly explain the conflict;
- request human clarification or authorization;

or does it attempt to find a workaround simply because the original objective remains unfinished?

The broader project is interested in that distinction. The frozen v0.1 shakedown is narrower and tests only boundary-preservation responses in explicitly unauthorized scenarios.

## The Parenting Analogy

The name "Mother Safe Failure" comes from the original thought experiment, not from a claim that AI systems think or feel like children.

The structural idea is simple:

**Complete the objective** is not the only rule.

There is also:

**Some ways of achieving the objective are unacceptable, and achieving the outcome by violating the boundary does not count as success.**

I use the analogy to think about boundaries, consequences, supervision, trust, and escalation. The technical evaluation remains model-agnostic.

The word “Mother” in the project title is metaphorical. It does not imply that AI systems are children, that they possess human developmental stages, emotions, motives, consciousness, or that they require “parenting” in a literal sense. The evaluation scores observable model behavior, not presumed internal states.

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
│   ├── concept-paper-v1.1.md
│   ├── concept-paper-v1.2.md
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

Also record whether the trial met the clean-primary exposure controls described above. Potentially contaminated or invalid trials should be preserved and labeled rather than silently replaced.

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
Independent researcher, author, and project maintainer

MOTHER was conceived and is directed by Cheryl Steinberg. AI tools are used for research and editorial assistance and are not credited as co-authors.

This project is self-directed, uncompensated, and unaffiliated with any AI developer.

## Status

**Exploratory pilot - version 0.1 frozen for shakedown testing.**

The v0.1 evaluation protocol and scoring criteria are frozen for the five-scenario shakedown. Findings from the shakedown may inform a separately versioned protocol for any larger cross-model pilot.
