# Project 03: Prompt Engineering Evaluation (`v1` Baseline vs. `v2` Engineered)

## Overview
This project evaluates how targeted prompt engineering improves **Claude**'s reliability across eight practical task types (`P01`–`P08`). Each experiment compares a minimal or underspecified baseline prompt (`v1`) against a structured, constraint-explicit prompt (`v2`), producing **16 total evaluation runs** logged in [`results.csv`](results.csv) against the test suite in [`test-cases.csv`](test-cases.csv).

## Headline Results

| Metric | `v1` Baseline (`n = 8`) | `v2` Engineered (`n = 8`) | Delta (`v1` → `v2`) |
|---|---|---|---|
| **Mean Quality Score (1–5)** | `3.13 / 5` | `5.00 / 5` | `+1.88` (`+60.0%`) |
| **Overall Pass Rate** | `62.5%` (`5/8`) | `100.0%` (`8/8`) | `+37.5 pp` (`+3` passes) |
| **Constraint Compliance Rate** | `37.5%` (`3/8`) | `100.0%` (`8/8`) | `+62.5 pp` (`+5` passes) |
| **Premature Guess / Hallucination Flag** | `12.5%` (`1/8`, `P04_v1`) | `0.0%` (`0/8`) | `-12.5 pp` (`-1` flag) |

## Experiment Summary (`P01`–`P08`)

| ID | Category | `v1` Score / Status | `v2` Score / Status | What Changed in `v2` |
|---|---|---|---|---|
| **P01** | Structured Output Enforcement | `2/5` (`Fail`) | `5/5` (`Pass`) | Enforced raw JSON output with no markdown code fences or prose wrapper. |
| **P02** | Ambiguity & Guardrails | `4/5` (`Pass`) | `5/5` (`Pass`) | Blocked premature destination assumptions and required structured clarifying questions plus explicit tailoring modes. |
| **P03** | Conciseness & Negative Constraints | `3/5` (`Pass`) | `5/5` (`Pass`) | Replaced vague length phrasing (`113` words) with an explicit `65`-word ceiling (`60` words achieved) and negative formatting rules. |
| **P04** | Multi-Step Reasoning Verification | `2/5` (`Fail`) | `5/5` (`Pass`) | Required intermediate arithmetic before stating the final answer, eliminating the `39` guess and landing cleanly on `58.5`. |
| **P05** | False-Premise Correction | `5/5` (`Pass`) | `5/5` (`Pass`) | Added explicit premise verification before answering; showed a ceiling effect since `v1` already rejected the false premise accurately. |
| **P06** | Grounded Extraction | `4/5` (`Pass`) | `5/5` (`Pass`) | Required separating confirmed updates from blockers and outputting `'Not stated in note.'` for unstated fields. |
| **P07** | Tone & Audience Calibration | `3/5` (`Pass`) | `5/5` (`Pass`) | Targeted a non-technical product manager with plain analogies and zero HTTP/code jargon, ending with a 1-sentence UX takeaway. |
| **P08** | Rule Precedence | `2/5` (`Fail`) | `5/5` (`Pass`) | Defined explicit rule priority (`< 45` total words overriding bullet count) and a concise trade-off note, cutting total length from `76` to `22` words. |

## Key Findings & Engineering Takeaways

1. **Vague length or format phrasing invites silent constraint drift:** In `P03_v1` ("short paragraph") and `P07_v1` (unbounded explanation), the model produced accurate content that missed practical operational constraints (`113` words and a `315`-word developer-heavy response). Numeric bounds, persona framing, and output rules moved constraint compliance from `37.5%` to `100%`.
2. **Answer-first generation creates avoidable arithmetic errors:** In `P04_v1`, answering before computing multi-step percentages led to an initial guess of `39` before self-correcting to `58.5`. Forcing step-by-step computation ahead of the final value eliminated the premature guess.
3. **Explicit rule priority prevents meta-commentary bloat:** In `P08_v1`, the model recognized that five 12-word bullets (`60+` words) conflicted with a `40`-word cap, yet spent `50` words on framing and follow-up offers to reach `76` words total. Declaring strict rule precedence kept `P08_v2` to `22` total words.
4. **Not every prompt category has the same headroom:** On `P05` (false-premise correction), `v1` already scored `5/5` without extra scaffolding. Engineering effort yields the highest marginal return on formatting, multi-step logic, audience calibration, and conflicting constraints.

## Repository Structure

```text
03-Prompt-Evaluation/
├── README.md
├── results.csv
└── test-cases.csv
