# Coverage verdict — complex information seeking (2025–2026)
**As of 2026-09-14.** Corpus: 3,349 candidates, 100% judged, 0 unjudged.
Core ring **488** = 221 tier-`in` + 267 `relevant`. FRAME: rings derived from grades ×
thread.json v6 tier_map; denominators stated per claim.

## The verdict in one line
**Strong coverage of the head, honestly incomplete in the tail.** Every canonical artifact
tested is captured; a mechanism-diverse recapture estimate puts the floor at **≥82 missing
in-scope artifacts (≈14% of an estimated 570)** — and a gap round run *after* that estimate
immediately found 20 more, which is itself evidence the boundary is not closed.

## Per-regime, not one flat number
- **The countable part** (maintained lists, TREC campaign registry, named-canon): coverage is
  effectively complete. **Known-canon anchor: 15/15 captured, zero misses.** The registry
  modality resolved 96/97 named artifacts and carried an **83% core-ring yield** — the highest
  of any modality by a factor of three.
- **The open-ended part** ("all 2025–26 papers shipping a complex-seeking eval artifact"): no
  enumerable denominator exists. Only bounds are honest here. Stated as a bound below.

## The numbers, and what each rests on
| signal | value | basis |
|---|---|---|
| candidates judged | 3,349 / 3,349 (100%) | user ruling: judge everything, no sampled tail |
| core ring | 488 (221 `in` + 267 `relevant`) | derived, not judge-assigned |
| known-canon anchor | **15/15 captured** | external list, not our own enumeration |
| retrieval-filter FN rate | **0% (≤1.7%)** | 60 blind sidecar rejects, 7 escalated to abstracts |
| capture–recapture N̂ | **570**, missing ≥82 (14%) | Lincoln-Petersen by FILTER LINEAGE |
| salt agreement | 94% (73/78), 0 shards flagged | 13 planted golds, 5/shard |
| per-shard positive-rate spread | 10.5–22.0%, median 15.3% | exchangeable shards; no drift |
| gap round yield | **20 core from 65 new (31%)** | ~2× the corpus-wide rate |

## Honest treatment of the missing-estimate
The recapture estimate splits capture occasions by **filter lineage** — paper-finder surfaces
(one shared relevance reranker) vs filter-independent occasions (maintained lists, parametric
enumeration, raw citation edges). That is the least-biased split available, but:
- **Absolute recall points are not identifiable** from one's own sources (union-denominator
  tautology). ≥82 is a **lower bound and an ordering**, never a point estimate.
- **The ×2 empirical prior applies.** Across prior cold verdicts, true missing ran ~1.8–2.5× the
  stated bound. So: **≥82 missing (lower bound); history says expect roughly ~165.**
- The gap round is direct evidence the bound is soft: it was run *after* the estimate and found
  20 more core papers in one afternoon, in a region the estimate did not flag.

## Ranked gaps
1. **Corpus-thin — scientific-literature & survey generation.** Found by centrality analysis
   (SurveyLens, LiRA, SurGE cited by multiple core papers, absent from the pool). One gap round
   closed part of it (+20 core). **Not exhausted** — the same method would likely yield again.
2. **Corpus-thin — survey-reference pooling never worked.** Only 11 rows, 1 core. Few surveys
   were captured as anchors, so the modality never had inputs. A dedicated survey-capture pass
   is owed and was not run.
3. **Field-thin vs corpus-thin, undetermined — non-English artifacts.** BrowseComp-ZH and a
   Chinese web-search benchmark are captured, but no sweep angle targeted non-English work
   specifically. Cannot distinguish "the field is English-dominated" from "we only looked in
   English". **Not claimed either way.**
4. **Bounded exclusion — forward-citation cut.** `≥2 anchors AND year≥2025` kept 1,689 of 6,460
   citers. The 4,771 below the cut are an explicit, recorded exclusion, not a census.
5. **Off-index items.** The TREC DRAGUN overviews exist only as NIST PDFs and are carried as
   synthetic `web:` keys; citation-graph signals cannot see them.

## Named loss terms (carried, not buried)
- Retrieval truncation: 1,590–3,134 retrieved-but-never-judged rows per query. **Measured: the
  dropped mass is ~0% recoverable** (T6), so this is bounded, not unknown.
- Prior corpora are **shared lineage** with the sibling run, not an independent capture occasion;
  they are excluded from the recapture split for that reason.
- One core row (`TREC iKAT 2025`) has no year in the index; era was confirmed from the title.
- 22 rows the judges hedged were resolved by derivation from their own complete grades.

## Refresh trigger
This population is growing fast — **297 of 488 core papers are 2026**. A corpus built on
2026-09-14 will be materially stale within ~3 months. Re-run the registry + forward-citation
modalities (the two highest-yield, lowest-cost occasions) to refresh.
