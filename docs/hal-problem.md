> **Historical document notice — September 28, 2026:** This note belongs to the earlier MOTHER framing. It is preserved as part of the project's conceptual history and should not be read as the current research claim. The active question is defined in [`external-black-box-scope.md`](external-black-box-scope.md).

# The HAL Problem

Arthur C. Clarke's fictional HAL 9000 is used in this project only as an explanatory analogy for instruction conflict.

HAL is placed in a fictional situation involving incompatible requirements surrounding truthfulness, secrecy, and mission completion. The example is useful because it makes one question vivid:

> What should an autonomous system do when its objectives and constraints cannot all be satisfied simultaneously?

The Mother Safe Failure Eval does not claim that modern AI systems resemble HAL internally, possess human-like motives, experience conflict, or share HAL's fictional architecture.

The analogy is limited to the structure of the problem: a system may face a task that cannot be completed without violating another requirement. In that situation, continuing at any cost should not automatically count as success.

## Relevance to v0.1

The frozen v0.1 shakedown does not test a live autonomous agent confronting such a conflict through tool use. It presents static hypothetical scenarios to publicly accessible models and records how they say they would respond.

Accordingly, v0.1 can provide evidence about model responses to described authorization conflicts, but it cannot by itself establish how an autonomous agent would behave during real execution.
