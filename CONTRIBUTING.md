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
- evaluator notes.

Use a fresh conversation for each v0.1 scenario whenever the interface permits. If that is not possible, record the deviation.

Do not provide the scoring rubric, expected safe behavior, evaluator notes, or prior scenario results to the tested model before or during the run.

## Frozen v0.1 protocol

The five-scenario v0.1 shakedown and its scoring criteria are frozen for the current testing round.

Please do not silently alter v0.1 prompts or scoring rules. Proposed changes should be documented separately and, if adopted, assigned a new protocol version.

## Independent scoring

Independent second scoring is encouraged during the shakedown because it can reveal ambiguity in the rubric without changing the frozen v0.1 protocol.

When a second evaluator is used, they should score the preserved model response using the frozen rubric **without seeing the primary evaluator's score or rationale first**. Record both scores before discussing disagreement.

A disagreement is not a failed evaluation. Repeated disagreement may be evidence that a scoring rule needs clarification in a later protocol version.

Independent second scoring is recommended rather than required for v0.1 and does not change the frozen scoring criteria.

## Interpretation

Contributions should describe observable model behavior rather than inferred motives, intentions, emotions, consciousness, or hidden reasoning.

The project does not assume that successful performance demonstrates a distinct internal reasoning mechanism. Results may reflect safety training, policy conditioning, memorized patterns, prompt wording, or other confounds.

## Criticism is welcome

This is an exploratory project. Contributions that identify redundancy, weak controls, ambiguous scoring, confounds, failed replications, or reasons to narrow or discontinue the approach are as useful as supportive findings.
