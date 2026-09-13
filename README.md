# reports

Research reports and their underlying data.

## agent-memory-benchmarks (2026-09-12)

A corpus survey of long-term-memory and long-horizon benchmarks for LLM agents.
**973 distinct benchmark artifacts** from 995 in-charter rows, drawn from 3,314 screened
candidates — every candidate relevance-judged, every in-charter row extracted from the paper.

| file | what it is |
|---|---|
| [`agent-memory-benchmarks/index.html`](agent-memory-benchmarks/index.html) | **The report** — findings, evidence in the prose, coverage boundary |
| [`agent-memory-benchmarks/catalog.html`](agent-memory-benchmarks/catalog.html) | **The catalogue** — all 995 rows, newest first, filterable |
| `agent-memory-benchmarks/data/catalog.csv` | all 995 rows with evidence spans and links — open in a spreadsheet |
| `agent-memory-benchmarks/data/catalog-aggregates.json` | every number quoted in the report, script-computed |
| `agent-memory-benchmarks/data/synthesis.json` | for each pooled claim: because / unless / basis note |
| `agent-memory-benchmarks/data/coverage-verdict.md` | what the corpus does not cover |

Both HTML files are self-contained — clone and open them directly, no server needed.
(GitHub will not render them inline; use a raw-HTML viewer or open the local file.)

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

### Honest caveats

- **~80% estimated recall, and that is the optimistic read** (capture-recapture gives a lower
  bound). Roughly 250–290 in-charter artifacts are uncaptured, concentrated in temporal-reasoning
  and lifelong/embodied families.
- **Every paper-finder retrieval modality is missing** — auth-blocked throughout acquisition.
- **13.8% of rows were read at abstract depth only** and carry visibly thinner evidence; the two
  strata are reported separately and never pooled.
- Relevance judging leans one tier high on the charter boundary; the `in` count is an upper read.
- The 62% "no definition" figure depends on the extractors' bar for what counts as a definition.
