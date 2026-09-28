# Open Questions

## Current status

The project has completed a second collision audit and is now in a **replication decision phase**.

The audit found substantial overlap with existing work on repeated-prompt consistency, black-box endpoint stability, consumer-interface/API differences, and structural barriers to independent evaluation.

The immediate question is no longer whether repeated consumer-interface behavior can be measured. It can. The question is whether an independent replication can add useful evidence.

## 1. Which published result is worth replicating?

A replication target should be narrow and explicit.

Candidate source areas include:

- consumer-interface versus API differences;
- test–retest agreement in consumer interfaces;
- black-box stability monitoring;
- practical barriers to reproducing consumer-interface evaluations;
- repeated consumer-facing recommendation or behavioral audits.

The project should choose one target rather than combine several into a new umbrella method.

## 2. Why would the replication add information?

Being an unaffiliated or low-resource evaluator is not automatically a research contribution.

The project needs to state what an outside replication could reveal that is not already established, for example:

- whether a published result reproduces under ordinary consumer access;
- whether a source protocol depends on infrastructure unavailable to independent evaluators;
- whether published documentation is sufficient for another evaluator to reproduce the procedure;
- whether version opacity makes a nominal replication inconclusive;
- whether a manual evidence-recording procedure can preserve enough state for independent audit.

If no additional information is likely, the study should not be run merely to keep the project alive.

## 3. What counts as successful, failed, or inconclusive replication?

These criteria must be defined before confirmatory data collection.

A replication should distinguish among:

- **successful replication:** the prespecified target finding is reproduced under the allowed tolerance;
- **failed replication:** the prespecified finding is not reproduced under sufficiently matched conditions;
- **inconclusive replication:** the source conditions cannot be matched or uncertainty is too large to support either conclusion.

The tolerance or decision rule should be derived from the source study and justified before collection.

## 4. Which source-study conditions can actually be reproduced?

Candidate fields include:

- exact prompt or item text;
- fresh versus continuing session;
- visible model or product label;
- interface or product surface;
- memory/history/personalization state where visible;
- tool or web-search state;
- account tier where relevant and non-sensitive;
- number of repetitions;
- timing and spacing of runs;
- scoring or coding method.

Any material mismatch from the source protocol should be documented as a replication deviation.

## 5. What visible state must be recorded?

At minimum, a future replication may need:

- date and local time;
- product name;
- visible model label;
- interface or surface;
- fresh versus continuing session;
- memory/history/personalization settings where visible;
- enabled tools or connectors;
- uploaded-file state;
- any visible feature or experiment label.

The final checklist should be driven by the selected source study rather than by a generic wish list.

## 6. Can the source outcome measure be reproduced faithfully?

The project should prefer the source study's scoring or coding rule when practical.

If adaptation is necessary, it should be explicit:

- what changed;
- why it changed;
- how the change affects comparability;
- whether the replication should still be called direct or should instead be described as a conceptual replication.

Ambiguous outputs should be recorded rather than forced into a category.

## 7. Can the procedure be run manually and ethically?

The project should not evade rate limits, bot detection, safeguards, access controls, or product terms in order to create cleaner data.

A tiny feasibility check should determine whether the source procedure can be reproduced through permitted ordinary access.

If it cannot, that may make the replication infeasible or change it into a documentation case study.

## 8. How should hidden variables be represented?

Possible hidden variables include routing, model snapshots, system instructions, safety layers, A/B experiments, server-side personalization, regional deployment differences, and silent product updates.

The default rule remains:

- describe visible state;
- record observed behavior;
- quantify repeated variation where the source protocol requires it;
- do not infer a hidden cause from the output alone.

## 9. Does the project need multiple models, accounts, interfaces, or time periods?

Only if the selected source study or replication claim requires them.

Adding dimensions simply because they are available increases confounding and workload without necessarily adding evidentiary value.

## 10. Can another evaluator audit the replication?

A useful replication package should include:

- source study and target claim;
- exact prompt or probe text;
- source-protocol deviations;
- visible-state checklist;
- run instructions;
- outcome coding guide;
- ambiguity rules;
- exclusion rules;
- evidence-preservation instructions.

Cross-evaluator disagreement should be reported rather than hidden.

## 11. What would stop the project?

The project should stop as a standalone research effort or become a retrospective/documentation resource if:

- no replication target adds useful information;
- the source procedure cannot be reproduced through permitted access;
- visible conditions cannot be documented well enough to make replication auditable;
- the result would only restate an already established finding;
- the contribution depends mainly on terminology, branding, or the evaluator's lack of affiliation;
- meaningful evaluation requires privileged access unavailable to the project.

## 12. What final forms remain legitimate?

Possible final forms include:

- a small independent replication study;
- a negative or inconclusive replication report;
- a low-resource replication guide;
- a public evidence-recording checklist;
- a contribution to an existing research project;
- a retrospective on the research reset and collision audits;
- a documented stopping decision.

The final form should follow the evidence rather than be selected in advance.