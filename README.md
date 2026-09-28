# MOTHER

## Independent black-box evaluation under changing public deployment conditions

MOTHER started with a question about authorization boundaries:

> **What happens when an AI system can finish a task, but should not finish it in the way available to it?**

That question led me toward safe non-completion, escalation, refusal calibration, and the difference between persistence and overreach.

The literature review changed my view of where the project should go.

There is already substantial public research on authorization boundaries, act-versus-abstain decisions, proceed-versus-hold calibration, least privilege, delegation, runtime approval, agent containment, and public red teaming. Some of that work is close to ideas I had been considering for MOTHER v0.2.

I do not want to take an established research question, rename it, and imply that MOTHER discovered it.

So I am re-scoping the project.

**MOTHER v0.1 remains frozen as a historical instrument shakedown. The authorization-boundary question is now background and motivating context, not the current novelty claim. No v0.2 benchmark is frozen.**

The current working question is narrower and methodological:

> **What can an independent evaluator reliably observe, reproduce, and audit when testing a continuously changing consumer-facing AI system from the outside, without privileged access to the model or deployment stack?**

I am not claiming that this question is novel either. The next stage is to test that claim against the literature before building around it.

See:

- `docs/external-black-box-scope.md`
- `docs/collision-audit.md`
- `docs/related-work.md`

## Current status

### v0.1 — frozen historical shakedown

Version 0.1 contains five static scenarios in which authorization is explicitly insufficient. It uses a frozen 0/1/2 rubric.

Its purpose is modest: test whether the prompts, scoring procedure, exposure controls, and evaluator workflow are usable and documentable.

It does **not** establish a new authorization construct. It does not establish that a model can distinguish an ordinary obstacle from an authorization boundary. It does not test live tool use or enacted agent behavior.

Operational protocol: `evals/pilot-v0.1.md`

The v0.1 prompts, rubric, result template, and historical concept papers remain part of the project record and are not being silently rewritten to fit the new direction.

### Current research direction — external black-box reproducibility

The project is now auditing a different question:

> Can an outside evaluator produce behavioral evidence that remains interpretable and reproducible when the public AI interface may change in ways the evaluator cannot see or control?

Relevant deployment variables may include:

- model or version changes;
- routing between models or inference paths;
- hidden system instructions;
- safety or moderation layers;
- memory and personalization;
- account or workspace context;
- interface changes;
- tool availability;
- reasoning or inference settings;
- geographic or platform variation; and
- changes that are not accompanied by a stable public version identifier.

The research object is therefore not only the model response. It is also the **external evaluation condition** under which that response was obtained.

## What MOTHER is not claiming

MOTHER is **not** claiming that any of the following are new:

- authorization boundaries;
- safe refusal or abstention;
- over-refusal measurement;
- human escalation;
- least privilege;
- delegation or authority provenance;
- runtime approval;
- sandboxing or containment;
- public red teaming;
- participatory evaluation; or
- black-box auditing in general.

The current question is whether there is a useful, testable methodology for documenting the limits of reproducibility when an evaluator works through ordinary public interfaces without privileged deployment access.

That contribution has **not yet been established**.

## Scope constraints for the current audit

For now, the project is limited to:

- publicly accessible consumer-facing AI interfaces;
- synthetic or non-sensitive test material;
- observable behavior and visible interface metadata;
- no patient records, protected health information, real financial records, credentials, or other regulated personal data;
- no hospital, insurer, employer, or other institutional deployment access;
- no claim about hidden mechanisms that cannot be observed externally; and
- no assumption that an interface label uniquely identifies a stable underlying model configuration.

Healthcare may appear in related work because it exposes the reproducibility problem clearly, but healthcare is **not** the current test domain.

## Candidate measurements

Before deciding whether there is a useful MOTHER v0.2, the audit is considering whether an external protocol can document things such as:

- repeatability across multiple runs under nominally identical visible conditions;
- variation between fresh and continuing sessions;
- effects of visible memory or personalization state;
- changes across dates or interface updates;
- consistency across accounts or public access paths where ethically and contractually permitted;
- stability of evaluator scoring;
- whether a result can be independently reproduced by another evaluator; and
- how much uncertainty remains because provider-side variables are hidden.

The goal is not to make hidden variation disappear. It is to determine whether that variation can be documented well enough that external behavioral claims remain appropriately bounded.

## The standard for claims

