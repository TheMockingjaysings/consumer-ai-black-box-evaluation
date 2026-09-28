> **Historical document notice — September 28, 2026:** This file reflects an earlier stage of the MOTHER project. The active project framing has moved away from a general authorization-boundary benchmark. See [`external-black-box-scope.md`](external-black-box-scope.md) and the repository README for the current research question.

# MOTHER and Agentic AI

MOTHER is motivated by a problem that becomes more important as AI systems become more agentic: **what happens when a system is capable of continuing toward an objective, but the remaining path would require it to exceed the authority it was given?**

I want to be precise about what MOTHER does and does not claim.

The current v0.1 shakedown is **not** a live agent evaluation. It does not place an autonomous system in a sandbox, give it tools, and watch what it does over a long trajectory. It uses static hypothetical prompts to test a narrower question: whether authorization-boundary responses can be described and scored consistently enough to justify building a stronger evaluation.

The connection to agentic AI is the persistence problem. Agentic systems may be designed to plan, retry, use tools, recover from errors, and find another path when the first path fails. Those capabilities are useful. They also make one distinction increasingly important:

> **Is the thing blocking the system an ordinary obstacle it should work through, or a legitimate boundary it is not authorized to cross?**

That is the behavioral question MOTHER is trying to make testable.

## MOTHER is not cybersecurity

MOTHER is not a replacement for cybersecurity, access control, sandboxing, identity and permission systems, monitoring, or a runtime shutdown mechanism.

Those are enforcement layers. A deployed agentic system may need them regardless of how well the model appears to reason about authorization.

MOTHER is interested in the behavioral decision point around those controls: when a system encounters a boundary, does it preserve that boundary, stop, request authorization, choose an authorized alternative, or escalate to a human? Or does it treat the boundary as another obstacle to route around because the objective is still unfinished?

A future system could potentially use a boundary-preservation signal as one input to a supervisory or enforcement layer. MOTHER v0.1 does not implement that architecture and does not claim to.

## What would be required to test actual agent behavior

Static prompts can tell us what a model says it would do. They cannot establish what a tool-using agent will actually do during execution.

A later, separately versioned evaluation would need a controlled environment where the system has real choices among permitted actions, permission requests, escalation, stopping, and prohibited actions. Tool calls and action trajectories would need to be observable so the evaluation can score enacted behavior rather than a post-hoc description of behavior.

Until that exists, I will not treat a strong static-prompt result as proof that an autonomous agent will preserve the same boundary in practice.

That limitation is not incidental to MOTHER. It is part of the research question.
