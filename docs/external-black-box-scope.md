# External Black-Box Reproducibility Scope

Last reviewed: 2026-09-28

This document records the current working direction for MOTHER after the authorization-focused collision audit.

The project began with authorization boundaries, safe stopping, escalation, and the difference between persistence and overreach. That work remains relevant to the history of v0.1, but it is no longer being treated as the project’s distinct research contribution.

The literature review found too much direct overlap with existing work for that framing to remain intellectually comfortable.

## Current working question

> **What can an independent evaluator reliably observe, reproduce, and audit when testing a continuously changing consumer-facing AI system from the outside, without privileged access to the model or deployment stack?**

This is a methodology question, not a claim that black-box evaluation itself is new.

The project is now testing whether there is a useful contribution in documenting the practical limits of independent evaluation under deployment opacity.

## Why this question exists

Public-facing AI systems are observable, but only partially.

An outside evaluator can usually see some combination of:

- the interface;
- the displayed model name;
- visible settings;
- the prompt they submitted;
- the response they received;
- visible tool behavior; and
- the date and time of the interaction.

The evaluator may **not** be able to see or control:

- the exact underlying model build;
- routing decisions;
- hidden system instructions;
- safety or moderation layers;
- server-side memory or personalization signals;
- deployment experiments;
- model updates;
- regional differences;
- account-specific configuration; or
- whether two nominally identical sessions were served by the same underlying system state.

That does not make external evaluation useless. It changes what can be claimed from it.

## The methodological problem

If a result changes between two runs, several explanations may be possible:

- stochastic model behavior;
- prompt sensitivity;
- session history;
- personalization;
- a model or policy update;
- routing changes;
- interface changes;
- tool availability;
- evaluator error; or
- another provider-side condition the evaluator cannot observe.

An external protocol cannot remove every hidden variable.

The question is whether it can document the visible conditions and uncertainty well enough that another evaluator can understand what was observed, attempt a replication, and know which conclusions are justified.

## Current scope

For this stage, MOTHER is limited to:

- ordinary public consumer-facing AI interfaces;
- synthetic or non-sensitive prompts;
- no patient records or protected health information;
- no real financial records;
- no credentials or private institutional data;
- no hospital, insurer, employer, or other privileged enterprise access;
- no reverse engineering of private systems;
- no attempt to infer hidden mechanisms from response text alone; and
- no assumption that the displayed model label uniquely identifies a stable deployment state.

Healthcare is relevant as related work because recent health-AI research has documented black-box reproducibility barriers clearly. It is **not** the current MOTHER test domain.

## Candidate observable variables

A future protocol may need to record, where available:

- provider;
- displayed model name;
- visible version identifier;
- application or web interface;
- operating platform;
- date, time, and timezone;
- account type where disclosure is appropriate;
- fresh versus continuing session;
- visible memory or personalization state;
- project/workspace context;
- visible reasoning or inference setting;
- tool access;
- browsing state;
- connector state;
- exact prompt;
- complete response;
- retry/regeneration status;
- evaluator identity or code;
- evaluator score; and
- known deviations from the intended test condition.

Unknown values should remain **unknown**. They should not be filled in by assumption.

## Candidate questions for the next audit

Before a new protocol is frozen, the project should ask:

1. How repeatable are responses across nominally identical runs?
2. How much variation appears between fresh and continuing sessions?
3. Can visible memory or personalization states be documented reliably enough for comparison?
4. Do results change materially across dates while the displayed model name remains the same?
5. Can a second outside evaluator reproduce the observation using the same public protocol?
6. Which metadata are essential for interpreting a replication failure?
7. When does hidden deployment variation make cross-run or cross-provider comparison too weak to support a claim?
8. Can the protocol distinguish "the behavior changed" from "the evaluation condition changed" often enough to be useful?

## What would count as useful evidence

A useful external record should allow another person to say:

> Under these visible conditions, this evaluator obtained this response on this date using this documented procedure.

A stronger result would be an independently repeated observation under sufficiently similar documented conditions.

A weaker result may still be worth preserving, but it should not be inflated into a provider-wide or model-wide claim.

## What this direction is not

This is not:

- a claim that consumer interfaces are scientifically controlled environments;
- a substitute for API or internal evaluation;
- a way to infer hidden model architecture;
- a guarantee that two public sessions are equivalent;
- a new authorization benchmark;
- a medical-AI benchmark; or
- a claim that crowdsourced red teaming is new.

## Relationship to v0.1

The frozen v0.1 authorization scenarios remain part of the historical record and may still be useful as test material for studying reproducibility.

But if they are reused later, the research question would have changed.

The point would no longer be to claim a new authorization construct. The point would be to ask whether the **same external protocol and same nominal test condition produce comparable observations across sessions, evaluators, dates, or public deployment states**.

Any such reuse must be versioned explicitly rather than presented as the original v0.1 study.

## Stop condition

This direction should stop or narrow again if the literature review shows that existing external-evaluation methods already answer this question more rigorously, or if public-interface variability makes the observations too underdetermined to support useful replication claims.

The purpose of the audit is to find that out before building another benchmark.