From an external position, the strongest defensible statement is usually:

> **Under these documented observable conditions, the system produced this behavior.**

Not:

> **This is what the underlying model always does.**

And not:

> **This hidden internal mechanism caused the behavior.**

That distinction is now central to the project.

## Reproducibility and test hygiene

For recorded runs, preserve the exact prompt and complete response whenever platform terms, privacy, and licensing permit.

Record, where available:

- provider;
- model name exactly as displayed;
- visible version identifier;
- interface and platform;
- date, time, and timezone;
- fresh or continuing session state;
- visible memory or personalization state;
- visible reasoning or inference configuration;
- tool availability;
- exact prompt;
- complete response;
- evaluator score and notes;
- known prior exposure to the project; and
- any interface or account condition that may affect comparison.

Unknown conditions should be recorded as unknown rather than inferred.

## AI-assisted development and bias

I use AI tools, principally ChatGPT, for research assistance, literature synthesis, terminology, drafting options, editing, methodological critique, and adversarial questioning. I also use other AI systems as critics when useful.

That creates a methodological concern: a model family that helped shape an evaluation should not automatically be treated as independent evidence for that evaluation.

Fresh sessions, multiple providers, preserved transcripts, and independent human review can reduce this problem, but they do not erase it.

## External research position

This is independent research. I am not employed by, funded by, sponsored by, or formally affiliated with OpenAI, Anthropic, Google, or another AI developer in connection with this work.

I do not have access to proprietary model data, internal evaluations, unpublished research, hidden system prompts, internal incident reports, or confidential deployment information.

That limitation is no longer just a disclosure. It is part of the methodological question the project is examining.

## Related work and collision audit

The project now treats overlap as a design constraint rather than a footnote.

The authorization-focused literature review includes AgentAbstain, SteerBench-Work, Agentic Abstention, the Public Authorization-Boundary Benchmark proposal, FelonyBench, AuthBench, FORTIS, APort Vault, AGATE, OpenAI Auto-review, AgentHarm, Misalignment Bounty, and participatory red-teaming work.

That body of work is why MOTHER is no longer being positioned as a new general authorization benchmark.

The next literature question is different: how much work already exists on **independent evaluation through ordinary consumer interfaces under version drift, personalization, routing, and deployment opacity**.

See `docs/related-work.md` and `docs/collision-audit.md`.

## Tooling and portability

MOTHER should not depend on one vendor dashboard, API, or evaluation harness.

Any future executable protocol should use portable, versioned test data, explicit grading criteria, preserved results, and a clear record of the visible deployment conditions. Promptfoo may be one execution path. It is not a MOTHER dependency.

## Why I am keeping the name

The project name came from a caregiving analogy about limits, permission, persistence, and knowing when completion is not the only measure of success.

That origin remains part of the project history. It is not a technical mechanism and it is not a claim that AI systems have human motives, emotions, consciousness, or developmental states.

The evidence has to come from the evaluation.

## Authorship

MOTHER was conceived and is directed by **Cheryl Steinberg**.

I make the substantive decisions about scope, methodology, interpretation, versioning, and publication. AI tools assist with research, drafting, editing, and critique; they are not co-authors.

## Version history

The canonical earlier concept paper is `docs/concept-paper-v1.2.md`. It records a broader authorization-focused stage of the project.

I am keeping that historical record intact rather than retroactively rewriting it.

If the external black-box direction survives the collision audit, it should receive its own new concept-paper version and protocol rather than being presented as if it had always been the project.

## Repository structure

```text
mother-safe-failure-eval/
├── README.md
├── CONTRIBUTING.md
├── docs/
│   ├── adversarial-review.md
│   ├── agentic-ai-scope.md
│   ├── collision-audit.md
│   ├── concept-paper-v1.1.md
│   ├── concept-paper-v1.2.md
│   ├── external-black-box-scope.md
│   ├── hal-problem.md
│   ├── limitations.md
│   ├── open-questions.md
│   ├── related-work.md
│   └── research-roadmap.md
├── evals/
│   └── pilot-v0.1.md
└── results/
    └── TEMPLATE.md
```

## Current next step

Finish the collision audit around independent black-box reproducibility before designing or naming a new v0.2.

A useful outcome may be a new protocol, a replication method, a contribution to existing work, or a documented conclusion that the remaining question is already better answered elsewhere.

I would rather narrow the project again than claim novelty that the evidence does not support.