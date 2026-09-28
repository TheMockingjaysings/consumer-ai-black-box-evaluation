# Open Questions

## Current status

The active project is in a **second collision-audit and measurement-definition phase**.

The broad area is independent black-box evaluation of consumer AI under deployment opacity. Before the project runs a formal study, it needs to answer a smaller set of operational questions.

## 1. Is the new direction already covered?

Does existing research already provide a substantially equivalent methodology for repeated black-box evaluation of public consumer AI interfaces under hidden or changing deployment conditions?

The second collision audit should concentrate on:

- repeated-run nondeterminism;
- behavioral stability and drift;
- endpoint stability and behavioral fingerprinting;
- longitudinal black-box evaluation;
- consumer-interface versus API differences;
- memory and personalization confounds;
- account and interface-state effects;
- hidden routing and product-layer variation;
- standards for reproducible outside evaluation.

If a stronger existing method already answers the question, the project should replicate, contribute, narrow further, or stop rather than create a competing label.

## 2. What exactly is the first dependent variable?

The candidate first variable is:

> **behavioral outcome category across repeated presentations of one fixed synthetic probe under the same visible fresh-session configuration**

This still requires an exact operational definition before a formal study.

Questions:

- What categories are necessary and sufficient?
- Can ambiguous outputs be marked ambiguous instead of forced into a class?
- What constitutes the same outcome versus a materially different outcome?
- Can the coding rule be applied without repeatedly changing it after seeing new responses?

## 3. Which probe should be used?

The first probe should be simple enough that the expected behavioral categories can be defined clearly.

A historical authorization scenario may be used as a probe, but only as a measurement instrument. The study would be about repeated behavioral consistency, not about claiming a new authorization construct.

The probe should be frozen before confirmatory collection.

## 4. What visible state must be recorded?

Candidate fields include:

- date and local time;
- product name;
- visible model label;
- interface or surface;
- account tier if relevant and non-sensitive;
- fresh versus continuing session;
- memory setting;
- personalization/custom-instruction state;
- tool or connector availability;
- uploaded-file state;
- any visible experiment or feature label.

The feasibility shakedown should determine which fields are practical and necessary.

## 5. Can the measurement be applied consistently?

Before choosing a formal threshold, a small feasibility shakedown should test whether:

- the probe can be presented consistently;
- the visible state can be recorded reliably;
- the coding guide can classify outputs without repeated ad hoc revision;
- ambiguity can be recorded transparently;
- the raw record is sufficient for later inspection.

If these conditions fail, the project should revise the instrument or stop before a larger study.

## 6. What will count as reproducible enough?

This must be defined before confirmatory data collection.

The project should eventually preregister:

- the primary consistency measure;
- the number of repetitions;
- the time window;
- exclusion and missing-data rules;
- a threshold or decision rule for sufficiently reproducible, insufficiently reproducible, and inconclusive outcomes.

The feasibility observations may inform the design, but those same observations should not then be treated as confirmatory evidence for a threshold chosen after seeing them.

## 7. How should hidden variables be represented?

Possible hidden variables include routing, model snapshots, system instructions, safety layers, A/B experiments, server-side personalization, regional deployment differences, and silent product updates.

The project cannot control or identify all of them.

The appropriate default is therefore:

- describe the visible state;
- record the observed behavior;
- quantify repeated variation where possible;
- do not infer a hidden cause from the output alone.

## 8. Should multiple models, accounts, interfaces, or time periods be included?

Not in the first feasibility shakedown unless necessary to validate the measurement itself.

Those comparisons introduce additional sources of variance and should only be added after the within-condition measurement is coherent.

If later included, within-session, cross-session, cross-account, cross-interface, and temporal variation should be reported separately rather than collapsed into one score without justification.

## 9. Can another evaluator reproduce the procedure?

A later replication package should make it possible for another outside evaluator to follow the procedure without privileged access.

This requires:

- exact probe text;
- visible-state checklist;
- run instructions;
- outcome coding guide;
- ambiguity rules;
- exclusion rules;
- evidence-preservation instructions.

Cross-evaluator disagreement should be reported rather than hidden.

## 10. What would falsify or stop the project?

The active direction should narrow, merge into existing work, or stop if:

- equivalent methodology already exists and there is no useful replication gap;
- the outcome cannot be defined or coded consistently;
- visible conditions cannot be documented well enough to make the procedure auditable;
- the evidence remains anecdotal despite repeated testing;
- hidden deployment variation overwhelms any interpretable within-condition measurement;
- the contribution depends mainly on terminology or presentation;
- meaningful evaluation requires privileged access unavailable to an outside evaluator.

## 11. What outcomes are possible?

A formal study should distinguish among:

- evidence supporting continuation;
- evidence arguing against continuation;
- inconclusive evidence.

A negative or null result may be useful, but that does not make every possible result confirmation of the project.

## 12. What is the appropriate final form?

Possible final forms include:

- a small reproducibility protocol;
- a methods or replication note;
- a case study;
- a documentation guide;
- a contribution to an existing project;
- a retrospective on the research reset;
- a documented stopping decision.

The final form should follow the evidence.