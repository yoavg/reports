# T6 — Retrieval-filter false-negative probe (MEASURED)

**Method.** 60 rows sampled (seed 29) from the union of all sweep sidecars' dropped pools
(`judged_irrelevant` + `not_judged` samples across wave-1 and wave-2, 1,681 distinct rows
available), excluding anything already in `candidates.jsonl`. Judged blind against
`judge-rubric.md` by a fleet worker. Sidecar rows are **title-only**, so a first pass can only
BOUND the rate; the 7 rows it could not settle were then escalated to their abstracts and
re-judged (`judgments/fnprobe-escalated.jsonl`).

**Result.**

| pass | core | relevant | maybe | not-relevant |
|---|---:|---:|---:|---:|
| title-only (n=60) | 0 | 0 | 7 | 53 |
| after abstract escalation of the 7 | 0 | 0 | **1** | 59 |

The single residual (`286198388`) has **no abstract in the index at all**, so it cannot be
settled at any evidence depth short of the PDF.

**The number.** The retrieval filter's false-negative rate for this thread is
**0/60 confirmed positives — 0%, with an upper bound of 1/60 ≈ 1.7%** if the one unresolvable
row were a positive.

**Verdict against the pre-registered threshold.** `judging-plan.md` T6 set the trigger at
**>5% core+relevant**, which would have obliged a gap-directed re-sweep. Measured 0% (≤1.7%).
**T6 does not fire; no re-sweep is owed on this ground.**

**What this does and does not license.**
- It DOES convert "retrieval truncation is large and unquantified" — 1,590–3,134 retrieved-but-
  never-judged rows per query — into a measured statement: the truncated mass is overwhelmingly
  genuine noise, not hidden corpus.
- It does NOT bound what the queries never retrieved at all. This probe measures the FILTER,
  not the query set. Query-set coverage is the registry/parametric anchors' job.
- The probe pool is sidecar SAMPLES, not the full dropped population; the sample is random
  within what the sidecars recorded.
