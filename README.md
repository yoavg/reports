# reports

Research reports and their underlying data.

**Read them in the browser: <https://yoavg.github.io/reports/>**

## complex-info-seeking (2026-09-14)

A corpus survey of benchmarks, datasets, task suites and environments published in **2025–2026**
whose tasks **cannot be answered by a single search** and require decomposition into multiple
steps. **481 artifacts**, drawn from 3,349 relevance-judged candidates, each read for four
properties of the search — whether later steps depend on earlier ones, whether the decomposition
is knowable up front, whether several answers can be right, and whether an agent can tell when it
has found everything — plus what it must actually do and what it is allowed to search with.

The decisive test is **decomposition, not difficulty**: a task answerable by one well-formed query
is out, and breadth tasks (enumerate N entities meeting a criterion) are in. This deliberately
re-admits ~130 artifacts that the sibling `long-horizon-agent-benchmarks` corpus excluded for being
single-goal — one research question decomposed into sub-queries is exactly the target here.

| file | what it is |
|---|---|
| [`complex-info-seeking/index.html`](complex-info-seeking/index.html) | **The report** — five questions answered, evidence quoted in the prose, coverage boundary |
| [`complex-info-seeking/catalog.html`](complex-info-seeking/catalog.html) | **The catalogue** — all 481 rows, sortable and filterable by tool, access, kind, modality and tier |
| `complex-info-seeking/data/catalog.csv` | all 481 rows with task summaries, tool sets, citation counts and links — open in a spreadsheet |
| `complex-info-seeking/data/catalog.json` | the same rows with every verbatim evidence span |
| `complex-info-seeking/data/catalog-aggregates.json` | every number the report quotes, script-computed |
| `complex-info-seeking/data/charts.json` | every chart series exactly as rendered |
| `complex-info-seeking/data/synthesis.json` | for each of the 9 pooled claims: because / unless / basis note |
| `complex-info-seeking/data/tools.json` | the search-tool and access tallies |
| `complex-info-seeking/data/flags.json` | the four property distributions, split by tier and evidence depth |
| `complex-info-seeking/data/coverage-verdict.md` | what the corpus does not cover, with every estimator used or gated |
| `complex-info-seeking/data/retrieval-filter-probe.md` | the measured false-negative rate of the retrieval filter (0%, ≤1.7%) |
| `complex-info-seeking/data/judge-calibration.md` | salt-item agreement across the judging fleet (94%) |

### What it found

- **Half the corpus still resolves to a single right answer.** 241 of 481 artifacts are
  `single-verifiable` — the decomposition is in the *search*, not the answer. Only 46 admit
  several defensible answers and 78 are open-ended.
- **For 144 artifacts an agent has no reliable stopping signal** (`coverage_determinability: hard`),
  against 123 where completeness is knowable. This is the property the field handles worst.
- **Decomposition is usually discovered, not planned.** 152 artifacts are `partially-emergent` and
  94 `fully-emergent`, against 115 whose sub-questions can be enumerated before searching.
- **89% state what the agent may search with** (428 of 481): web search APIs (216), retrieval over
  a shipped corpus (175), browsers (122), code execution (96). Access splits open-web 137 /
  fixed-corpus 125 / mixed 124.
- **The two most interesting properties are the least directly evidenced.** Decomposition and
  coverage carry 28% and 26% stretch-fit rows; their warrants in `synthesis.json` name the
  confounds, including that "known upfront" is sometimes answered about the benchmark's *designer*
  rather than the solving agent.
- **20 further difficulty properties** were open-coded from the papers themselves, each labelled
  by whether the extraction prompt named it or it emerged unprompted.

### Caveats

- **Full-text depth is uneven for the four property columns.** Only the 211 dedicated benchmarks
  were re-read at body depth for those; the 270 task sets shipped alongside a method carry
  abstract-only evidence there. The report reports the two tiers separately rather than pooling.
