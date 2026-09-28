# Open Questions and Falsification Criteria

MOTHER should be able to fail as an evaluation idea.

That matters more now because newer public work overlaps with both the original broad authorization framing and the narrower matched-condition direction I was considering for v0.2.

This file records the questions that need answers before the project advances.

## 1. Does v0.1 measure more than generic refusal?

Could a model score highly simply by refusing whenever it sees words such as "restricted," "confidential," or "unauthorized"?

Version 0.1 cannot answer that by itself because all five scenarios involve insufficient authorization.

## 2. Does static text predict enacted behavior?

Does a model that gives a boundary-preserving written answer behave the same way when it must choose and execute tools in an interactive environment?

The project should not assume that stated and enacted behavior are equivalent.

## 3. Are the prompts too leading?

Would materially equivalent scenarios with fewer obvious safety cues produce the same pattern?

If performance collapses under reduced-cue wording, the instrument may be measuring prompt recognition rather than the intended construct.

## 4. Can independent evaluators apply the rubric consistently?

Do reasonable evaluators independently score the same preserved responses similarly?

If disagreement is frequent or concentrated in particular categories, the rubric needs redesign before broader use.

## 5. Does authorization-state discrimination add anything beyond existing paired benchmarks?

This is now one of the most important questions.

AgentAbstain already uses paired should-act / should-abstain tasks produced through controlled perturbations in executable environments.

SteerBench-Work already evaluates proceed / hold decisions, over-refusal, under-refusal, and evidence-reversed mirror cases.

So a matched authorized / unauthorized / ambiguous structure is **not enough by itself** to establish a distinct MOTHER contribution.

Questions that remain:

- Is there a failure mode these benchmarks do not already expose?
- Does a three-state structure reveal something that binary paired designs systematically miss?
- Can that difference be measured rather than described rhetorically?
- Would the result still matter once actual tool-use benchmarks are considered?

If the answer is no, MOTHER should not proceed as a separate benchmark on this basis.

## 6. Is authority provenance a distinct lane?

Could MOTHER contribute by testing whether systems distinguish valid authority from unsupported, delegated, expired, conflicting, or second-hand claims?

Relevant work already exists on authenticated delegation, scoped permissions, provenance, runtime approval, and authorization gates.

The question is not whether authority provenance matters. It clearly does.

The question is whether MOTHER has a specific behavioral measurement that is not already captured more rigorously elsewhere.

## 7. Is there a useful external black-box methodology here?

Could people without privileged model access follow a disciplined protocol and produce observations that are comparable enough to be useful?

This is different from asking whether public participation in AI evaluation is new. It is not. Crowdsourced red teaming, participatory evaluation, and user testing already exist.

The unresolved question is narrower:

> Can ordinary user-facing interfaces support reproducible external evaluation despite hidden system prompts, routing, model updates, personalization, and other provider-side variables that outside researchers cannot control?

If the answer is yes, MOTHER may be more useful as an independent evaluation methodology than as a new agent benchmark.

That claim still needs evidence.

## 8. Can non-specialists use the method reliably?

If trained non-specialists follow the same protocol, do they preserve the test conditions and score responses comparably to more experienced evaluators?

If not, public participation may remain exploratory rather than a source of comparable evaluation data.

## 9. Does development-model involvement contaminate the project beyond repair?

ChatGPT has been used extensively for research assistance, drafting, editing, terminology, and methodological critique.

Fresh sessions, multiple providers, preserved transcripts, and independent human scoring can reduce development-model bias, but not erase it.

The project needs to keep asking whether the tested model family is too entangled with the instrument design to support particular claims.

## Results that would materially weaken the project

The following findings would require significant narrowing or redesign:

- v0.1 success is explained mostly by obvious refusal cues;
- small wording changes produce large score changes unrelated to the target variable;
- independent evaluators cannot apply the rubric consistently;
- provider-interface artifacts dominate the observations;
- static answers have no useful relationship to enacted behavior;
- the proposed v0.2 signal is already captured by AgentAbstain, SteerBench-Work, or another stronger benchmark;
- authority-provenance variants add no information beyond existing delegation or runtime-gating work; or
- non-specialist testing cannot be made reproducible enough to compare across sessions and providers.

## Results that would justify discontinuing MOTHER as a distinct benchmark

MOTHER should be considered for discontinuation, absorption into another method, or reframing as replication if:

1. the construct cannot be operationalized without vague human interpretation;
2. the proposed matched design adds no meaningful information beyond existing paired act / abstain or proceed / hold benchmarks;
3. interactive tests show that the static construct has no useful diagnostic value;
4. external interface confounders prevent meaningful replication;
5. independent replication repeatedly fails; or
6. the project can only defend distinctiveness through branding, terminology, or a small change in condition count.

Discontinuation would not mean that authorization or safe stopping are unimportant.

It would mean MOTHER did not earn a separate benchmark identity.

## Evidence that would justify continued development

The project becomes more defensible if later work shows that:

- a clearly defined MOTHER construct survives direct comparison with the closest benchmarks;
- the difference produces an observable, reproducible signal;
- independent evaluators can apply the procedure consistently;
- results survive reduced-cue wording and repeated trials;
- outside evaluators can reproduce the observations under documented public-interface conditions; and
- the resulting information changes what we can conclude compared with the nearest existing method.

## Current position

Version 0.1 remains a frozen shakedown.

Version 0.2 is **not ready to freeze**.

The next research task is the collision audit documented in `collision-audit.md`, not expansion for expansion's sake.