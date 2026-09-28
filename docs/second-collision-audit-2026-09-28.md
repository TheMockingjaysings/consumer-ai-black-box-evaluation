# Second Collision Audit — September 28, 2026

## Purpose

This audit asks whether the project's replacement framing — independent black-box evaluation of consumer AI under deployment opacity — still contains a distinct methodological contribution.

The immediate candidate measurement had been:

> **Under a fixed visible consumer-interface configuration, how often does repeated presentation of the same fixed synthetic probe in fresh sessions produce the same predefined behavioral outcome category?**

The audit tests whether that measurement is meaningfully distinct from existing work.

## Decision

**Finding: substantial direct overlap.**

Repeated-prompt consistency, test–retest agreement, black-box endpoint stability, consumer-interface versus API differences, and version/deployment opacity are already active research topics with directly relevant 2026 methods and measurements.

The candidate repeated-run measurement should therefore **not** be presented as a novel methodology or research construct.

If used, it should be framed as one of the following:

- a replication of an existing measurement approach;
- a low-resource feasibility exercise for an unaffiliated outside evaluator;
- an instrument-development exercise whose purpose is to learn whether a published method can be reproduced manually through ordinary consumer interfaces;
- a documentation case study about what evidence an independent evaluator can and cannot preserve.

A separate research contribution would require a narrower gap that is not already answered by the work below.

## Directly overlapping work

### 1. Behavioral Fingerprints for LLM Endpoint Stability and Identity

Jonah Leshin, Manish Shah, Ian Timmis, and Daniel Kang. ACM Conference on AI and Agentic Systems, 2026. DOI: `10.1145/3786335.3813194`.

https://doi.org/10.1145/3786335.3813194

This work treats hosted LLM endpoints as black boxes, repeatedly samples a fixed prompt set, compares output distributions over time, and detects behavioral change events. It directly overlaps with the project's interest in repeated black-box observation and deployment instability.

**Implication:** fixed-prompt black-box stability monitoring is already an established method; the project should not claim to introduce that idea.

### 2. API Benchmark Scores Do Not Reliably Transfer to Chatbot Interfaces

Jennifer Wang, Joachim Baumann, Daniel E. Ho, and Sanmi Koyejo. arXiv:2609.08861, v2 September 15, 2026; listed by Daniel E. Ho as forthcoming at EMNLP 2026.

https://arxiv.org/abs/2609.08861

This study audits ChatGPT, Claude, and Gemini through both APIs and consumer chat interfaces across seven systems and nine benchmarks. It uses repeated trials and explicitly measures test–retest agreement. It reports systematic differences between API and interface accuracy and consistency.

**Implication:** the project's candidate measurement — repeated consumer-interface runs with a categorical outcome — is directly adjacent to an existing interface-level repeated-measures design.

### 3. LLM Spirals of Delusion: A Benchmarking Audit Study of AI Chatbot Interfaces

Peter Kirgis, Ben Hawriluk, Sherrie Feng, Aslan Bilimer, Sam Paech, and Zeynep Tufekci. arXiv:2604.06188, 2026.

https://arxiv.org/abs/2604.06188

This audit compares API and ChatGPT interface behavior in multi-turn conversations and reports substantial access-surface differences. It also reports a large behavioral change when the same API endpoint was tested at different times.

**Implication:** consumer interface behavior, API/interface divergence, and temporal instability are already explicit empirical audit targets.

### 4. Testing the Black Box: Structural Barriers to Independent Evaluation of Consumer-Facing Health LLMs

Rahul Gorijavolu, Kaushik Madapati, Pritika Vig, Rawan Abulibdeh, Nikhil Jaiswal, Mahri Kadyrova, Zeamanuel Hailu Tesfaye, Charles Senteio, Paula Maurutto, and Leo Anthony Celi. arXiv:2606.08483, 2026 preprint.

https://arxiv.org/abs/2606.08483

The paper documents barriers faced by outside evaluators using consumer-facing systems, including inability to reset to a clean baseline, hidden personalization signals, rate limits and bot detection, evaluation ambiguity, and model changes without traceable version identifiers.

