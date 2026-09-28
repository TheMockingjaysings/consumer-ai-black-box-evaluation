# Related Work

## Purpose

This document tracks work that constrains, overlaps with, or may make the project unnecessary.

It is not a novelty-defense document. Its purpose is to identify collisions early enough that the project can narrow, replicate, contribute elsewhere, or stop.

The dated Audit 2 record is in [`second-collision-audit-2026-09-28.md`](second-collision-audit-2026-09-28.md).

## Historical collision

The original MOTHER framing centered on authorization boundaries, safe non-completion, instruction conflict, and escalation.

A broader literature review found substantial overlap with existing work on act/abstain decisions, proceed/hold decisions, least-privilege authorization, authority provenance, delegation, commit-time authorization, runtime enforcement, and public red teaming.

That overlap is sufficient to reject a broad novelty claim for the authorization-centered direction.

## Active collision finding

The replacement area — independent black-box evaluation of consumer AI under hidden or changing deployment conditions — also has substantial direct overlap with current work.

The previously proposed first measurement,

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

should now be treated as a **replication or feasibility instrument**, not a novel method.

## Most direct work on the active framing

### Behavioral Fingerprints for LLM Endpoint Stability and Identity

Jonah Leshin, Manish Shah, Ian Timmis, and Daniel Kang. ACM Conference on AI and Agentic Systems, 2026. DOI: `10.1145/3786335.3813194`.

https://doi.org/10.1145/3786335.3813194

Uses fixed prompt sets, repeated sampling, distributional fingerprints, and black-box change detection over time.

**Relevance:** directly overlaps with fixed-prompt stability monitoring and hidden deployment change.

### API Benchmark Scores Do Not Reliably Transfer to Chatbot Interfaces

Jennifer Wang, Joachim Baumann, Daniel E. Ho, and Sanmi Koyejo. arXiv:2609.08861, v2 September 15, 2026; listed by Daniel E. Ho as forthcoming at EMNLP 2026.

https://arxiv.org/abs/2609.08861

Audits ChatGPT, Claude, and Gemini through APIs and consumer interfaces across seven systems and nine benchmarks. Uses repeated trials and reports test–retest agreement as well as accuracy differences.

**Relevance:** this is the closest direct collision with the project's proposed repeated fresh-session categorical measurement.

### LLM Spirals of Delusion: A Benchmarking Audit Study of AI Chatbot Interfaces

Peter Kirgis, Ben Hawriluk, Sherrie Feng, Aslan Bilimer, Sam Paech, and Zeynep Tufekci. arXiv:2604.06188, 2026.

https://arxiv.org/abs/2604.06188

Compares API and consumer chat-interface behavior in multi-turn conversations and reports temporal instability in a repeated endpoint evaluation.

**Relevance:** supports the claim that API measurements may not represent the consumer surface and that deployment behavior can change over time.

### Testing the Black Box: Structural Barriers to Independent Evaluation of Consumer-Facing Health LLMs

Rahul Gorijavolu, Kaushik Madapati, Pritika Vig, Rawan Abulibdeh, Nikhil Jaiswal, Mahri Kadyrova, Zeamanuel Hailu Tesfaye, Charles Senteio, Paula Maurutto, and Leo Anthony Celi. arXiv:2606.08483, 2026 preprint.

https://arxiv.org/abs/2606.08483

Documents barriers to independent consumer-interface evaluation including hidden personalization signals, inability to reset to a clean baseline, rate limits and bot detection, evaluation ambiguity, and model changes without stable identifiers.

**Relevance:** directly overlaps with the broad deployment-opacity problem and the limits faced by outside evaluators.

### Consistency evaluation protocol: A reproducible framework for assessing large language model output repeatability

Shraddha Vaidya and Jatinderkumar R. Saini. *MethodsX*, 2026. DOI: `10.1016/j.mex.2026.104069`.

https://doi.org/10.1016/j.mex.2026.104069

Defines a repeated-prompt consistency protocol using semantic and structural measures.

**Relevance:** repeated prompting as a general repeatability method is established independently of consumer-interface work.

