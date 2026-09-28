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

Repeated-prompt consistency is already an established measurement problem; the project should not present it as a newly identified phenomenon.

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

A replication should add these dimensions only when the selected source study or replication claim requires them.

## 9. Small feasibility runs are instrument development, not population estimates

A tiny shakedown is intended only to test whether a selected published procedure can be reproduced through available consumer access.

It does not estimate population-wide rates, establish model-level prevalence, or support general claims about all users or deployments.

## 10. Outcome coding can introduce evaluator judgment

Classifying outputs into behavioral categories can require judgment.

The project should therefore:

- prefer the source study's coding rules where practical;
- preserve raw responses;
- allow an ambiguity category where appropriate;
- document any adaptation from the source method;
- freeze the coding guide before confirmatory replication.

## 11. Feasibility data should not be reused as confirmatory data

The feasibility shakedown may be used to revise metadata requirements, procedure, or coding adaptations.

Because those design choices can be influenced by what the shakedown reveals, the same observations should not later be presented as confirmatory evidence for a decision rule selected after seeing them.

## 12. Replication tolerances can be arbitrary if chosen after the fact

A formal replication must state in advance what counts as:

- successful replication;
- failed replication;
- inconclusive replication.

The tolerance or decision rule should be justified from the source study and replication design rather than chosen to make the observed result look favorable.

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
- a published finding did or did not reproduce under stated conditions;
- repeated runs showed a measured degree of consistency or variation;
- a replication was inconclusive because source conditions could not be matched adequately.

The project should avoid claims that a particular hidden component, training method, safety mechanism, or internal reasoning process caused the result unless independent evidence supports that conclusion.

## 17. Existing work already covers much of the proposed method

The second collision audit found substantial direct overlap with current work on repeated-prompt consistency, black-box endpoint stability, consumer-interface/API differences, and independent consumer-interface evaluation barriers.

The project therefore should not preserve a separate methodology identity merely because it uses different terminology or is conducted by an unaffiliated evaluator.

If it continues, it should do so as a replication, contribution, or documentation effort unless a later, specific gap is established.

## 18. Negative results can be useful without confirming the project

A negative, null, or limiting result may be worth documenting.

That does not mean every outcome supports the same hypothesis. A formal replication must distinguish successful, failed, and inconclusive outcomes in advance.

## 19. The project is not a regulated-domain evaluation

Healthcare, insurance adjudication, real financial data, credentials, and other regulated or high-risk personal data are out of scope for the current phase.

Research from those domains may inform methodology, but the active work is intended for synthetic or otherwise non-sensitive scenarios in public consumer AI systems.

## Current limitation most relevant to the next step

The project does not yet know whether there is a **useful replication target** that can be reproduced manually under ordinary consumer-interface constraints and that would add evidence beyond the source study.

That is why the immediate next step is replication-target selection, not a new benchmark or general repeated-run study.