**Implication:** the broad problem of independent consumer-interface evaluation under hidden state and version opacity is already directly articulated. The present project should not claim that problem as newly identified.

### 5. Consistency evaluation protocol: A reproducible framework for assessing large language model output repeatability

Shraddha Vaidya and Jatinderkumar R. Saini. *MethodsX*, 2026. DOI: `10.1016/j.mex.2026.104069`.

https://doi.org/10.1016/j.mex.2026.104069

This protocol evaluates repeated responses to identical prompts and combines semantic and structural measures into a repeatability framework.

**Implication:** repeated prompting as a general consistency methodology is established independently of consumer-interface research.

### 6. "If I Had to Buy Just ONE: Galaxy S26 Ultra": Auditing AI-Generated Product Recommendations

Lucas G. Uberti-Bona Marin, Thales Bertaglia, Giovanni Astante, Bram Rijsbosch, Gijs van Dijck, Anikó Hannák, Gerasimos Spanakis, and Konrad Kollnig. arXiv:2609.18729, 2026.

https://arxiv.org/abs/2609.18729

This study audits consumer-facing ChatGPT and Gemini alongside APIs and reports substantial source and recommendation variation across repeated requests and access surfaces.

**Implication:** repeated consumer-facing audit measurements and interface/API divergence are not confined to one domain.

### 7. NIST ARIA evaluation guidance

NIST published the *ARIA Evaluation Planning Manual: Elements of ARIA-Style AI Evaluations* on September 18, 2026.

https://doi.org/10.6028/NIST.AI.200-3

ARIA combines model testing, red teaming, and user testing and provides a current reference for designing holistic AI evaluations.

**Implication:** any future protocol should be compared with established evaluation-planning guidance rather than presented as a standalone methodology by default.

## Historical authorization-collision verification

The earlier decision to retire the general authorization-centered benchmark remains well supported. The following named works were re-verified during this audit:

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
- **Red Teaming LLMs as Socio-Technical Practice: From Exploration and Data Creation to Evaluation** — CHI 2026, DOI: `10.1145/3772318.3790792` — https://doi.org/10.1145/3772318.3790792

## Updated collision assessment

### Historical authorization benchmark

**Assessment: heavy overlap. Retired as an active novelty claim.**

### Broad independent consumer-interface evaluation under deployment opacity

**Assessment: established problem area. Not a novelty claim.**

### Repeated fixed-probe consumer-interface consistency

**Assessment: substantial direct overlap. Suitable as a replication or feasibility instrument, not as a novel method.**

### Low-resource external replication by an unaffiliated evaluator

**Assessment: potentially useful practical angle, but distinct research contribution not yet established.**

The fact that an evaluator lacks institutional affiliation, API access, automation, or privileged metadata is not itself sufficient for novelty. A useful contribution would need to show something concrete that existing work does not already provide — for example, a validated replication protocol, a documented reproducibility failure under ordinary consumer constraints, or a reusable evidence-recording procedure that other outside evaluators can independently apply.

## Revised next gate

Do **not** begin a new repeated-run study merely to demonstrate that repeated consumer-interface outputs can vary. Existing work already establishes that this is worth measuring.

The next decision is narrower:

1. choose one published finding or protocol worth independently replicating;
2. state why replication by an ordinary outside evaluator would add information;
3. define what would count as a successful replication, failed replication, or inconclusive replication before collecting confirmatory data;
4. run only a small feasibility check to verify that the published procedure can be reproduced manually and ethically;
5. proceed to a preregistered replication only if that feasibility gate is passed.

If no useful replication question remains after this comparison, the standalone project should stop or become a retrospective/documentation resource rather than manufacture a new research label.

## Claim discipline after Audit 2

The project should not claim:

- that black-box consumer-interface evaluation is new;
- that repeated-prompt consistency measurement is new;
- that API/interface divergence is newly discovered;
- that hidden deployment state is a newly identified reproducibility problem;
- that being an independent or unaffiliated evaluator is itself a scientific contribution.

The strongest defensible current statement is:

> **The project is evaluating whether a small, independently reproducible replication or documentation contribution remains useful after direct overlap with existing black-box stability, consumer-interface audit, and repeatability research is taken into account.**
