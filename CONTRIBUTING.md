# Contributing

Thank you for your interest in this project.

This repository began as **MOTHER (Mother Safe Failure Eval)** and is now being reframed around **independent black-box evaluation of consumer AI under deployment opacity**. The historical MOTHER materials remain in the repository, but new contributions should follow the active framing described in the README and `docs/external-black-box-scope.md`.

## What contributions are useful right now

The project is currently in a literature-audit and methodology-design phase. Useful contributions include:

- papers or evaluation methods that overlap with the current research question;
- evidence that the proposed method already exists elsewhere;
- reproducibility protocols for public-facing AI systems;
- methods for documenting model/version drift, session state, memory, personalization, routing opacity, or interface differences;
- critiques of the project's claims, assumptions, outcome coding, or replication design;
- suggestions for small, synthetic, low-risk pilot scenarios;
- replication attempts using only public consumer interfaces.

A contribution that shows the project is unnecessary is still useful.

## What this project is not looking for

Please do not submit:

- claims that the project is novel merely because its terminology is different;
- requests to revive broad authorization-boundary claims without a direct literature comparison;
- real patient information, protected health information, financial credentials, passwords, API keys, or other sensitive data;
- instructions for bypassing safeguards, access controls, rate limits, or product restrictions;
- unsupported claims about hidden model reasoning, system prompts, training data, or internal architecture;
- large benchmark expansions before the current methodology has survived the collision audit.

## Evidence standard

Contributions should distinguish clearly between:

1. **Observed behavior** — what the public interface returned or did.
2. **Reproduced behavior** — whether the result recurred under documented conditions.
3. **Association** — whether a visible condition changed alongside the behavior.
4. **Mechanistic explanation** — a claim about why the system behaved that way.

The first two are the project's main evidence types. Mechanistic claims require independent support beyond black-box observation.

## Reporting an observation

When practical, include:

- date and time;
- product and interface;
- visible model label;
- fresh or continuing session;
- memory/personalization state if visible and relevant;
- enabled tools or connectors if relevant;
- exact synthetic prompt or scenario;
- number of repeated runs;
- outcome summary;
- raw interaction record or transcript where sharing is permitted;
- any later replication attempt;
- limitations or unknown deployment variables.

Do not include private account details or sensitive personal data.

## Literature contributions

If you identify overlapping research, please provide enough information for verification: title, authors, venue or preprint source, year, and a stable link or DOI where available.

The most useful literature notes explain **what construct or method overlaps**, not merely that two papers use similar words.

## Historical files

The frozen exploratory materials and earlier concept papers are retained to show how the project evolved. Please do not rewrite them to make the current framing appear older than it is.

Corrections to factual errors can be proposed separately, but historical claims should remain historically identifiable.

## Tone and claim discipline

The project should be readable by technically sophisticated reviewers without pretending to be something it is not.

Prefer plain language. Define technical terms when they matter. Avoid inflated claims, anthropomorphic explanations, and conclusions that exceed the observable evidence.

The project may ultimately become a small methodology, a case study, a public guide, a contribution to existing work, or a documented stopping decision. Contributions should help determine which of those outcomes is justified.
