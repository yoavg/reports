# Coverage verdict — long-horizon / many-subgoal LLM-agent evaluation artifacts, 2025–2026

**As-of: 2026-09-13.** Computed over `observations.jsonl` (4,327 records) after the last data
change (w2 + w3 judging merged, substrate rebuilt, `validate.py` green).

## The number
**CORE = 508 papers** (186 `in` + 322 `relevant`), from 4,327 candidates, 2,191 judged.

## Denominator regime — READ THIS BEFORE QUOTING ANY FRACTION
This thread is **MIXED**, and the two halves support very different claims:
- **The closed, countable part.** Two enumerable populations were swept end-to-end: the
  parametric canon list (85 seeds, 59 era-eligible) and the maintained community
  registries/leaderboards (168 entries enumerated, 156 resolved = **93% resolve rate**). Against
  these, committed fractions are meaningful.
- **The open part — "all 2025–26 papers describing such an artifact" — has NO enumerable
  denominator.** arXiv has no "long-horizon multi-goal agent benchmark" category. For this part
  the corpus **samples**; it does not enumerate. No percentage-of-the-field is definable, and
  none is claimed below.

## Estimate of what is missing
Capture–recapture, **calibrated pairing only** (paper-finder-FILTERED vs FILTER-INDEPENDENT —
parametric ∪ co-citation ∪ forward-citation ∪ registry):

| | |
|---|---|
| n_a (PF-filtered) | 343 |
| n_b (filter-independent) | 356 |
| overlap | 191 (37.6% — genuine co-capture, `reliable: true`) |
| captured | 508 |
| N̂ | 639 ± 41 |
| **estimated missing** | **≥131 — a LOWER BOUND, never a point estimate** |

**Two corrections the reader must apply, not skip:**
1. **History says double it.** Across five measured cold verdicts in this methodology, true
   missing has run **~1.8–2.5× the verdict's own stated bound**. The honest working range is
   therefore **roughly 130–320 missing in-scope artifacts**, i.e. captured share plausibly
   **~60–80%** of the reachable population — not the 79% the raw N̂ implies.
2. **62% of the core was found by exactly ONE modality** (152 by asta-find alone, 149 by
   forward-citation alone). A high single-modality share is the standard under-sampling smell,
   and it WIDENS the range above rather than sitting beside it.

**The forbidden pairing, computed deliberately to show why it is not quoted:** parametric memory ×
curated web lists — two fame-coupled enumerators — returns N̂=137 against 508 already captured, an
impossible answer. Fame-coupling collapses N̂; this is why only the filtered/independent pairing
is reported.

## External anchors (you cannot prove completeness from inside the set)
1. **Known-canon anchor** (parametric enumeration, blind to retrieval). 59 era-eligible seeds:
   20 landed in core, **11 were judged OUT with clean charter reasons** (WebGames = "50+
   independent one-shot browser challenges"; ScreenSpot-Pro; MCP-Bench; DeepResearch Bench;
   EmbodiedEval; MemBench; METR; HCAST), 10 maybe, 18 were captured-but-unjudged → sent to the w3
   top-up. Deliberate exclusion, not blindness — that is what this anchor is for.
2. **External-enumeration anchor** (16 maintained community lists: awesome-* rosters, UK AISI
   `inspect_evals`, HAL, BrowserGym, Meta ARE, HuggingFace, survey tables). **93% resolve rate**;
   of 113 era-eligible entries, 34 → core, 31 judged out, 13 maybe, 35 captured-but-unjudged.
3. **Infrastructure-adjusted reference-pool recall.** Raw recall over 7,207 works cited by the
   447-paper core looks poor — 87% @≥15 core-citations, 77% @≥10, 67% @≥7, 57% @≥5, 45% @≥3.
   Triaging the 102 never-captured works cited by ≥7 core papers explains it: **76 (75%) are
   pre-2025** (era charter-out), 7 are substrate (Qwen3, DeepSeek-R1/V4, Qwen2.5-VL, G-Eval),
   3 are memory *systems* not eval artifacts (A-MEM, Mem0, MIRIX), and only 16 are 2025–26 —
   nearly all of which fall out under the thread's own rulings (HealthBench and BrowseComp-Plus
   single-goal; MCP-RADAR tool-chaining; π0.5 and Hi Robot are VLA models; PersonaLens
   personalization; NoLiMa long-context). **The depressed recall is the BOUNDARY, not blindness.**
   Same story in missed-high-centrality: the top 20 uncaptured nodes (WebArena, SWE-bench,
   AgentBench, ToolLLM, ReAct, GAIA, τ-bench, ALFWorld, Generative Agents, AppWorld,
   TheAgentCompany, OSWorld, WorkArena, WebVoyager, WebShop, Llama 3, GPT-4o card, DeepSeek-R1)
   are **all** pre-2025 or substrate. Zero in-scope 2025–26 misses in either list.

