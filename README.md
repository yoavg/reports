# reports

Research reports and their underlying data.

**Read them in the browser: <https://yoavg.github.io/reports/>**

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
