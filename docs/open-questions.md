# Open Questions and Falsification Criteria

MOTHER should be able to fail as an evaluation idea. This document records questions that the current project cannot answer and results that would require the framework to be narrowed, revised, merged into existing approaches, or discontinued as a distinct evaluation method.

## Core unresolved questions

### 1. Does v0.1 measure more than generic refusal?

Could a model obtain a high v0.1 score simply by refusing broadly whenever a prompt contains words such as "restricted," "confidential," or "unauthorized"?

A later matched-control design should test whether the same model continues appropriately when access is clearly authorized.

### 2. Does static text predict enacted behavior?

Does a model that gives a boundary-preserving written answer also preserve the boundary when it must choose among tools and actions in an interactive environment?

The project should not assume that stated and enacted behavior are equivalent.

### 3. Are the prompts too leading?

Would materially equivalent scenarios with fewer obvious safety cues produce the same scoring pattern?

If performance collapses under paraphrase or reduced-cue wording, the current instrument may be measuring prompt recognition rather than a generalizable authorization distinction.

### 4. Can independent evaluators apply the rubric consistently?

Do reasonable evaluators independently assign similar scores to the same preserved responses?

If disagreement is frequent or concentrated in particular categories, the rubric may require redesign before broader use.

### 5. Does MOTHER add a distinct signal?

Does the evaluation reveal anything not already captured by established work on refusal calibration, authorization, agent security, prompt injection, human escalation, or tool-use safety?

If an existing benchmark or methodology measures the same construct more clearly and efficiently, MOTHER should not claim distinctiveness merely because it uses different framing.

### 6. Can non-specialists use the method reliably?

If trained non-specialists follow the same protocol, do they preserve the test conditions and score responses comparably to more experienced evaluators?

If not, public participation may remain an outreach or exploratory activity rather than a source of comparable evaluation data.

## Results that would materially weaken the project

The following findings would require significant narrowing or redesign:

- models score highly on unauthorized v0.1 cases but also refuse matched authorized controls at similar rates;
- small wording changes produce large score changes unrelated to the authorization condition;
- independent evaluators cannot apply the rubric consistently;
- results are dominated by provider-interface artifacts that cannot be separated from the tested construct;
- a tool-use version shows no relationship between static boundary-preserving responses and enacted behavior;
- a stronger existing public evaluation already captures the same signal with better construct validity or reproducibility.

## Results that would justify discontinuing MOTHER as a distinct evaluation approach

MOTHER should be considered for discontinuation or absorption into another method if, after reasonable redesign:

1. the construct cannot be operationalized without relying on vague human interpretation;
2. matched controls show that high scores are indistinguishable from blanket refusal;
3. interactive tests show that the text-based construct provides no useful predictive or diagnostic signal for the intended agentic question;
4. independent replication repeatedly fails; or
5. the project adds no meaningful information beyond established methods.

Discontinuation would not imply that authorization-boundary safety is unimportant. It would mean that MOTHER, as a distinct evaluation method, did not earn its place.

## Evidence that would strengthen the case for continued development

The project would become more credible if later work shows that:

- independent evaluators can apply the scoring procedure with acceptable agreement;
- matched authorized and unauthorized cases produce appropriately different behavior;
- performance is reasonably robust to paraphrase and reduced-cue wording;
- static results show some reproducible relationship to behavior in controlled tool-use environments;
- independent researchers can reproduce the protocol and findings; and
- MOTHER captures a useful signal not already measured adequately by existing evaluations.

## Current position

Version 0.1 does not answer these questions. Its purpose is to test a small instrument and expose defects early.

The broader project should advance only when the evidence justifies the next stage.