## Coverage as a FAMILY × ERA MATRIX (never a scalar — misses concentrate)

| family | 2025 | 2026 | core |
|---|---|---|---|
| business / office / enterprise | 42 | 94 | 136 |
| personal assistant & memory | 16 | 78 | 94 |
| multi-agent org & society | 32 | 37 | 69 |
| embodied & robotics | 25 | 23 | 48 |
| web / GUI | 22 | 22 | 44 |
| games & interactive fiction | 16 | 12 | 28 |
| science & deep research | 4 | 17 | 21 |
| travel & constraint planning | 8 | 10 | 18 |
| customer service & dialogue | 4 | 14 | 18 |
| tool / API use | 4 | 11 | 15 |
| OS / computer-use | 2 | 6 | 8 |
| healthcare / clinical | 0 | 5 | 5 |
| **total** | **175** | **333** | **508** |

**Read the thin cells as UNRESOLVED, not as covered.** Self-consistent holes look healthy from
inside; detecting them properly needs an external per-cell volume prior this run does not have.
Two cells are internally flagged:
- **healthcare/clinical 2025 = 0** with 5 in 2026 — an era-dip in a family that certainly existed
  in 2025 (MedAgentBench, AgentClinic are 2024/25). Likely a real corpus-thin cell.
- **OS/computer-use = 8 total** is implausibly small for a family with OSWorld, WindowsAgentArena
  and a large 2025–26 literature — but most of that literature is single-task GUI work that
  crit_3 legitimately excludes. Partly boundary, partly thin; not resolved.
The **personal-assistant/memory 2025:2026 = 16:78 split** is a genuine field shift (the
multi-session-agent literature is mostly 2026), amplified by the parametric anchor's 2026
blindness. Treat the 2025 memory cell as under-sampled.

## Named loss terms (every estimator is blind to at least one of these)
1. **Retrieval filter false-negatives — MEASURED, not assumed.** 60 papers sampled at random from
   the 2,177 the paper-finder filter dropped, judged blind: **0 `in`, 0 `relevant`, 8 `maybe`,
   52 out**. 4 of the 8 maybes were already in the corpus via another modality. Confirmed FN rate
   **0/60 → ≤5% (rule of three)**; **≤13%** if every unsettled maybe is counted against it.
   Limit: sidecar rows carry title only, so this BOUNDS the rate rather than pinning it.
   Full write-up: `coverage/fn-probe.md`.
2. **Deferred tail — sampled, not enumerated.** Prior deciles 4–9 (2,246 candidates) were covered
   by an 80-per-decile stratified sample under a **numerically pre-stated** escalation rule
   (`judging-plan.md`, written before any judgment was seen): escalate a decile to full judging
   iff its sampled yield ≥0.12. **No decile reached it** (0.100, 0.087, 0.087, 0.062, 0.025,
   0.000). Derived residual by extrapolating the judged yield gradient: **~135 further relevant
   papers sit unjudged in the tail** (lower bound; up to ~390 if every tail `maybe` resolved
   positive). This is the single largest loss term and it is a deliberate, measured deferral.
3. **Truncation / un-escalated depth.** The staged sweep policy's DILIGENT leg never ran: the
   paper-finder backend refused all 13 escalations (`FastBroadSearch failed to respond`,
   `APIConnectionError`, DNS `Errno 8`). Only the thread's primary question ran diligent. The 13
   flagged angles retain **4,186 un-probed `not_judged` sidecar drops** (robotics 424, lh-general
   270, shopping 80, crafting-tree 71, continual-lifelong 62, planning 61, household-behavior 50,
   computer-use 39, milestone 33, multi-objective 33, personal-assistant 33, and others).
   Compensation: a 20-angle axis-switched fast sweep, which yielded **581 new candidates → 37 new
   core**. The substitution paid, but it is not the same as depth.
