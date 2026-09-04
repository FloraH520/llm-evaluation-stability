# Are LLM Rankings Stable?

*A replication and modern-model study of evaluation sensitivity.*

## Research Question
How stable are LLM capability rankings under seemingly minor evaluation choices, and when are benchmark differences large enough to justify choosing one model over another in real-world deployment?

## Why This Matters
Benchmark scores are often treated as stable evidence of model capability. Prior work suggests that small evaluation choices can change measured performance and even alter model rankings. This project starts by reproducing that phenomenon, then extends the analysis to newer models and practical model-selection tradeoffs such as cost, latency, and stability.

## Current Plan
1. Reproduce a peer-reviewed result from **When Benchmarks are Targets: Revealing the Sensitivity of Large Language Model Leaderboards** (ACL 2024).
2. Run a controlled modern-model extension.
3. Analyze whether apparent model rankings and specializations remain stable across evaluation conditions.
4. Translate the findings into deployment guidance for model selection.

## Anchor Paper
- ACL Anthology: https://aclanthology.org/2024.acl-long.744/
- PDF: https://aclanthology.org/2024.acl-long.744.pdf
- Official code: https://github.com/National-Center-for-AI-Saudi-Arabia/lm-evaluation-harness

## Planned Outputs
- Reproducible evaluation pipeline
- Pilot and main experiment datasets
- Statistical and visual analysis of ranking stability
- 4–6 page technical report
- Deployment-oriented cost/performance analysis

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

The experimental design, models, benchmarks, perturbations, and metrics will be frozen only after the anchor paper has been fully reviewed and the replication scope passes the first research-design gate.
