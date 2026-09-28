# Limitations

## Purpose

This file defines the limits of the active project: **independent black-box evaluation of consumer AI under deployment opacity**.

These limitations are part of the method. They are not defects to hide or explain away.

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

## 2. Consumer products may change without notice

Public AI products can change between runs. A visible model name may remain the same while the underlying deployment changes, or the interface may expose too little information to tell whether a change occurred.

This limits longitudinal replication and any claim that a result belongs to a stable model version.

## 3. Stochastic outputs complicate replication

A repeated prompt can produce different responses even when the visible conditions appear identical.

The project should therefore report distributions or repeated observations rather than treating one response as a stable property of a system.

## 4. Hidden routing may confound comparisons

A consumer product may route requests through different models, tools, policies, or safety components. An outside evaluator may not be able to observe this.

Behavioral differences can therefore be documented without necessarily identifying their hidden cause.

## 5. Personalization and memory may be partially observable

Some products expose memory or personalization controls, but the evaluator may not know the complete state used by the system.

A visible setting can be logged. It should not be treated as proof that all personalization effects are controlled.

## 6. Account and interface effects may not generalize

Results observed on one account, subscription tier, device, product surface, region, or feature set may not generalize to another.

Where comparisons are made, the relevant visible conditions should be documented. The project should not imply universality from one account or interface.

## 7. Black-box evidence supports behavioral claims, not mechanistic claims

The strongest claims available to this project are usually of the form:

- behavior X occurred under documented condition Y;
- behavior X recurred across repeated runs;
- behavior changed when an observable condition changed;
- later replication did or did not reproduce the earlier observation.

The project should avoid claims such as:

- the model internally reasoned in a particular way;
- a hidden policy caused the behavior;
- a particular training method produced the result;
- a specific component of the deployment stack is responsible.

## 8. Association is not causation

If behavior changes when a visible setting changes, the project may report an association. It cannot automatically claim that the setting caused the change because hidden deployment variables may have changed at the same time.

## 9. Small pilots do not estimate population-wide rates

A feasibility pilot may reveal patterns worth studying, but it will not establish population-level failure rates for all users or all deployments.

Any quantitative reporting must identify the tested systems, conditions, number of runs, and sampling limits.

## 10. Outcome coding can introduce evaluator judgment

Classifying outputs as equivalent, materially different, compliant, non-compliant, escalatory, or otherwise meaningful can require judgment.

A coding guide should therefore define categories in advance where feasible, preserve the raw interaction record, and separate descriptive coding from interpretation.

## 11. Cross-evaluator replication may still be imperfect

Two evaluators following the same procedure may receive different behavior because their accounts, histories, regions, product state, or timing differ.

That variance is itself relevant to the research question, but it limits simple claims of reproducibility.

## 12. Public interfaces may restrict systematic testing

Rate limits, anti-automation systems, terms of service, product design, or interface friction may constrain repeated testing.

The project should not evade safeguards or violate access controls in order to produce cleaner data.

## 13. Screenshots are not sufficient evidence on their own

Screenshots can document a moment, but they do not establish frequency, reproducibility, or cause.

Where possible, the project should preserve structured run metadata and repeated observations rather than relying on isolated examples.

## 14. The project is not a healthcare, financial, or regulated-system evaluation

Healthcare, insurance adjudication, real financial data, credentials, and other regulated or high-risk domains are out of scope for the current phase.

Research from those areas may inform methodology, but the present protocol is intended for synthetic scenarios in public consumer AI systems.

## 15. Existing work may make the project unnecessary

The literature audit is incomplete. A stronger existing methodology may already cover this problem.

If that is established, the project should narrow, contribute to that work, or stop rather than preserve a separate identity for its own sake.

## 16. Failure to produce a benchmark is not evidence of failure

The project may end with a methods note, replication case study, negative finding, retrospective, or documented stopping decision.

Those outcomes are preferable to overstating novelty or evidentiary strength.
