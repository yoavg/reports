# Signal: retrieval false-negative probe (wave D) — MEASURED, not assumed

**What it is.** Paper-finder's own relevance filter drops documents before they ever reach the
result set. `--include-rejected sample` writes those drops to a sidecar. Across 35 fast sweeps
the sidecars sampled **2,177 distinct dropped documents** (the full drop volume was larger:
`not_judged` totalled 4,186 and `metadata_filtered` ~8,000 across queries). A random sample of
**60** (seed 20260913) was judged by a fleet worker under the same rubric as every other
candidate, blind to the fact that they had been dropped.

**Result.**

| tier | n |
|---|---|
| in | 0 |
| relevant | 0 |
| maybe | 8 |
| not-relevant | 52 |

**Zero clearly-relevant papers were found in the dropped pool.**

**The 8 maybes, and what happened to them.** All 8 were tiered `maybe` for the same reason: the
sidecar rows carry **title only — no abstract and no year** — so the judge could not settle
crit_3/crit_4 and correctly refused to guess. Cross-checking those 8 titles against the corpus:

- **4 of 8 are already in the corpus**, captured by another modality (Game-Theoretic Lens on
  LLM-based Multi-Agent Systems · EmbodiedBrain · POLARIS · RiskWebWorld — all found by
  asta-find, two also by forward-citation). The filter dropped them on one query; a different
  query or modality caught them. This is multi-modal acquisition doing exactly its job.
- **4 of 8 are NOT in the corpus**: TrajLLM (agent-based human-trajectory simulation) ·
  SmartBench (Chinese smartphone assistant) · Towards General Computer Control with Hierarchical
  Agents · A Comprehensive Survey of Agents for Computer Use (a librarian, not a member).

**The number to quote.** Unrecovered-and-possibly-relevant = **4/60 = 6.7% of the sampled
dropped pool**, every one of them unsettled rather than confirmed. Clearly-relevant
false-negative rate = **0/60**; by the rule of three the 95% upper bound on that rate is
**5%**. Taking the maybes at face value as an upper bound instead gives **13%**.

**Honest limits of this signal.**
1. Title-only evidence. The probe is a weaker test than the main judging; it bounds the rate, it
   does not pin it. A judged `maybe` here would often resolve to not-relevant with an abstract.
2. It measures only the SAMPLED drops, not the full `metadata_filtered` volume — much of which
   is dropped on year/venue metadata and is legitimately out for a 2025–26 thread.
3. It speaks to ONE filter. Every paper-finder surface (find / interactive / snowball /
   citances) shares that filter, so this number is the shared-lineage loss term for all of them
   at once — and says nothing about the filter-independent modalities.

**Consequence for the verdict.** The retrieval filter is not a major source of loss on this
thread. It is a NAMED, MEASURED term at ≤5–13%, not an unquantified hedge — and 4 of the 8
borderline drops were recovered by other modalities, which is direct evidence that the
multi-modal design is absorbing filter error rather than inheriting it.

**Follow-up owed:** resolve and judge the 4 never-captured titles properly (with abstracts)
before the coverage verdict closes.
