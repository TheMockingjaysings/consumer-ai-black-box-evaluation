# Open Questions

## Current status

These are the unresolved questions for the project's active direction: **independent black-box evaluation of consumer AI under deployment opacity**.

The purpose of this file is not to manufacture a novelty claim. It is to identify what must be answered before the work can justify continuing as a standalone methodology.

## 1. Is the question already answered?

The first question remains the most important:

> Does existing research already provide a sufficiently similar methodology for independent evaluators testing ordinary public AI interfaces under hidden or changing deployment conditions?

The literature audit should search specifically for work that combines several of the following:

- consumer-facing interfaces rather than controlled APIs;
- repeated black-box behavioral testing;
- unknown or changing model versions;
- memory and personalization effects;
- account or interface-state effects;
- model routing or hidden deployment layers;
- longitudinal replication;
- standards for documenting externally observed behavior;
- explicit limits on causal inference from black-box evidence.

If a stronger existing method already covers this combination, this project should not claim a separate contribution.

## 2. What is the unit of evidence?

Is one interaction ever meaningful evidence, or should the minimum unit be a repeated set of runs under documented conditions?

Questions:

- How many repetitions are needed before a behavioral pattern is worth reporting?
- Should outcome coding be categorical, descriptive, or both?
- How should stochastic variation be represented without implying more statistical precision than the sample supports?
- What raw records are necessary for another evaluator to inspect the claim?

## 3. What visible state must be recorded?

A public-interface evaluator may be able to observe some deployment state but not all of it.

Candidate fields include:

- date and local time;
- product name;
- visible model label;
- interface or surface;
- account tier if relevant and non-sensitive;
- memory setting;
- personalization/custom-instruction state;
- tool or connector availability;
- fresh versus continuing conversation;
- uploaded-file state;
- any visible experiment or feature label.

Which of these are essential for a reproducible record?

## 4. How should hidden variables be handled?

Possible hidden variables include routing, server-side safety layers, system instructions, A/B experiments, model snapshots, regional deployment differences, and product updates.

The project cannot control all of these. The question is whether it can document enough uncertainty around them to keep the resulting evidence useful.

## 5. What does reproducibility mean here?

Several kinds of reproducibility may need to be separated:

- **within-run reproducibility:** repeated prompts in the same visible state;
- **cross-session reproducibility:** fresh-session replication;
- **cross-account reproducibility:** replication under a second account where appropriate;
- **cross-interface reproducibility:** web/mobile/desktop or different product surfaces;
- **temporal reproducibility:** replication days or weeks later;
- **cross-evaluator reproducibility:** another person following the same procedure.

These should not be collapsed into a single score unless there is a strong methodological reason.

## 6. How much causal language is defensible?

The default answer should be: very little.

An external evaluator can usually document an association between visible conditions and behavior. That is different from proving that the visible condition caused the behavior.

The project needs a claim language that distinguishes:

- observation;
- replication;
- association;
- causal explanation;
- mechanistic explanation.

## 7. Can memory and personalization be studied without turning the project into a privacy study?

If memory or personalization is included, the scenarios should use synthetic, non-sensitive information. No real medical, financial, credential, or other high-risk personal information should be required.

The project should test product behavior, not collect intimate user profiles.

## 8. Should different model labels be compared?

A visible model label may not uniquely identify the deployed behavior. Conversely, two runs under the same visible label may not be backed by an identical model snapshot or routing path.

The project should determine whether model labels are useful metadata, misleading metadata, or simply one field among many.

## 9. What would distinguish this from ordinary anecdotal red teaming?

This question is critical.

A credible methodology would need more than interesting screenshots. It should add at least some of the following:

- controlled repetition;
- explicit condition logging;
- predefined outcome coding;
- longitudinal replication;
- independent replication by another evaluator;
- transparent uncertainty statements;
- a record of product/version drift.

If the project cannot move beyond anecdotal evidence, it should say so and stop claiming methodology development.

## 10. What would falsify the project?

The active direction should be abandoned, narrowed, or merged into existing work if:

- equivalent methodology already exists;
- results are too unstable to replicate meaningfully;
- visible deployment metadata is insufficient to support useful comparisons;
- the project can only produce anecdotes;
- meaningful evaluation requires privileged access that outside evaluators do not have;
- the contribution depends mainly on terminology rather than capability.

## 11. What is the appropriate final form?

The work does not have to become a benchmark.

Possible final forms include:

- a small reproducibility protocol;
- a methods note;
- a case study;
- a replication package;
- a public guide for documenting black-box observations;
- a contribution to another project;
- a retrospective on why the original benchmark framing was abandoned.

The final form should follow the evidence rather than be decided in advance.
