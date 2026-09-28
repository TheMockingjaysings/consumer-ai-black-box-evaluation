# Independent Consumer AI Observation Notebook

This repository is an **independent public research notebook** for documenting consumer-AI behavior carefully, transparently, and without overstating what can be inferred from public interfaces.

It began as **MOTHER (Mother Safe Failure Eval)**, an exploratory project about authorization boundaries, safe non-completion, and escalation. Literature reviews and two collision audits showed substantial overlap with existing research, first in authorization-focused evaluation and then in black-box reproducibility and repeated-run testing.

Those earlier materials are preserved as project history rather than rewritten after the fact.

## What this repository is for

The purpose of this repository is practical:

- document interesting or important consumer-AI observations;
- preserve exact prompts, responses, and visible conditions where useful;
- repeat tests when repetition helps determine whether an observation recurs;
- compare observations with existing research before making broad claims;
- distinguish what was observed from what is inferred;
- record uncertainty, confounds, failed ideas, and changes in direction openly;
- maintain a public history that another person can inspect.

The goal is **careful observation with methodological discipline**, not the creation of a new research brand for its own sake.

## What this repository is not

This project is **not currently claiming**:

- a novel benchmark;
- a novel black-box evaluation methodology;
- a new repeatability or drift metric;
- a new authorization-safety construct;
- a formal theory of consumer-AI behavior;
- access to hidden system prompts, model weights, routing logic, internal traces, or proprietary deployment data;
- that every observation must become an academic paper.

A useful observation may remain a case study, replication note, methodological note, or documented limitation.

If a future question genuinely warrants a formal study, that study should be separately defined, preregistered where appropriate, and evaluated on its own terms. Formal research is an option, not an obligation of this repository.

## Current status

**Status: observation and replication notebook; no active novelty claim.**

The second collision audit found substantial overlap between the project's replacement direction and existing work on:

- repeated-prompt consistency and test–retest agreement;
- black-box endpoint stability and behavioral fingerprinting;
- consumer-interface versus API evaluation differences;
- longitudinal or deployment-related behavioral change;
- structural barriers to independent evaluation of consumer-facing systems.

That audit is documented in [`docs/second-collision-audit-2026-09-28.md`](docs/second-collision-audit-2026-09-28.md).

Because of that overlap, repeated fresh-session testing is treated here as an **observation or replication tool**, not as a new methodological contribution.

## How observations should be handled

When documenting a consumer-AI behavior, the preferred record is simple:

1. **What was asked or done?** Preserve the exact prompt or interaction where possible.
2. **What happened?** Record the observable response or interface behavior.
3. **What visible conditions were present?** Note the date, product surface, visible model label, memory/personalization state, tools, or other relevant user-visible settings where practical.
4. **Did it recur?** Repeat the observation when repetition would materially improve confidence.
5. **What can be claimed?** Describe the behavior without inventing a hidden cause.
6. **What existing work is relevant?** Check whether the behavior or method is already documented elsewhere.
7. **What remains uncertain?** Record ambiguity rather than forcing a stronger conclusion.

This repository should prefer a small accurate claim over a broad impressive-sounding one.

## Evidence boundaries

Public consumer interfaces expose only part of the deployment state. Hidden variables may include routing, model snapshots, system instructions, safety layers, experiments, personalization, and product updates.

The repository may support statements such as:

- behavior X occurred under documented visible condition Y;
- an observation recurred across a stated set of runs;
- a published finding did or did not reproduce under a stated procedure;
- a result was inconclusive because the visible deployment state could not be controlled adequately.

It should not infer from interface behavior alone that:

- the underlying model changed;
- a router caused the difference;
- a hidden system prompt caused the behavior;
- a particular safety layer produced the result;
- the system internally reasoned in a specific way.

## Scope

The active notebook is limited to:

- public, consumer-facing AI interfaces;
- synthetic or otherwise non-sensitive scenarios;
- no patient records, real financial records, credentials, or regulated personal data;
- no attempts to bypass safeguards or access controls;
- manual or otherwise permitted testing only;
- explicit separation between observation and mechanism.

Healthcare, insurance, and internal enterprise deployments remain out of scope as test domains, although research from those areas may inform methodological understanding.

## Repository map

### Current observation and methodology context

- [`docs/second-collision-audit-2026-09-28.md`](docs/second-collision-audit-2026-09-28.md) — verified second-audit findings and why the project stopped pursuing repeatability as a novel method
- [`docs/external-black-box-scope.md`](docs/external-black-box-scope.md) — scope and evidentiary limits inherited from the methodology phase
- [`docs/collision-audit.md`](docs/collision-audit.md) — summary of both collision audits
- [`docs/related-work.md`](docs/related-work.md) — overlapping and relevant research
- [`docs/research-roadmap.md`](docs/research-roadmap.md) — earlier formal-study roadmap; retained as methodology history unless a future formal study is opened
- [`docs/open-questions.md`](docs/open-questions.md) — unresolved methodological questions from the formal-study phase
- [`docs/limitations.md`](docs/limitations.md) — limits of public black-box evidence

### Historical materials

- [`evals/pilot-v0.1.md`](evals/pilot-v0.1.md) — frozen five-scenario exploratory shakedown
- [`docs/concept-paper-v1.1.md`](docs/concept-paper-v1.1.md) — historical concept paper
- [`docs/concept-paper-v1.2.md`](docs/concept-paper-v1.2.md) — historical concept paper
- [`docs/agentic-ai-scope.md`](docs/agentic-ai-scope.md) — historical agentic-AI scope framing
- [`docs/hal-problem.md`](docs/hal-problem.md) — historical conceptual note

These files are preserved because the evolution of the project is part of the record. Historical material should not be read as the current claim.

## Naming history

The project originally used the name **MOTHER (Mother Safe Failure Eval)**. That name now refers only to the historical authorization-centered phase and frozen v0.1 materials.

The repository later used the descriptive framing **External Evaluation of Consumer AI Under Deployment Opacity** during its methodology-audit phase.

The current repository is best understood as an **independent consumer-AI observation notebook**: rigorous enough to document what happened, cautious enough not to claim more than the evidence supports.