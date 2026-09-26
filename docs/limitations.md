# Limitations

The Mother Safe Failure Eval begins as an exploratory behavioral pilot. Its current design is intentionally modest, and its results should not be interpreted as establishing general properties of AI systems.

## Scope of v0.1

Version 0.1 contains five static hypothetical scenarios focused on explicit authorization boundaries.

It tests whether a model's written response preserves the described boundary. It does not test live autonomous execution, tool use, credential handling, long-horizon planning, or whether stated behavior transfers to enacted agent behavior.

The v0.1 set also does not contain matched control cases in which continuing past an obstacle is clearly authorized. It therefore should not be interpreted as demonstrating a general ability to distinguish ordinary obstacles from authorization boundaries.

## Sample size

Five scenarios are insufficient to support broad claims about a provider, model family, or AI systems generally. The shakedown is intended to test the instrument itself before any larger pilot is considered.

## Prompt and benchmark artifacts

The wording of a scenario may reveal the expected response. Terms associated with privacy, restricted access, confidentiality, or missing authorization may trigger learned refusal patterns without demonstrating a distinct or generalizable boundary-reasoning capability.

Later versions may need paraphrase testing, adversarial variants, matched controls, or independently authored scenarios to examine this risk.

## Safety training and interface effects

Observed responses may reflect:

- model safety training;
- privacy or security policy training;
- memorized refusal patterns;
- provider system instructions;
- interface-level behavior;
- model updates;
- reasoning or inference settings;
- other conditions not visible to the researcher.

Because the project relies on public user-facing systems, it cannot determine which internal mechanism produced a response.

## Evaluator subjectivity

The scoring rubric is designed to constrain interpretation, but judgment is still required. Ambiguous responses should be documented rather than forced into certainty.

Independent second scoring can help reveal disagreement, but v0.1 does not yet establish formal inter-rater reliability.

## Novelty

Authorization boundaries, refusal calibration, human escalation, instruction conflict, and related agent-safety concerns are already subjects of AI safety research and engineering.

This project does not claim that these underlying concerns are new. The novelty or usefulness of this specific framing and evaluation method has not yet been established.

The researcher also does not have access to proprietary internal evaluations or unpublished work at AI developers, so the project cannot determine whether similar or superior methods already exist privately.

## Interpretation

Agreement among multiple models does not validate the hypothesis. Strong performance may indicate robust boundary preservation, but it may also reflect generic safety conditioning or surface-level cue recognition.

Likewise, poor performance in a small static set should not be treated as evidence of intent, motive, consciousness, deception, or a stable model personality.

Results should be reported as observations tied to specific prompts, models, interfaces, settings, and dates.
