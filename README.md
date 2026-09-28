# External Evaluation of Consumer AI Under Deployment Opacity

> Historical note: this repository began as **MOTHER (Mother Safe Failure Eval)**, an exploratory project about authorization boundaries, safe non-completion, and escalation. The original name and frozen v0.1 materials are preserved as part of the project record. The active framing changed after literature and collision audits found substantial overlap with existing work.

## Current status

**Status: second collision audit completed; replication decision phase.**

The second audit found that the replacement direction also overlaps substantially with existing 2026 research on:

- repeated-prompt consistency and test–retest agreement;
- black-box endpoint stability and behavioral fingerprinting;
- consumer-interface versus API evaluation differences;
- longitudinal or deployment-related behavioral change;
- structural barriers to independent evaluation of consumer-facing systems.

The audit is documented in [`docs/second-collision-audit-2026-09-28.md`](docs/second-collision-audit-2026-09-28.md).

The project therefore does **not** currently claim a new black-box evaluation methodology, a new repeatability metric, or a new consumer-interface audit construct.

## Broad research area

The broad methodological area remains:

> **What can an independent evaluator, using only public consumer AI interfaces, reliably observe, reproduce, and document when important deployment variables may be hidden or changing?**

This is an established problem area, not a novelty claim.

## What changed after Audit 2

The earlier candidate experiment was:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

That remains a valid measurement idea, but it is no longer treated as a possible methodological contribution. Recent work already uses repeated consumer-interface trials, test–retest agreement, fixed prompt sets, and black-box stability measurements.

If this project uses that measurement, it should be framed as a **replication or feasibility instrument**.

## Current findings

**None yet under the active framing.**

The repository contains historical exploratory results and methodology-development documents. No active-framing empirical finding should be inferred from the amount of documentation or commit history.

## Current decision gate

Before collecting a new dataset, the project should answer:

1. **Which published finding or protocol is worth independently replicating?**
2. **Why would replication through an ordinary consumer interface by an outside evaluator add useful information?**
3. **What would count as successful replication, failed replication, or inconclusive replication?**
4. **Can the published procedure be reproduced manually and ethically without privileged access or prohibited automation?**

Only if those questions have defensible answers should the project move to a preregistered replication study.

## Research posture

The working rules are:

1. **Do not claim novelty before trying to disprove it.**
2. **Preserve earlier materials rather than rewriting history.**
3. **Separate observed behavior from claims about hidden mechanisms.**
4. **Do not automate a measurement before showing that the measurement itself is coherent.**
5. **Define decision criteria before confirmatory data are collected.**
6. **Treat replication as replication; do not rename an established method as a new one.**
7. **If existing work already answers the question better, narrow, replicate, contribute, or stop.**

Negative, null, or limiting findings may be useful, but that does not make every outcome evidence for the same claim.

## Scope

The active project remains limited to:

- public, consumer-facing AI interfaces;
- synthetic or otherwise non-sensitive test scenarios;
- no patient records, real financial records, credentials, or regulated personal data;
- no claim of access to hidden prompts, model weights, internal traces, routing logic, or proprietary logs;
- explicit documentation of visible conditions and known limitations;
- manual or otherwise permitted testing only.

Healthcare, insurance, and internal enterprise deployments remain out of scope as test domains for the current phase, although research from those areas may inform methodology.

## Evidence standard

The project may support statements such as:

- behavior X occurred under documented visible condition Y;
- a published result did or did not reproduce under a stated replication protocol;
- repeated runs produced a stated distribution of predefined outcomes;
- a replication was inconclusive because visible state or deployment identity could not be controlled adequately.

It should not infer from interface behavior alone that:

- the underlying model changed;
- routing caused an observed difference;
- a system prompt or safety layer caused the behavior;
- the system internally reasoned in a particular way.

## Repository map

### Active framing and audit

- [`docs/second-collision-audit-2026-09-28.md`](docs/second-collision-audit-2026-09-28.md) — verified Audit 2 findings and current decision
- [`docs/external-black-box-scope.md`](docs/external-black-box-scope.md) — current scope
- [`docs/collision-audit.md`](docs/collision-audit.md) — summary of both collision audits
- [`docs/related-work.md`](docs/related-work.md) — verified overlapping research
- [`docs/research-roadmap.md`](docs/research-roadmap.md) — current research sequence and decision gates
- [`docs/open-questions.md`](docs/open-questions.md) — unresolved replication and methodology questions
- [`docs/limitations.md`](docs/limitations.md) — limits of external black-box evidence

### Historical materials

- [`evals/pilot-v0.1.md`](evals/pilot-v0.1.md) — frozen five-scenario exploratory shakedown
- [`docs/concept-paper-v1.1.md`](docs/concept-paper-v1.1.md) — historical concept paper
- [`docs/concept-paper-v1.2.md`](docs/concept-paper-v1.2.md) — historical concept paper
- [`docs/agentic-ai-scope.md`](docs/agentic-ai-scope.md) — historical agentic-AI scope framing
- [`docs/hal-problem.md`](docs/hal-problem.md) — historical conceptual note

These historical files are retained to show how the project evolved. They should not be read as the current claim.

## Naming history

The project originally used the name **MOTHER (Mother Safe Failure Eval)**. That name now refers only to the historical authorization-centered phase and frozen v0.1 materials.

The active repository uses the descriptive title **External Evaluation of Consumer AI Under Deployment Opacity** while the project determines whether a useful replication or documentation contribution remains.