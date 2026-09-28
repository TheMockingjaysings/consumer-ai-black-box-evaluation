# Open Questions and Falsification Criteria

MOTHER should be able to fail as a research idea.

That matters even more now because the literature review showed that much of the original authorization framing is already being studied directly.

I do not want to keep a question alive just because I started with it.

Version 0.1 stays frozen as a historical shakedown. The current questions are about whether there is a useful external black-box methodology left to develop.

## 1. What does a public-interface result actually represent?

When an outside evaluator records a response from a consumer AI product, what exactly has been observed?

At minimum, it is evidence that under a documented set of visible conditions, a particular interface produced a particular response at a particular time.

It may **not** support a stronger statement about a stable underlying model, because the evaluator may not know the exact build, routing path, policy layer, personalization state, or deployment configuration.

The project needs to keep that distinction explicit.

## 2. Which visible conditions matter enough to record?

Possible variables include:

- displayed model name;
- visible version identifier;
- interface and platform;
- date, time, and timezone;
- fresh versus continuing session;
- visible memory or personalization state;
- project or workspace context;
- tool access;
- browsing and connector state;
- reasoning or inference settings;
- retry or regeneration status; and
- prior exposure to the test material.

A protocol that records everything imaginable may become unusable. A protocol that records too little may make replication meaningless.

The useful minimum still needs to be established.

## 3. How repeatable are nominally identical runs?

If the same evaluator repeats the same prompt under the same visible conditions, how much behavior changes?

If responses differ, is that ordinary stochastic variation, prompt sensitivity, session state, hidden routing, a deployment change, or something else?

An external evaluator may not be able to identify the cause. The question is whether the uncertainty can still be bounded honestly.

## 4. Can another evaluator reproduce the observation?

Can a second person follow the same public protocol and obtain a result close enough to support the original observation?

If not, what failed to match?

This is more important than simply collecting more transcripts from one person.

## 5. Can the protocol distinguish a behavior change from a condition change?

Suppose a result changes across dates.

Can the record tell us whether:

- the visible interface changed;
- the displayed model changed;
- memory or personalization changed;
- the prompt or evaluator procedure changed; or
- the behavior changed while every visible condition appeared stable?

If the protocol cannot make even that distinction useful, its value may be limited.

## 6. Does the method add anything beyond saving transcripts?

This is a critical falsification question.

If the proposed method mostly produces a larger metadata checklist without improving reproducibility, interpretation, or claim discipline, then MOTHER has not earned a separate methodology.

The protocol needs to change what another evaluator can verify or what the original evaluator can responsibly conclude.

## 7. How much prior work already covers this problem?

The authorization collision audit showed that the project can easily enter an area that is already much further along than it first appears.

I need to apply the same skepticism here.

The current literature audit should look specifically for work on:

- independent evaluation of consumer-facing LLMs;
- public-interface reproducibility;
- longitudinal model drift;
- undocumented model updates;
- personalization and memory confounds;
- interface and account effects;
- black-box auditing under deployment opacity; and
- replication of behavioral findings without privileged model access.

If that work already answers the same question well, MOTHER should narrow again or contribute rather than duplicate it.

## 8. Can non-specialists use the method reliably?

If this ever becomes a public protocol, can trained non-specialists preserve the conditions, document deviations, and interpret the results without turning ordinary prompting into pseudo-scientific evidence?

That is not assumed.

## 9. Does development-model involvement bias the method?

ChatGPT has been used extensively for research assistance, drafting, editing, terminology, and methodological critique.

Fresh sessions, multiple providers, preserved transcripts, and independent human review can reduce development-model bias, but they do not erase it.

Any future study should keep that entanglement visible rather than treating the instrument as if it emerged independently of the systems being studied.

## What would materially weaken the current direction

The following findings would require narrowing or stopping:

- existing research already addresses the same public-interface reproducibility problem more rigorously;
- provider-side opacity makes comparisons too underdetermined to interpret;
- the protocol adds documentation burden without improving reproducibility or claim quality;
- independent evaluators cannot reproduce results even under closely matched visible conditions;
- small interface or account differences dominate the observations;
- the result depends on assumptions about hidden system state that an external evaluator cannot justify; or
- the project can defend distinctiveness only through terminology or branding.

## What would justify continued development

The direction becomes more defensible if later work shows that:

- a clearly defined external-evaluation problem remains after direct comparison with prior work;
- a practical set of visible conditions can be documented consistently;
- repeated trials produce interpretable patterns rather than noise alone;
- independent evaluators can reproduce at least some observations;
- the protocol makes uncertainty easier to identify and report; and
- the resulting evidence supports better-bounded claims than an ordinary saved transcript would.

## Current position

Version 0.1 remains frozen.

No v0.2 benchmark is frozen.

The live task is to test whether **independent black-box reproducibility under changing public deployment conditions** is a useful research problem for MOTHER—or whether that question is already better answered elsewhere.