# Limitations

## Purpose

This file defines the limits of the active project: **independent black-box evaluation of consumer AI under deployment opacity**.

These limitations constrain what the evidence can support. They should not be treated as proof that the project succeeds simply because they are acknowledged.

## 1. No privileged access

The project assumes the evaluator does not have access to:

- model weights;
- hidden system prompts;
- internal chain-of-thought;
- routing logic;
- safety-layer logs;
- experiment assignment;
- server-side configuration;
- complete model-version metadata.

The project therefore cannot determine hidden mechanisms from interface behavior alone.

## 2. Visible sameness does not guarantee deployment sameness

Two runs may appear identical from the user's point of view while differing in hidden routing, model snapshot, system instructions, safety layers, experiments, personalization state, or infrastructure.

The project may measure observed variation under the same **visible** conditions, but it cannot assume that all hidden conditions were held constant.

## 3. Consumer products can change without notice

Public AI products may change between runs. A visible model name can remain unchanged while the underlying deployment changes, and a product may expose too little metadata to identify the change.

This limits longitudinal replication and attribution.

## 4. Stochastic outputs complicate replication

Repeated presentation of the same prompt can produce different responses even when visible conditions appear identical.

The active project therefore treats repeated outcome consistency as a quantity to measure rather than assuming deterministic behavior.

## 5. Behavioral change is not automatically model drift

An observed difference over time or across sessions may reflect model changes, routing, product logic, personalization, safety layers, or another hidden variable.

The project should use language such as **observed behavioral variation** unless independent evidence supports a more specific claim.

## 6. Association is not causation

If behavior changes when a visible setting changes, the project may report that the conditions were associated with different observed outcomes.

It should not automatically conclude that the visible setting caused the change because hidden deployment variables may also have changed.

## 7. Personalization and memory may be only partly observable

Some products expose memory or personalization controls, but the evaluator may not know the complete state used by the system.

A visible setting can be logged. It should not be treated as proof that all personalization effects were controlled.

## 8. Account, interface, device, tier, and region may matter

Results observed on one account, subscription tier, device, product surface, or region may not generalize elsewhere.

The first feasibility shakedown therefore should avoid adding these dimensions unnecessarily. They can be studied later only if the basic within-condition measurement is coherent.

## 9. Small feasibility runs are instrument development, not population estimates

A tiny shakedown is intended to test whether the probe, metadata record, and coding scheme work.

It does not estimate population-wide rates, establish model-level prevalence, or support general claims about all users or deployments.

## 10. Outcome coding can introduce evaluator judgment

Classifying outputs into behavioral categories can require judgment.

The project should therefore:

- define categories before confirmatory collection;
- preserve raw responses;
- allow an ambiguity category where appropriate;
- document coding revisions during feasibility work;
- freeze the coding guide before the formal study.

## 11. Feasibility data should not be reused as confirmatory data

The feasibility shakedown may be used to revise the instrument, coding rules, metadata requirements, or study design.

Because those design choices can be influenced by what the shakedown reveals, the same observations should not later be presented as confirmatory evidence for a threshold or hypothesis selected after seeing them.

## 12. Reproducibility thresholds can be arbitrary if chosen after the fact

The project has not yet defined what will count as “reproducible enough.”

A formal study must state its decision rule before confirmatory data collection and distinguish among:

- sufficiently reproducible;
- insufficiently reproducible;
- inconclusive.

The threshold should be justified rather than chosen to make the observed result look favorable.

## 13. Cross-evaluator replication may still be imperfect

Another evaluator following the same procedure may receive different behavior because of account history, product state, timing, region, or other hidden variables.

That disagreement can be measured, but it limits simple claims of reproducibility.

## 14. Public interfaces may restrict systematic testing

Rate limits, anti-automation systems, product design, terms of service, or interface friction may constrain repeated testing.

The project should not evade safeguards, bypass access controls, or automate in ways that violate platform rules in order to obtain cleaner data.

## 15. Screenshots are insufficient on their own

Screenshots can preserve an example, but they do not establish frequency, reproducibility, or cause.

The project should preserve structured run metadata and repeated observations where possible.

## 16. Black-box evidence supports behavioral claims, not mechanistic claims

The strongest claims available to this project are usually of the form:

- behavior X occurred under documented visible condition Y;
- outcome X recurred across a stated set of repeated runs;
- repeated runs showed a measured degree of consistency or variation;
- later replication did or did not reproduce the earlier pattern.

The project should avoid claims that a particular hidden component, training method, safety mechanism, or internal reasoning process caused the result unless independent evidence supports that conclusion.

## 17. Existing work may make the project unnecessary

The second collision audit is incomplete. A stronger existing methodology may already cover the practical measurement this project is considering.

If so, the project should replicate, contribute, narrow further, or stop rather than preserve a separate identity for its own sake.

## 18. Negative results can be useful without confirming the project

A negative, null, or limiting result may be worth documenting.

That does not mean every outcome supports the same hypothesis. A formal study must specify in advance which outcomes support continuation, which argue against it, and which remain inconclusive.

## 19. The project is not a regulated-domain evaluation

Healthcare, insurance adjudication, real financial data, credentials, and other regulated or high-risk personal data are out of scope for the current phase.

Research from those domains may inform methodology, but the active protocol is intended for synthetic scenarios in public consumer AI systems.

## Current limitation most relevant to the next step

The project does not yet know whether its candidate first measurement can be applied consistently.

That is why the immediate next step is a **small feasibility shakedown after the second collision audit**, not a broad benchmark or longitudinal multi-model study.