4. **Ingestion loss — found only by the anchors.** 51 papers named by the canon or registry
   anchors were captured but had never reached a judge. Judged in w3: **17 became core (33% yield
   — 3–5× the random tail-sample yield)**, rescuing ClinEnv, CitySim, CityReal, SC2Arena,
   DecisionBench, RoboCasa365, LifeSciBench, DRBench, HealthAgentBench, Agents' Last Exam,
   WebMall, VideoGameBench. No internal signal saw these; only the external anchors did.
   **Implication: a comparable slice probably remains in the unjudged tail.**
5. **Off-index artifacts.** 8 registry-named artifacts have no S2 record at all and are therefore
   absent from every citation-based signal: HORIZON Leaderboard · Harvey Long Horizon Legal Agent
   Benchmark · Manager Coercion Benchmark · MemoryCode · OmniMemEval · PinchBench · TDW-MAT/C-WAH ·
   WebTaskBench. They exist; the corpus cannot represent them.
6. **The 2026 stratum has no parametric anchor.** Only 1 of 85 canon seeds was 2026, yet 333 of
   508 core papers are. The 2026 half of this corpus rests on retrieval and forward-citation
   alone and is **not** externally validated by the canon anchor. It is the least-verified half.
7. **Residual `maybe` ring: 109 papers** (38 survived a deliberate second pass). Unresolved.
8. **Scope drift control:** all numbers recomputed over `observations.jsonl` @ 4,327 records after
   the final merge. Earlier figures in this run's history (447 core) predate w2/w3.

## Estimators: used and GATED (a silently skipped estimator is indistinguishable from a forgotten one)
- `capture_recapture_modalities` (PF-filtered × filter-independent) — **USED**, reliable=true.
- `capture_recapture_modalities` (parametric × registry) — **COMPUTED AND REJECTED**: fame-coupled
  enumerators, N̂ < captured. Reported only as a demonstration.
- `reference_pool_recall` — **USED after repair.** First run was invalid (`core_with_edges: 20`);
  references refetched for all 447 then-core papers (429 resolved) and recomputed.
- `citation_graph` missed-high-centrality — **USED**, fully triaged.
- `unseen_class_incidence` (Chao1 on citation incidence) — **GATED**: requires relevance labels on
  external references; label coverage over the 7,207-work cited pool is far below 1, which would
  make it a lower bound on a lower bound. Not run.
- `strategy_decay` — **GATED**: needs ≥8 ordered per-query yields for one strategy; the sweep was
  fanned out in parallel with no reliable per-query cumulative ordering, and the run's own receipt
  says the fit is unidentifiable below ~25 sequential points.
- `eigenvector_centrality` — **NOT USED as a signal**; its role (ranking prior) was served by the
  deterministic composite prior in `work/prior.py`.
- `yield_by_frequency` — superseded by the decile yield gradient, which is the same idea computed
  over this run's actual strata.

## Confidence and what you may conclude
**Confidence: MODERATE.**
- **You MAY conclude:** the corpus contains the large majority of what a well-resourced search of
  the 2025–26 academic literature would surface for this question; that its boundary is
  deliberate and auditable (every major exclusion traces to a stated user ruling with a judge's
  reason attached); and that the named 2025–26 artifacts the field's own lists consider notable
  are in it or explicitly judged out.
- **You MAY NOT conclude:** that it is exhaustive; that any family's count is the field's true
  count; that a thin cell is genuinely thin; or that "no benchmark does X" — an absence claim
  needs a targeted check against the papers, not this corpus's silence.
- **Head vs tail, stated separately:** the HEAD (prior deciles 0–3, 1,489 papers judged in full,
  externally anchored by canon + registry) is well covered. **The TAIL is SAMPLED, not enumerated.**

**Refresh trigger.** This field publishes several qualifying artifacts per week — 333 of 508 core
papers are 2026 alone. Treat this corpus as **stale after ~6–8 weeks**. Re-run the forward-citation
modality (cheapest, highest-yield here: 62% of core, 149 of them found by nothing else) plus the
registry enumeration; a full re-sweep is not needed before ~6 months.

**The cheapest calibrator of all is a second independent run.** For anything high-stakes resting
on these counts, that is the recommendation.
