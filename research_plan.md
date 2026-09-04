# Research Plan

> **Status:** Draft skeleton. Freeze experimental choices only after the replication anchor has been fully reviewed.

## Working Title
**When Is a Model Actually Better? Evaluating the Stability of LLM Capability Rankings Across Evaluation and Inference Conditions**

## Core Research Question
When we conclude that one LLM is better than another, how stable is that conclusion across reasonable evaluation choices and inference conditions?

A second, deployment-oriented question follows:

> When is a measured model advantage large, stable, and useful enough to justify choosing that model in practice?

## Research Lineage
This project intentionally combines a stable replication anchor with newer work rather than treating the newest preprint as the foundation.

### Replication anchor — ACL 2024
**When Benchmarks are Targets: Revealing the Sensitivity of Large Language Model Leaderboards**  
https://aclanthology.org/2024.acl-long.744/

Role: establish a reproducible baseline for evaluation sensitivity.

### Evaluation methodology — NAACL 2025
**OLMES: A Standard for Language Model Evaluations**  
https://aclanthology.org/2025.findings-naacl.282/  
https://github.com/allenai/olmes

Role: inform reproducibility standards, experiment logging, and careful treatment of evaluation configuration.

### Modern inference extension — 2026
**How Inference Compute Shapes Frontier LLM Evaluation**  
https://arxiv.org/abs/2606.17930

Role: motivate later experiments asking whether apparent capability and model rankings depend on inference-time elicitation conditions.

### Model-selection context — 2026
**The Capability Frontier: Benchmarks Miss 82% of Model Performance**  
https://arxiv.org/abs/2606.26836

Role: related work for specialization, repeated generations, cost-performance, and deployment/model-selection questions. It is not treated as the peer-reviewed replication anchor.

## Conceptual Model
The project separates three ideas that are often conflated:

1. **Underlying model capability** — what the model can potentially do.
2. **Elicited capability** — what a particular prompting/inference setup manages to extract.
3. **Measured performance** — what a benchmark and scoring protocol record.

The experiments ask how confidently we can infer (1) from (3), given variation in (2) and evaluation design.

## Phase 0 — Tiny Pilot
**Budget ceiling: $20.**

Goal: validate the pipeline, task difficulty, scoring, and whether the selected perturbation produces an interpretable signal.

Provisional scope:
- 2 models
- 30–50 questions
- at least 2 controlled evaluation conditions

### Go / No-Go Gate
Scale only if:
1. the pipeline is reproducible;
2. scoring is trustworthy;
3. questions have useful difficulty/discrimination;
4. model/API versions and configurations are fully logged;
5. the pilot either reveals a meaningful signal or identifies a concrete design problem that can be corrected.

## Phase 1 — ACL 2024 Replication
Reproduce one carefully scoped evaluation-sensitivity phenomenon from *When Benchmarks are Targets*.

### Provisional Hypotheses
These must be refined after Day 1 reading.

- **H1:** Controlled evaluation changes can produce measurable answer instability.
- **H2:** Sensitivity differs across models.
- **H3:** Evaluation-induced variation can sometimes be large enough to affect comparative conclusions or rankings.

### Experimental Matrix
| Variable | Status | Final choice |
|---|---|---|
| Questions | Frozen within comparison | TBD |
| Benchmark(s) | To select | TBD |
| Model | Manipulated | TBD |
| Evaluation condition | Manipulated | TBD |
| Prompt template | Controlled unless explicitly studied | TBD |
| Temperature / sampling | Controlled | TBD |
| Scoring method | Controlled or explicitly manipulated | TBD |
| Random seed | Recorded where supported | TBD |
| API/model version | Recorded | TBD |
| Run date | Recorded | TBD |

### Candidate Metrics
- Accuracy
- Answer flip rate
- Performance change by condition
- Rank change / ranking variance
- Confidence intervals / uncertainty

## Phase 2 — Modern-Model Extension
Ask whether the replicated phenomenon persists on newer models and whether sensitivity differs by model.

Candidate question:

> Do modern models that appear close on a benchmark remain ordered the same way under multiple defensible evaluation configurations?

This phase should add a research question, not merely newer model names.

## Phase 3 — Capability Elicitation / Inference Extension
Only proceed if Phase 1–2 establish a defensible baseline.

Motivated by 2026 inference-evaluation work, select a small number of inference conditions—for example inference budget or repeated attempts—and ask:

> Does changing how capability is elicited change the conclusion about which model is best for the task?

Do not attempt to reproduce the entire 2026 paper. Scope this as a focused extension of the central stability question.

## Phase 4 — Deployment Analysis
If supported by the data, combine:
- measured capability/performance
- evaluation/inference stability
- API cost
- latency

Deployment question:

> Is the apparent advantage of a model sufficiently large and stable to justify its deployment cost?

A possible later descriptive quantity is **selection stability**: across defensible evaluation configurations, how often would the same model actually be selected? Do not introduce this as a formal new metric unless the data and literature justify it.

## Research Integrity Rules
1. Preserve raw outputs and experiment configurations.
2. Record exact model/API versions and run dates.
3. Separate preregistered hypotheses from post-hoc observations.
4. Report null or failed replications rather than forcing a positive result.
5. Do not expand scope before passing the relevant gate.
6. Every public claim must map to an experiment that supports it.
7. Distinguish peer-reviewed foundations from recent preprints.
8. Do not interpret a benchmark score as intrinsic model capability without discussing evaluation and elicitation conditions.

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