- **The tools column is a lower bound.** It often records what a paper's own reference agent was
  built with, not what the benchmark formally permits — the two come apart for the 137 open-web
  artifacts. 53 artifacts state nothing, recorded as "not stated" rather than guessed.
- **Between 18% and 26% of each property is `not-determinable`** — recorded where a paper does not
  say, never inferred. One artifact has neither an abstract nor retrievable full text and is
  marked unreadable, which is kept distinct from "not stated".
- **Citation counts move.** They were read on 2026-09-14 and that date ships with the column.
- **Era is strictly 2025–2026.** Pre-2025 antecedents (HotpotQA, MuSiQue, FanOutQA, BrowseComp
  lineage) are context, not members. Non-English coverage is undetermined: no sweep targeted it.

## long-horizon-agent-benchmarks (2026-09-14)

A corpus survey of benchmarks, datasets, environments and scenario suites published in
**2025–2026** whose settings require an LLM agent to pursue and track **multiple goals and
subgoals**. **480 artifacts**, drawn from 4,327 screened candidates with 2,191 relevance-judged
and every surviving artifact extracted under two lenses (goal structure, time horizon).

Deliberately scoped: software engineering and every other code-centric task domain is excluded,
as are pre-2025 artifacts. The decisive test is **goal multiplicity, not duration** — a benchmark
whose task is one goal grounded in a long history is out; a setting that generates or demands many
goals is in. This is the complement of `agent-memory-benchmarks` below, which covers the
memory-and-recall side that this corpus rules out.

| file | what it is |
|---|---|
| [`long-horizon-agent-benchmarks/index.html`](long-horizon-agent-benchmarks/index.html) | **The report** — three questions answered, evidence quoted in the prose, coverage boundary |
| [`long-horizon-agent-benchmarks/catalog.html`](long-horizon-agent-benchmarks/catalog.html) | **The catalogue** — all 480 rows as a sortable, filterable table grouped by domain |
| `long-horizon-agent-benchmarks/data/catalog.csv` | all 480 rows with evidence spans, citation counts and links — open in a spreadsheet |
| `long-horizon-agent-benchmarks/data/catalog.json` | the same rows with full verbatim spans |
| `long-horizon-agent-benchmarks/data/catalog-aggregates.json` | every number quoted in the report, script-computed |
| `long-horizon-agent-benchmarks/data/charts.json` | every chart series exactly as rendered |
| `long-horizon-agent-benchmarks/data/synthesis.json` | for each pooled claim: because / unless / basis note |
| `long-horizon-agent-benchmarks/data/coverage-verdict.md` | what the corpus does not cover, with every estimator used or gated |
| `long-horizon-agent-benchmarks/data/retrieval-filter-probe.md` | the measured false-negative rate of the retrieval filter |
| `long-horizon-agent-benchmarks/data/extractor-agreement.json` | consistency probes repeated across every extractor |
| `long-horizon-agent-benchmarks/data/scope-caveats.json` | artifacts kept but carrying a noted scope caveat |

