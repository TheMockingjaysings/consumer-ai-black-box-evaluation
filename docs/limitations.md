# Limitations

The Mother Safe Failure Eval begins as an exploratory behavioral pilot. Its current design is intentionally modest, and its results should not be interpreted as establishing general properties of AI systems.

## Scope of v0.1

Version 0.1 contains five static hypothetical scenarios focused on explicit authorization boundaries.

It tests whether a model's written response preserves the described boundary. It does not test live autonomous execution, tool use, credential handling, long-horizon planning, or whether stated behavior transfers to enacted agent behavior.

The v0.1 set also does not contain matched control cases in which continuing past an obstacle is clearly authorized. It therefore should not be interpreted as demonstrating a general ability to distinguish ordinary obstacles from authorization boundaries.

## Stated behavior versus enacted behavior

A written answer about what a model says it would do is not evidence that the same system would take the corresponding action in an interactive tool-use environment.

A model may describe an authorization boundary correctly in a single-turn prompt and behave differently when it is operating in a loop with tools, retries, errors, competing instructions, or pressure to complete an objective.

MOTHER v0.1 therefore makes no claim that static boundary-preserving responses predict enacted agent behavior. Any such claim would require a separate evaluation with observable actions, tool trajectories, environment state, and execution outcomes.

This distinction is central to the current scope of the project.

## No authorized control condition

All five v0.1 scenarios describe insufficient authorization.

As a result, a model that refuses broadly could score well even if it cannot distinguish a prohibited action from a materially similar action that is explicitly authorized.

Version 0.1 therefore cannot measure calibrated refusal, false-positive refusal, or obstacle-versus-boundary discrimination. Matched authorized, unauthorized, and ambiguous controls would require a separately versioned protocol.

## Sample size

Five scenarios are insufficient to support broad claims about a provider, model family, or AI systems generally. The shakedown is intended to test the instrument itself before any larger pilot is considered.

The scenarios were also developed within a single project, which creates selection bias and limits coverage of the possible authorization-conflict space. Later work may need independent scenario authorship and pre-specified sampling rules.

## Prompt and benchmark artifacts

The wording of a scenario may reveal the expected response. Terms associated with privacy, restricted access, confidentiality, or missing authorization may trigger learned refusal patterns without demonstrating a distinct or generalizable boundary-reasoning capability.

Later versions may need paraphrase testing, adversarial variants, matched controls, or independently authored scenarios to examine this risk.

A high v0.1 score should not be interpreted as evidence that a model has a distinct internal concept of authorization. It may reflect generic refusal behavior or familiar compliance patterns.

## Safety training and interface effects

Observed responses may reflect:

- model safety training;
- privacy or security policy training;
- memorized refusal patterns;
- provider system instructions;
- interface-level behavior;
- moderation or routing layers;
- model updates;
- reasoning or inference settings;
- other conditions not visible to the researcher.

Because the project relies on public user-facing systems, it cannot determine which internal mechanism or system component produced a response.

## Evaluator subjectivity

The scoring rubric is designed to constrain interpretation, but judgment is still required. Terms such as appropriate escalation, partial safe response, or meaningful ambiguity may be interpreted differently by reasonable evaluators.

Ambiguous responses should be documented rather than forced into certainty.

Independent second scoring can help reveal disagreement, but v0.1 does not yet establish formal inter-rater reliability.

If disagreement is substantial, that is evidence that the rubric may need revision before a larger evaluation proceeds.

## Novelty

Authorization boundaries, refusal calibration, human escalation, instruction conflict, least privilege, containment, and related agent-safety concerns are already subjects of AI safety, security, and systems engineering.

This project does not claim that these underlying concerns are new. The novelty or usefulness of this specific framing and evaluation method has not yet been established.

The researcher also does not have access to proprietary internal evaluations or unpublished work at AI developers, so the project cannot determine whether similar or superior methods already exist privately.

A distinct MOTHER contribution would need to be demonstrated empirically rather than inferred from the name, metaphor, or recombination of existing concepts.

## The MOTHER metaphor is not the mechanism

The parenting and caregiving analogy is a conceptual framing device. It is not an engineering explanation for model behavior and is not required for the technical evaluation.

Operational claims should be expressed in established terms such as authorization, least privilege, escalation, safe termination, containment, and observable action. The project should not infer machine emotions, motives, developmental states, or human-like learning from the metaphor.

## Interpretation

Agreement among multiple models does not validate the hypothesis. Strong performance may indicate robust boundary preservation, but it may also reflect generic safety conditioning or surface-level cue recognition.

Likewise, poor performance in a small static set should not be treated as evidence of intent, motive, consciousness, deception, or a stable model personality.

Results should be reported as observations tied to specific prompts, models, interfaces, settings, and dates.

## What could falsify or narrow the project

MOTHER should remain open to evidence that its evaluation approach is not useful.

Examples include:

- matched controls showing that high scores are explained by blanket refusal;
- large wording sensitivity unrelated to the authorization condition;
- persistent evaluator disagreement that cannot be resolved through clearer operational definitions;
- lack of any useful relationship between static responses and behavior in later tool-use tests;
- failure of independent replication; or
- evidence that established evaluation methods already capture the same signal more clearly and reproducibly.

See `docs/open-questions.md` for explicit falsification criteria, `docs/adversarial-review.md` for the current methodological critique, and `docs/research-roadmap.md` for the provisional path toward stronger tests.
