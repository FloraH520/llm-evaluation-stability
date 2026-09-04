# When Is a Model Actually Better?

*Evaluating the stability of LLM capability rankings across evaluation and inference conditions.*

## Research Question
When we say one language model is "better" than another, how stable is that conclusion across reasonable evaluation choices and inference conditions—and when is the observed advantage large enough to justify a real deployment decision?

## Why This Matters
Model capability is often summarized by a benchmark score or leaderboard rank. But measured performance can depend on how the evaluation is constructed and how capability is elicited at inference time. This project studies the gap between **observed benchmark performance** and a more robust conclusion about **what different models can actually do**.

The practical goal is model selection: understanding not only which model scores highest once, but whether its apparent advantage is stable, reproducible, and worth its cost and latency in deployment.

## Research Lineage
### 1. Replication anchor — evaluation sensitivity
**When Benchmarks are Targets: Revealing the Sensitivity of Large Language Model Leaderboards** — ACL 2024 Long Paper
- Paper: https://aclanthology.org/2024.acl-long.744/
- PDF: https://aclanthology.org/2024.acl-long.744.pdf
- Code: https://github.com/National-Center-for-AI-Saudi-Arabia/lm-evaluation-harness

This gives the project a peer-reviewed, reproducible starting point: test whether seemingly minor evaluation choices can materially change measured performance or model rankings.

### 2. Methodology update — reproducible evaluation
**OLMES: A Standard for Language Model Evaluations** — Findings of NAACL 2025
- Paper: https://aclanthology.org/2025.findings-naacl.282/
- Code: https://github.com/allenai/olmes

OLMES motivates treating prompt formatting, in-context examples, normalization, task formulation, and detailed experiment logging as part of the evaluation itself rather than incidental implementation details.

### 3. Frontier extension — inference conditions
**How Inference Compute Shapes Frontier LLM Evaluation** — 2026 preprint
- Paper: https://arxiv.org/abs/2606.17930

This motivates a later extension beyond static benchmark perturbations: test whether conclusions about model capability change with inference-time conditions such as compute budget, repeated attempts, context handling, or feedback.

### 4. Model-selection / deployment context
**The Capability Frontier: Benchmarks Miss 82% of Model Performance** — 2026 preprint
- Paper: https://arxiv.org/abs/2606.26836

This is related work rather than the replication foundation. It motivates thinking about model specialization, multiple generations, cost-aware selection, and whether a single model/run adequately represents achievable capability.

## Project Structure
**Phase 1 — Replication:** reproduce a scoped ACL 2024 evaluation-sensitivity result.

**Phase 2 — Modern-model extension:** test whether the phenomenon persists on newer models and whether sensitivity differs across models.

**Phase 3 — Capability elicitation extension:** if Phase 1–2 produce a defensible signal, study whether model rankings change under selected inference conditions motivated by newer work.

**Phase 4 — Deployment analysis:** combine performance, stability, latency, and API cost to ask when an apparent benchmark advantage actually supports choosing one model over another.

## Planned Outputs
- Reproducible evaluation pipeline
- Pilot and main experiment datasets
- Statistical and visual analysis of ranking stability
- Modern-model / inference-condition extension if justified by earlier results
- 4–6 page technical report
- Deployment-oriented model-selection analysis

## Repository Structure
```text
.
├── README.md
├── paper_notes.md
├── research_plan.md
├── src/
├── configs/
├── data/
├── results/
├── figures/
└── requirements.txt
```

## Status
**Day 1 / 12 — Literature review and replication scoping**

The ACL 2024 paper is the replication anchor, not the endpoint. Experimental choices will be frozen only after the anchor paper is understood and the replication scope passes the first research-design gate. Newer 2025–2026 work informs the extension; it does not substitute for a clean replication design.
