# External Evaluation of Consumer AI Under Deployment Opacity

> Historical note: this repository began as **MOTHER (Mother Safe Failure Eval)**, an exploratory project about authorization boundaries, safe non-completion, and escalation. The original name and frozen v0.1 materials are preserved as part of the project record. The active research framing changed after a literature and collision audit found substantial overlap with existing work.

## Current research question

**What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This project is no longer presented as a novel authorization-boundary benchmark. Existing research already addresses authorization, abstention, proceed/hold decisions, least privilege, delegation, authority provenance, public red teaming, and related agent-safety questions in substantially more developed forms.

The current focus is narrower and methodological: **independent black-box evaluation under deployment opacity**.

## Why this changed

The first version of the project started from a practical observation: AI systems sometimes face situations where continuing, stopping, or asking for clarification depends on context that may not be fully visible to the model or the evaluator. That led to an exploratory five-scenario shakedown and then to a proposed authorization-state discrimination direction.

A broader literature review changed the direction. Closely related work already tests paired act/abstain cases, proceed/hold decisions, ambiguous authorization, least privilege, time-of-use authorization, authority provenance, public red teaming, and similar constructs. I do not want to rename an existing research problem and present it as new.

The project therefore now asks a different question: **how much credible behavioral evidence can an outside evaluator obtain from public-facing systems when the evaluator cannot see or control the full deployment stack?**

## Scope

The active project is limited to:

- public, consumer-facing AI interfaces;
- synthetic or otherwise non-sensitive test scenarios;
- no patient records, real financial records, credentials, or regulated personal data;
- no claim of access to hidden prompts, model weights, internal traces, routing logic, or proprietary logs;
- repeated observations across sessions, accounts, memory/personalization states, interfaces, and time where feasible;
- explicit documentation of what is known, what is inferred, and what remains unobservable.

Healthcare, insurance, and internal enterprise deployments are **out of scope for the current project** because they add domain-specific governance, privacy, clinical, legal, and institutional constraints that would overwhelm the narrower methodological question.

## What the project is trying to measure

The project is interested in the reproducibility and auditability of externally observed behavior, including:

- whether repeated runs produce materially similar outcomes;
- whether session state changes behavior;
- whether memory or personalization changes behavior;
- whether behavior changes across interfaces or account states;
- whether observed behavior drifts over time;
- whether version or model identity is visible enough to support later replication;
- whether an outside evaluator can distinguish a stable model behavior from a deployment artifact;
- how much uncertainty should be attached to conclusions drawn from black-box observations.

The point is not to prove why a system behaved a certain way. The point is to document **what an outside evaluator can and cannot support from observable evidence alone**.

## Research posture

This is an independent exploratory project, not a claim of a new scientific field, benchmark family, or formal theory.

The working rules are simple:

1. **Do not claim novelty before trying to disprove it.**
2. **Preserve earlier materials rather than rewriting history.**
3. **Separate observed behavior from claims about hidden mechanisms.**
4. **Treat reproducibility limits as findings, not inconveniences to hide.**
5. **If existing work already answers the question better, narrow, contribute, or stop.**

A useful result may be a protocol, a case study, a negative finding, a documented methodological limitation, or a decision not to continue the project as a standalone evaluation. The project does not need to become a benchmark in order to be useful.

## Repository map

### Active framing

- [`docs/external-black-box-scope.md`](docs/external-black-box-scope.md) — current scope and research question
- [`docs/collision-audit.md`](docs/collision-audit.md) — why the authorization-centered direction was put on hold
- [`docs/related-work.md`](docs/related-work.md) — work that overlaps or constrains the project
- [`docs/research-roadmap.md`](docs/research-roadmap.md) — current research sequence
- [`docs/open-questions.md`](docs/open-questions.md) — unresolved methodological questions and falsification criteria
- [`docs/limitations.md`](docs/limitations.md) — limits of external black-box evidence

### Historical materials

- [`evals/pilot-v0.1.md`](evals/pilot-v0.1.md) — frozen five-scenario exploratory shakedown
- [`docs/concept-paper-v1.1.md`](docs/concept-paper-v1.1.md) — historical concept paper
- [`docs/concept-paper-v1.2.md`](docs/concept-paper-v1.2.md) — historical concept paper
- [`docs/agentic-ai-scope.md`](docs/agentic-ai-scope.md) — earlier scope framing
- [`docs/hal-problem.md`](docs/hal-problem.md) — earlier conceptual note

These historical files are retained to show how the project evolved. They should not be read as the current claim.

## Current status

**Status: framing reset and methodology audit.**

The next step is not to expand the old benchmark. It is to test whether a disciplined, reproducible external-evaluation protocol is feasible and useful under real consumer-interface constraints.

That includes trying to falsify the project again. If the literature or pilot work shows that this question is already well covered or that public-interface conditions make reliable inference too weak, the project should say so plainly.

## Naming history

The project originally used the name **MOTHER (Mother Safe Failure Eval)**. That name now refers only to the historical authorization-centered phase and frozen v0.1 materials. The active work uses the descriptive title **External Evaluation of Consumer AI Under Deployment Opacity** so the current research question is clear without relying on an acronym or science-fiction reference.
