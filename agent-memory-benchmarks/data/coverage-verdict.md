# Coverage verdict — agent-memory-benchmarks (run2, 2026-09-12)

FRAME: view = core ring (in + relevant), version = substrate @ 2026-09-12 run2,
denominator = 3,314 candidates, 100% judged. Core = 995.

## Verdict
**Recall is approximately 80%, and 80% is the OPTIMISTIC read.** Roughly **250-290 in-charter
artifacts remain uncaptured.** Confidence: moderate. The estimate rests on two mutually
consistent capture-recapture pairs; the gap is LOCALIZED (below), which is stronger than a bare
percentage but is not a closed denominator.

## Signals [T] — each with its self-check

### 1. Capture-recapture across modalities — USED (two pairs, consistent)
| pair | n_a | n_b | overlap | N_hat | reliable? |
|---|---|---|---|---|---|
| snowball x human-curated (lists+surveys+HF+vendor+proceedings) | 390 | 347 | 109 (17.4%) | **1,236 +/-161** | yes |
| keyword-sweeps (S2+arXiv) x human-curated | 595 | 347 | 161 (20.6%) | **1,279 +/-123** | yes |
| S2 sweep x arXiv sweep | 405 | 428 | 238 (40.0%) | 728 | **DISCARDED** |
The third pair returned N_hat=728 against 993 OBSERVED — an estimate below the observed count is
the signature of positive dependence between the two samples: both sweeps run the same keyword
culture over overlapping indexes, so they are not independent captures. It passed the 10% overlap
gate, which is precisely the case the gate cannot see. Reported, never averaged in.
N_hat is a LOWER bound on the population under heterogeneous catchability (famous benchmarks are
over-captured), so 995/1,240-1,280 = ~78-80% is an UPPER read of recall.

### 2. Reference-pool recall — GATED, DO NOT QUOTE AS RECALL
Computed over 947 core papers with fetched references (33,275 edges, 13,398 distinct cited works).
Raw output: 50.8% recall among works cited by >=15 core papers. **This number is meaningless for
this thread** and is recorded only so nobody re-derives it and believes it. Verified by reading
the top never-captured references: they are GPT-4, Llama 3, Qwen3, Gemini 2.5, Few-Shot Learners,
ReAct, Chain-of-Thought, Toolformer, InstructGPT, MMLU, Natural Questions, RULER. A benchmark
corpus cites mostly models, methods and out-of-charter benchmarks; those absences are CORRECT.
The estimator assumes the reference pool is predominantly in-scope, which is false here.

### 3. Mention-shadow — USED as a LOCALIZER (this is the load-bearing signal)
Filtering the same never-captured reference pool to titles that are BOTH benchmark-shaped AND
memory/horizon-shaped leaves **48 works cited by >=4 core papers that the corpus never captured**
(`scratch/mention-shadow-gaps.json`). Reading them, the gap is not uniform — it has a shape:
- **A literal miss:** *Evaluating the Long-Term Memory of Large Language Models* (280322210, 2025)
  is cited by 4 core papers and names the charter's own construct in its title. It was never
  retrieved by any modality.
- **Temporal-reasoning benchmarks are systematically under-captured** — EvolveBench (280018147),
  TIQ (269762435), ComplexTempQA (280711340). crit_2 names "temporal reasoning over an evolving
  history" explicitly, so these are in-charter; the sweeps' vocabulary skewed to "memory" and
  "long-horizon" and under-weighted "temporal".
- **Lifelong / embodied navigation is under-captured** — GOAT-Bench (269033284, multi-modal
  lifelong navigation), Towards Long-Horizon Vision-Language Navigation (274656539), and the
  classic-RL lineage (Arcade Learning Environment, SMAC) the charter admits as a flagged section.
- The remainder are agent benchmarks with no horizon claim (BFCL, AgentHarm, CharacterEval,
  privacy/safety suites) and are correctly out on crit_2.

### 4. Judge calibration — MEASURED, directional
125 salt judgments over 26 shards: 98.4% same-side, 86.4% exact-tier. All 17 exact misses fall on
two boundary items and 15/17 are one tier HIGH. The fleet reads adjacent-family artifacts
(long-horizon-without-memory-framing; knowledge-editing) as core. **The 582 `in` count is an upper
read of the in/relevant boundary**; the 995 core total is not affected.

## The boundary — what this corpus does NOT cover
1. **Every `asta` paper-finder modality is missing.** Auth failed (401) for all of round 1, so
   find / interactive / snowball / citances never ran. Substituted with filter-independent raw S2
   and arXiv sweeps plus a hand-rolled citation snowball. This is the single largest structural
   hole and a plausible cause of the temporal-reasoning gap above.
2. **~250-290 in-charter artifacts uncaptured**, concentrated per signal 3.
3. **The no-paper stratum is captured but not enumerable.** 79 distinct benchmarks came from HF
   and vendor pages, 25+ with no academic paper at all. Citation-graph signals cannot see them, so
   no capture-recapture estimate covers that stratum — its recall is genuinely unknown.
4. **~420 rows of the 580-row dropped pool were never re-screened.** The screen's false-negative
   rate was MEASURED at 8% on a random 50-row sample, and a corrected re-screen recovered 110 rows
   (44 in-charter). The residual is declared in thread.json `acq_deferred`.
5. **Evidence depth is abstract-only** for the catalog wave; 87.5% of core rows have an abstract
   on disk, so 12.5% are cataloged from title and curated hints alone.
6. **Charter breadth is doing heavy lifting.** 995 in-charter ROWS is far above the 80-160
   BENCHMARKS originally estimated, because the charter admits long-horizon agentic execution
   with or without memory framing. Rows are not artifacts; the distinct-benchmark count comes
   from the dedupe step and will be materially smaller.

## User ruling (2026-09-12)
Presented with the ~80% figure, the user chose to **keep the corpus as-is for now and remain ready
to extract more later**. The gap-closing round is therefore DEFERRED, not refuted; signal 3 above
is its ready-made target list.
