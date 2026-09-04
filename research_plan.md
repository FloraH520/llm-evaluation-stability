# Research Plan

> **Status:** Draft skeleton. Do not freeze experimental choices until the anchor paper review is complete.

## Working Title
**Are LLM Rankings Stable? A Replication and Modern-Model Study of Evaluation Sensitivity**

## Research Question
How stable are LLM capability rankings under controlled changes to evaluation setup?

## Motivation
Benchmark rankings influence research claims and real-world model selection. If small, defensible evaluation choices materially change measured performance or rankings, a single leaderboard score may overstate certainty about which model is actually better for a task.

## Phase 1 — Replication
Reproduce a scoped phenomenon from *When Benchmarks are Targets* (ACL 2024).

### Hypotheses
These are provisional and must be refined after Day 1 reading.

- **H1:** Controlled evaluation changes will produce measurable answer instability.
- **H2:** Sensitivity will differ across models.
- **H3:** Some between-model performance differences may be comparable to evaluation-induced variation.

## Experimental Matrix
| Variable | Status | Final choice |
|---|---|---|
| Questions | Frozen within comparison | TBD |
| Benchmark(s) | To select | TBD |
| Model | Manipulated | TBD |
| Evaluation condition | Manipulated | TBD |
| Prompt template | Controlled | TBD |
| Temperature / sampling | Controlled | TBD |
| Scoring method | Controlled or explicitly manipulated | TBD |
| Random seed | Recorded where supported | TBD |
| API/model version | Recorded | TBD |

## Core Metrics
Final definitions TBD after paper review.

Candidate metrics:
- Accuracy
- Answer flip rate
- Performance change by condition
- Rank change / ranking variance
- Confidence intervals / uncertainty
- Latency
- Token usage
- Estimated API cost

## Phase 0 — Tiny Pilot
**Budget ceiling: $20.**

Goal: validate the pipeline, task difficulty, scoring, and whether there is enough signal to justify scaling.

Provisional scope:
- 2 models
- 30–50 questions
- At least 2 controlled evaluation conditions

### Go / No-Go Gate
Scale only if:
1. the pipeline is reproducible;
2. scoring is trustworthy;
3. questions have useful difficulty / discrimination;
4. observed results justify a larger experiment or reveal a clear design problem worth fixing.

## Phase 1 — Main Replication
Target scope after pilot:
- ~4 models
- ~100–200 questions
- controlled evaluation conditions

Exact scope will be set from pilot evidence, not ambition.

## Phase 2 — Modern Extension
Candidate question:

> Do apparent model rankings or specializations remain stable on newer models under different valid evaluation conditions?

This phase is optional until the replication produces a defensible result.

## Phase 3 — Deployment Analysis
If supported by the data, compare:
- capability/performance
- evaluation stability
- API cost
- latency

Question:

> Is an apparent leaderboard advantage large and stable enough to justify choosing a more expensive model in a real product?

## Research Integrity Rules
1. Preserve raw outputs and experiment configurations.
2. Record model/API versions and run dates.
3. Separate preregistered hypotheses from post-hoc observations.
4. Report null or failed replications rather than forcing a positive result.
5. Do not expand scope before passing the relevant gate.
6. Every public claim must point to an experiment that supports it.

## Deliverables
- `paper_notes.md`
- frozen `research_plan.md`
- reproducible evaluation pipeline
- raw and processed results
- 4–6 publication-quality figures
- 4–6 page technical report
- public-facing README
- LinkedIn summary
- resume bullets
- concise Randy referral package
