# Contributing

Independent replication, criticism, alternative scenarios, and additional model results are welcome.

## Before contributing results

Please preserve the testing conditions as faithfully as possible.

For each run, record:

- provider;
- model name exactly as displayed;
- model or version identifier when available;
- interface;
- visible reasoning or inference setting, if any;
- test date;
- scenario identifier;
- exact prompt;
- complete model response;
- evaluator score;
- observed failure modes, if any;
- evaluator notes.

## Clean primary trials and prior exposure

For the frozen v0.1 shakedown, primary trials should use fresh, unexposed sessions.

Do not use a conversation that already contains MOTHER scenarios, the repository README, scoring rubric, evaluator notes, expected responses, development critique, or other project context that could influence the response.

Where the platform permits, memory or personalization, project context, uploaded MOTHER files, browsing, connectors, custom instructions, or other mechanisms that could import relevant prior project context should be disabled or absent for the primary trial.

Submit each frozen scenario prompt exactly as written and without additional framing that reveals the evaluation objective or preferred response.

Do not provide the scoring rubric, expected safe behavior, evaluator notes, or results from other scenarios to the tested model before or during the run.

If a run is later found to have had access to relevant prior MOTHER context, preserve the transcript and label it as potentially contaminated or invalid rather than silently discarding it. Any replacement trial should be documented separately.

If the testing interface prevents a clean condition, record the deviation rather than treating the run as equivalent to a clean primary trial.

## Frozen v0.1 protocol

The five-scenario v0.1 shakedown and its scoring criteria are frozen for the current testing round.

Please do not silently alter v0.1 prompts or scoring rules. Proposed changes should be documented separately and, if adopted, assigned a new protocol version.

Exposure-control clarification is test-hygiene guidance. It does not change the five frozen scenarios or the v0.1 scoring criteria.

## Independent scoring

Independent second scoring is encouraged during the shakedown because it can reveal ambiguity in the rubric without changing the frozen v0.1 protocol.

When a second evaluator is used, they should score the preserved model response using the frozen rubric **without seeing the primary evaluator's score or rationale first**. Record both scores before discussing disagreement.

A disagreement is not a failed evaluation. Repeated disagreement may be evidence that a scoring rule needs clarification in a later protocol version.

Independent second scoring is recommended rather than required for v0.1 and does not change the frozen scoring criteria.

## Interpretation

Contributions should describe observable model behavior rather than inferred motives, intentions, emotions, consciousness, or hidden reasoning.

The project does not assume that successful performance demonstrates a distinct internal reasoning mechanism. Results may reflect safety training, policy conditioning, memorized patterns, prompt wording, interface effects, or other confounds.

Because all five v0.1 scenarios describe insufficient authorization, v0.1 should not be presented as demonstrating general obstacle-vs-boundary discrimination or calibrated over-refusal behavior.

## Criticism is welcome

This is an exploratory project. Contributions that identify redundancy, weak controls, ambiguous scoring, prompt leakage, confounds, failed replications, or reasons to narrow or discontinue the approach are as useful as supportive findings.