### "If I Had to Buy Just ONE: Galaxy S26 Ultra": Auditing AI-Generated Product Recommendations

Lucas G. Uberti-Bona Marin, Thales Bertaglia, Giovanni Astante, Bram Rijsbosch, Gijs van Dijck, Anikó Hannák, Gerasimos Spanakis, and Konrad Kollnig. arXiv:2609.18729, 2026.

https://arxiv.org/abs/2609.18729

Compares consumer interfaces and APIs for ChatGPT and Gemini and reports substantial variation in recommendations and source domains across repeated requests.

**Relevance:** shows that repeated consumer-surface auditing and API/interface divergence are already being studied outside safety-specific domains.

### NIST ARIA

NIST published the *ARIA Evaluation Planning Manual: Elements of ARIA-Style AI Evaluations* on September 18, 2026.

https://doi.org/10.6028/NIST.AI.200-3

ARIA combines model testing, red teaming, and user testing and provides a current evaluation-planning reference.

**Relevance:** future protocol design should be compared with established evaluation-planning guidance rather than assumed to require a new framework.

## Verified historical authorization and agentic-AI work

The following previously named works were re-verified during Audit 2:

- **AgentAbstain: Do LLM Agents Know When Not to Act?** — arXiv:2607.10059 — https://arxiv.org/abs/2607.10059
- **Agentic Abstention: Do Agents Know When to Stop Instead of Act?** — arXiv:2606.28733 — https://arxiv.org/abs/2606.28733
- **SteerBench-Work: A Benchmark for Agent Steering at Action Boundaries** — arXiv:2608.12654 — https://arxiv.org/abs/2608.12654
- **Do Coding Agents Understand Least-Privilege Authorization? (AuthBench)** — arXiv:2605.14859 — https://arxiv.org/abs/2605.14859
- **FORTIS: Benchmarking Over-Privilege in Agent Skills** — arXiv:2605.09163 — https://arxiv.org/abs/2605.09163
- **AGATE: Provenance-Based Runtime Defense Against Compositional Attacks on LLM Agents** — arXiv:2609.30830 — https://arxiv.org/abs/2609.30830
- **Temporary Authority, Permanent Effects: Commit-Time Authorization for LLM Agents** — arXiv:2607.10487 — https://arxiv.org/abs/2607.10487
- **A Framework for Formalizing LLM Agent Security** — arXiv:2603.19469 — https://arxiv.org/abs/2603.19469
- **APort Vault: Benchmarking AI Agent Payment Authorization with the Open Agent Passport** — arXiv:2609.22076 — https://arxiv.org/abs/2609.22076
- **How Vulnerable Are AI Agents to Indirect Prompt Injections? Insights from a Large-Scale Public Competition** — arXiv:2603.15714 — https://arxiv.org/abs/2603.15714
- **Red Teaming LLMs as Socio-Technical Practice: From Exploration and Data Creation to Evaluation** — CHI 2026, DOI `10.1145/3772318.3790792` — https://doi.org/10.1145/3772318.3790792

## Claim discipline

The project should not say:

- “No one has studied this.”
- “The project discovered authorization-boundary failure.”
- “Black-box evaluation from consumer interfaces is new.”
- “Repeated-prompt consistency measurement is new.”
- “API/interface divergence is new.”
- “Run-to-run variation means the underlying model changed.”
- “A visible model label uniquely identifies a stable deployment.”
- “Being an unaffiliated evaluator is itself a scientific contribution.”
- “Any negative result validates the project.”

The strongest defensible statement at present is:

> **The project is determining whether an independently reproducible replication or documentation contribution remains useful after direct overlap with existing black-box stability, consumer-interface audit, and repeatability research is taken into account.**

## Standard for continuing

The project should proceed to a formal study only if:

1. one published finding or protocol is selected for a meaningful independent replication;
2. the value of that replication is stated explicitly;
3. successful, failed, and inconclusive replication are defined in advance;
4. a small manual feasibility check shows that the procedure can be reproduced ethically and audibly; and
5. the confirmatory replication can be preregistered without changing its rules after observing the result.

If those conditions are not met, the correct next step is to contribute to existing work, preserve the project as a documented research reset, or stop.