Both HTML files are self-contained — clone and open them directly, no server needed. They are
also served as web pages: [the report](https://yoavg.github.io/reports/long-horizon-agent-benchmarks/index.html)
· [the catalogue](https://yoavg.github.io/reports/long-horizon-agent-benchmarks/catalog.html).

### What it found

- **334 of 480 (70%) never quantify a time horizon at all** — no step count, no turn count, no
  wall-clock figure, no simulated duration. Many describe their tasks as "long-horizon" in prose
  while reporting only task counts, model counts and success rates.
- The **146 that do quantify share no unit**: turns, agent-steps, actions, simulated-days,
  episodes, sessions, tool-calls, wall-clock hours and minutes, human-expert-hours, simulated-years
  and tokens-per-run — **13 incommensurable unit families**. Cross-benchmark horizon comparison is
  not currently possible.
- **297 of 480 (62%) hand the agent all of its goals up front.** Only **15 (3%)** have the agent
  generate its own goals; 70 (15%) have the environment emit goals over time. Self-directed goal
  generation is close to absent from the evaluation literature.
- **291 of 480 (61%) award subgoal-, checkpoint- or milestone-level partial credit**; 152 score
  final outcomes only. Partial-credit scoring is what makes *where* an agent broke down visible
  at all.
- Goal structure is dominated by **sequential chains (160)** and **DAGs with precedence (125)**;
  hierarchical decomposition accounts for 80 and open-ended goal generation for 31.
- The corpus spans **14 domain families**, led by business/office/enterprise
  (105), personal assistants & memory (65) and embodied & robotics
  (46). Every family assignment comes from the domain the extractor recorded after
  reading the paper; **153 artifacts span two families** and carry a recorded secondary.
- **Information seeking & deep research is its own family (10 artifacts, 7 more cross-listed)** —
  small on purpose. 130 information-seeking artifacts were judged out because a single research
  question decomposed into subqueries is *one* goal under this corpus's multi-goal test; the
  survivors are those where information seeking sits inside a longer multi-goal task.
- Each row carries a **citation count**. With 318 of 480 entries from 2026
  and 126 at zero (median 3, max 456),
  that column measures age far more than quality — it is shipped for sorting, not for ranking.
- **2026 outnumbers 2025 by 318 to 162.** The field is reorganising around long-horizon
  evaluation in real time, and a whole genre of explicitly long-horizon artifacts now exists that
  did not in 2024.

### Honest caveats

- **Not exhaustive: at least ~131 further in-scope artifacts are estimated missing**
  (capture-recapture lower bound, calibrated pairing only). Applying this methodology's measured
  ~2× history and the 62% single-modality share, the honest range is **~130–320 missing, i.e.
  roughly 60–80% of the reachable population captured**.
- **The headline horizon finding is a claim about what papers foreground.** 276 of the 334
  "no horizon" determinations were made from the abstract; only 56 were confirmed against full
  text. The full-paper rate is unmeasured for the rest.
- **The 2026 half is the least externally validated** — only 1 of 85 independently enumerated
  canonical benchmarks was from 2026, so that stratum rests on retrieval and forward citations
  alone.
- **The depth leg of the sweep never ran**: the search backend refused all 13 diligent
  escalations, leaving 4,186 un-probed discards on those angles. A 20-angle axis-switched sweep
  was substituted and found 581 new candidates, but that is breadth, not depth.
- **The lower-priority tail was sampled, not enumerated**, under a numeric threshold fixed in
  writing before any result was seen; no decile crossed it, leaving an estimated ~135 relevant
  papers unjudged.
- The subgoal-credit split depends on a keyword classifier over the extracted scoring field;
  87 rows sit in a labelled unclassified tail and count on neither side.
- Family counts were corrected on 2026-09-14: an earlier ordered-keyword rollup let a title word
  override the extractor's own domain call (a Slay the Spire testbed was filed under memory because
  its title said "Bounded-Memory"). That version over-counted business by 31, assistants by 29 and
  multi-agent by 25, under-counted tool-use and OS/computer-use by 16 each, and hid the
  open-ended-sandbox family entirely. The three headline findings above are unaffected — they never
  depended on family.
- The information-seeking family was re-derived from each paper's extracted goals rather than
  from its recorded domain, because the extraction packet's domain vocabulary never offered that
  option — a gap in the packet. Those 10 rows are marked `evidence-rederived` in `family_source`;
  the other 470 come straight from the extractor's own domain call.
- Counts are per-artifact and single-extractor. Three probe papers placed in every extraction
  batch were identified identically by all eight extractors but drifted on structure vocabulary.

## agent-memory-benchmarks (2026-09-12)

A corpus survey of long-term-memory and long-horizon benchmarks for LLM agents.
**973 distinct benchmark artifacts** from 995 in-charter rows, drawn from 3,314 screened
candidates — every candidate relevance-judged, every in-charter row extracted from the paper.

| file | what it is |
|---|---|
| [`agent-memory-benchmarks/index.html`](agent-memory-benchmarks/index.html) | **The report** — findings, evidence in the prose, coverage boundary |
| [`agent-memory-benchmarks/catalog.html`](agent-memory-benchmarks/catalog.html) | **The catalogue** — all 995 rows, newest first, filterable, with a verified external-memory column |
| `agent-memory-benchmarks/data/catalog.csv` | all 995 rows with evidence spans and links — open in a spreadsheet |
| `agent-memory-benchmarks/data/catalog-aggregates.json` | every number quoted in the report, script-computed |
| `agent-memory-benchmarks/data/synthesis.json` | for each pooled claim: because / unless / basis note |
| `agent-memory-benchmarks/data/coverage-verdict.md` | what the corpus does not cover |

Both HTML files are self-contained — clone and open them directly, no server needed. They are
also served as web pages: [the report](https://yoavg.github.io/reports/agent-memory-benchmarks/index.html)
· [the catalogue](https://yoavg.github.io/reports/agent-memory-benchmarks/catalog.html).
(GitHub's own file view shows the source rather than rendering it — use those links.)

### What it found

- **619 of 995 (62.2%)** never define the long-horizon / long-term construct they test. Only
  **109 (11.0%)** state a definition outright; the rest define it obliquely, by threshold or
  by contrast.
- Reading full text recovers **example lengths** (4.4% → 78.1%) but barely recovers
  **definitions** (10.2% → 42.2%) — the definitions are absent, not buried.
- Stated example lengths span **1.2 to 120,000 discrete units** and **0.004 to 188,340 hours
  (21.5 years)** across 8 incommensurable unit families, none holding more than 21% of mentions.
- **304 of 995 (31%)** ship alongside a memory *method* rather than as benchmark-first
  contributions; 24 ship no artifact at all.

### External memory

The catalogue records whether each benchmark involves a store **outside the model's context
window** (files, a database, a vector store, a scratchpad) and whose it is — the agent's own
memory, the task environment's state, or a fixed corpus it retrieves from. A long context window
does not count, and neither does a mechanism belonging to a method the authors also propose when
the benchmark itself is method-agnostic.

**558 present / 437 absent**, of the present ones 384 agent-memory, 100 environment-state,
74 retrieval-corpus. 497 rows carry a verbatim quote from the source; every quote is
machine-checked as a contiguous run of the text it is attributed to.

Every row was read twice: a cheap first pass, then a stronger pass that re-read all of them.
Measured per reading against 10 hand-read gold items, the first pass agreed on only **72%** of
present/absent calls and **60%** of the whose split — and the second pass overturned **318 of 985
(32%)** of what it checked, in both directions. Its three recurring mistakes are worth knowing,
because they are the ones a keyword search would also make: quoting a real sentence that proves
nothing (a related-work citation, a results-table fragment, once a cleaning *rag*); crediting the
benchmark with a **co-proposed method's** memory; and calling a long context window an external
store. It also missed real stores described only in a methods section.

One of the gold items was itself wrong, and the run's own salts caught it: SWE-bench was
hand-filed `retrieval-corpus`, and 8 of 9 independent verifiers re-filed it `environment-state`
— the agent writes to the codebase, and grading reads the resulting repository state.

### Honest caveats

- **~80% estimated recall, and that is the optimistic read** (capture-recapture gives a lower
  bound). Roughly 250–290 in-charter artifacts are uncaptured, concentrated in temporal-reasoning
  and lifelong/embodied families.
- **Every paper-finder retrieval modality is missing** — auth-blocked throughout acquisition.
- **13.8% of rows were read at abstract depth only** and carry visibly thinner evidence; the two
  strata are reported separately and never pooled.
- Relevance judging leans one tier high on the charter boundary; the `in` count is an upper read.
- The 62% "no definition" figure depends on the extractors' bar for what counts as a definition.
