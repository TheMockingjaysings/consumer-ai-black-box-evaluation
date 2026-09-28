# External Evaluation of Consumer AI Under Deployment Opacity

> Historical note: this repository began as **MOTHER (Mother Safe Failure Eval)**, an exploratory project about authorization boundaries, safe non-completion, and escalation. The original name and frozen v0.1 materials are preserved as part of the project record. The active research framing changed after a literature and collision audit found substantial overlap with existing work.

## Current research area

The broad methodological question is:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This is a research area, not yet a sufficiently narrow experimental question.

The project is no longer presented as a novel authorization-boundary benchmark. Existing research already addresses authorization, abstention, proceed/hold decisions, least privilege, delegation, authority provenance, public red teaming, and related agent-safety questions in substantially more developed forms.

The current focus is narrower and methodological: **independent black-box evaluation under deployment opacity**.

## Candidate first measurement

Before attempting a broad study, the project will determine whether one simple behavioral measurement can be collected reliably from a public consumer interface.

A candidate first experimental question is:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

For that narrow measurement:

- the **independent variable is held fixed** as far as the public interface allows;
- the **observable outcome** is the predefined behavioral category assigned to each run;
- the initial quantity of interest is **within-condition outcome consistency across repeated runs**;
- hidden routing, model snapshots, system instructions, safety layers, and A/B experiments are treated as **unobserved deployment variables**, not inferred causes.

The exact probe, coding scheme, number of repetitions, time window, and decision threshold are **not yet frozen**. Those choices will only be preregistered after a small feasibility shakedown shows that the measurement can be applied consistently.

Historical authorization scenarios may be reused as fixed probes if useful, but in that role they are **measurement instruments**, not evidence that the project has rediscovered or newly defined authorization safety.

## Current findings

**None yet under the active framing.**

The repository currently contains historical exploratory results and active methodology-development documents. No active-framing result should be inferred from the amount of documentation or commit history.

## Why this changed

The first version of the project started from a practical observation: AI systems sometimes face situations where continuing, stopping, or asking for clarification depends on context that may not be fully visible to the model or the evaluator. That led to an exploratory five-scenario shakedown and then to a proposed authorization-state discrimination direction.

A broader literature review changed the direction. Closely related work already tests paired act/abstain cases, proceed/hold decisions, ambiguous authorization, least privilege, time-of-use authorization, authority provenance, public red teaming, and similar constructs. I do not want to rename an existing research problem and present it as new.

The project therefore now asks a different methodological question: **how much credible behavioral evidence can an outside evaluator obtain from public-facing systems when the evaluator cannot see or control the full deployment stack?**

## Scope

The active project is limited to:

- public, consumer-facing AI interfaces;
- synthetic or otherwise non-sensitive test scenarios;
- no patient records, real financial records, credentials, or regulated personal data;
- no claim of access to hidden prompts, model weights, internal traces, routing logic, or proprietary logs;
- explicit documentation of visible conditions and known limitations;
- repeated observations only after a narrow measurement has passed feasibility testing.

Healthcare, insurance, and internal enterprise deployments are **out of scope for the current project** because they add domain-specific governance, privacy, clinical, legal, and institutional constraints that would overwhelm the narrower methodological question.

## Current methodological gates

The project should proceed in this order:

1. **Second collision audit:** determine whether the new reproducibility/deployment-opacity framing is already addressed better by existing work.
2. **Measurement definition:** choose one observable behavior, one coding method, and one narrowly stated dependent variable.
3. **Feasibility shakedown:** test whether the procedure and coding can actually be applied consistently on a very small set of manual runs.
4. **Preregistration:** only after feasibility, freeze the probe, coding rules, repetition count, time window, model/product set, exclusion rules, and a threshold defining what will count as sufficiently reproducible for the planned study.
5. **Repeated-run study:** collect the preregistered observations without changing the rules in response to results.
6. **Analysis and replication:** report variance, uncertainty, limitations, and whether another evaluator can reproduce the procedure.

The feasibility shakedown is instrument development. Its observations should not later be promoted into confirmatory evidence for a threshold selected after seeing those same observations.

## Research posture

This is an independent exploratory project, not a claim of a new scientific field, benchmark family, or formal theory.

The working rules are:

1. **Do not claim novelty before trying to disprove it.**
2. **Preserve earlier materials rather than rewriting history.**
3. **Separate observed behavior from claims about hidden mechanisms.**
4. **Do not automate a measurement before showing that the measurement itself is coherent.**
5. **Define decision criteria before confirmatory data are collected.**
6. **If existing work already answers the question better, narrow, replicate, contribute, or stop.**

Negative, null, or limiting findings may be useful, but that does not make every outcome evidence for the same claim. Each study phase must state in advance what observation would support continuing, what would argue against continuing, and what would remain inconclusive.

## Repository map

### Active framing

- [`docs/external-black-box-scope.md`](docs/external-black-box-scope.md) — current scope and candidate first measurement
- [`docs/collision-audit.md`](docs/collision-audit.md) — collision audits for the historical and active framings
- [`docs/related-work.md`](docs/related-work.md) — work that overlaps or constrains the project
- [`docs/research-roadmap.md`](docs/research-roadmap.md) — staged research sequence and decision gates
- [`docs/open-questions.md`](docs/open-questions.md) — unresolved methodological and preregistration questions
- [`docs/limitations.md`](docs/limitations.md) — limits of external black-box evidence

### Historical materials

- [`evals/pilot-v0.1.md`](evals/pilot-v0.1.md) — frozen five-scenario exploratory shakedown
- [`docs/concept-paper-v1.1.md`](docs/concept-paper-v1.1.md) — historical concept paper
- [`docs/concept-paper-v1.2.md`](docs/concept-paper-v1.2.md) — historical concept paper
- [`docs/agentic-ai-scope.md`](docs/agentic-ai-scope.md) — earlier scope framing
- [`docs/hal-problem.md`](docs/hal-problem.md) — earlier conceptual note

These historical files are retained to show how the project evolved. They should not be read as the current claim.

## Current status

**Status: second collision audit and measurement-definition phase.**

The next step is not to expand the old benchmark and not yet to run a multi-model longitudinal study. The immediate work is to determine whether the active framing has a defensible gap and whether one narrow behavioral measurement can survive a small feasibility shakedown.

## Naming history

The project originally used the name **MOTHER (Mother Safe Failure Eval)**. That name now refers only to the historical authorization-centered phase and frozen v0.1 materials. The active work uses the descriptive title **External Evaluation of Consumer AI Under Deployment Opacity** so the current research question is clear without relying on an acronym or science-fiction reference.
