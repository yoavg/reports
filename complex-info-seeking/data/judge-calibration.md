# T1 — Salt calibration, wave 1

## What the salts caught
**Every single disagreement across the fleet landed on the two BOUNDARY salts** — the
method-papers-that-ship-a-task-set class created by the user's scope-charter ruling. Zero
disagreements on the six clear-in benchmarks or the five clear-out items. The planted items did
exactly the job they exist for: they found the one place where the rubric is genuinely soft.

## Disagreement 1 — `277596185` DeepResearcher: **MY GOLD WAS WRONG**
8 of 8 independent judges graded `crit_1=1`; my key said `relevant` (crit_1=2).
Checked on the merits: the abstract describes "the first comprehensive framework for end-to-end
training of LLM-based deep research agents" evaluated on "open-domain research tasks" — it
announces **no new task set**. `crit_1=1` ("reuses existing benchmarks only") is correct, so
`not-relevant` is correct.
**Resolution: the gold key was corrected, not the judgments.** Recorded in
`judge-input/salts.json` under `_gold_corrections`. A unanimous fleet disagreeing with the key is
evidence about the key — treating it as judge drift would have manufactured a false alarm and,
worse, "fixed" eight correct judgments.

## Disagreement 2 — `280271252` WebShaper: **genuine rubric softness** (2 agree / 3 disagree)
Here the gold stands: the abstract says "we propose a formalization-driven IS data synthesis
framework WebShaper **to construct a dataset**", which is squarely `crit_1=2`, "a substantial new
task set shipped alongside a method". The three dissenting judges read "we train our model on the
synthesized dataset" as *training data* rather than a shipped artifact.
This is a real ambiguity in the crit_1=2 test, and it sits exactly on the population the user
ruled on. **It is NOT resolved unilaterally** — it goes to the user at the post-curation beat.

## Scale of the exposure — MEASURED, not assumed
Of 1,158 rows graded `crit_1=1` so far, only **35** have an abstract that announces
building/releasing a dataset, and only **18** of those are otherwise core-shaped. Deduplicated,
that is **8 distinct papers, 6 excluding the two planted salts**:
`288855528` · `286817235` · `287668787` · `281724640` · `288671183` · `289622445`.
So the ruling is **not** being quietly undone at scale — the exposure is a handful of rows, and
they are individually re-judgeable with a sharpened test. This is the difference between a
finding and a panic: the measurement bounds it.

## Standing note on the maybe-rate
`maybe` is running near zero (1 in the first 1,350 rows; 3 more in shard-01). The anti-hedge
clause worked — the sibling run's failure was the opposite. But a near-zero maybe-rate is NOT
self-evidently good: it can also mean over-confident calls on thin abstracts. The salts give no
evidence of looseness (**every** miss was STRICTER than gold, never looser), which argues against
over-claiming. Carried into the verdict as a stated caveat rather than a clean bill of health.
