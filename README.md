# AI Evaluation Portfolio

A structured portfolio showcasing practical large language model (LLM) evaluation, rubric-based quality assessment, hallucination and factual-accuracy auditing, and data/logic verification.

## Core Focus Areas
- **LLM Response Quality Evaluation:** Multi-criteria scoring across accuracy, relevance, completeness, instruction following, and clarity.
- **Hallucination & Factual Accuracy Auditing:** Adversarial and constraint-driven testing across fabricated events/citations/statistics, false premises, obscure facts, uncertainty calibration, and arithmetic/count anomalies.
- **Data & Statistical Validation:** Checking numerical consistency, denominator assumptions, and ground-truth alignment in evaluation datasets.

## Repository Structure

| Folder | Status | Scope & Deliverables |
| :--- | :---: | :--- |
| `01-LLM-Response-Quality-Evaluation/` | Completed | Comparative benchmarking of ChatGPT and Claude across 20 questions in 10 categories using a 5-criterion rubric (`accuracy`, `relevance`, `completeness`, `instruction following`, `clarity`), structured datasets, and summary documentation. |
| `02-Hallucination-Factual-Accuracy/` | Completed | 10 adversarial/factual prompts (`H01`–`H10`) evaluated across ChatGPT and Claude (20 evaluation rows total), including `test-cases.csv`, `results.csv`, and `README.md`. |
| `03-Prompt-Evaluation/` | Completed | 8 prompt-engineering experiments (`P01`–`P08`) comparing `v1` baseline vs. `v2` engineered prompts on Claude (16 runs total; `3.13/5` to `5.00/5` mean score lift), including `test-cases.csv`, `results.csv`, and `README.md`. |
| `04-Automated-AI-Evaluation/` | Completed | Structured audit of an automated event-registration and routing workflow (`WF-01` to `WF-10`), including field-mapping checks, case/whitespace sensitivity tests, fallback verification, `test-cases.csv`, `results.csv`, and `README.md`. |

## Planned Roadmap
Spreadsheet & Data-Validation Auditing

## Methodology Highlights
- **Explicit Ground Truths & Rubrics:** Every test case pairs clear evaluation criteria or ground-truth checks with per-response notes rather than relying on vague impressions.
- **Separation of Hallucination vs. Uncertainty:** Distinguishes outright fabrication from appropriate hedging, premise pushback, or explicit statements of missing/ambiguous data.
- **Reproducible Tabular Artifacts:** Stores test cases and evaluation outputs in clean CSV files alongside project-level `README.md` summaries.
