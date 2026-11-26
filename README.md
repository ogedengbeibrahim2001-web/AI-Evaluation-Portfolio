# AI-Evaluation-Portfolio
Benchmarking, hallucination testing, prompt engineering, and automated evaluation workflows for LLMs.
---

## Project 01: LLM Response Quality Evaluation (`Q01`–`Q20`)

### Executive Summary
This benchmark compares **ChatGPT** and **Claude** across a 20-prompt evaluation suite (`Q01`–`Q20`) spanning general knowledge, conceptual synthesis, arithmetic and logic, data interpretation, constraint adherence, ambiguity handling, false-premise correction, grounded summarization/extraction, and structured output generation (`JSON` and Markdown tables). Each response was scored on a **1–5 scale** across five rubric dimensions—**Accuracy**, **Relevance**, **Completeness**, **Instruction Following**, and **Clarity**—for a maximum of **25 points per prompt** (**500 points total**).

* **Claude** finished first overall at **491 / 500 (98.2%)**, leading by **+8 points** across the full benchmark.
* **ChatGPT** finished second at **483 / 500 (96.6%)**, holding the lead through the first ten prompts (`246` vs. `242`) before Claude pulled ahead in the second half.
* Across all 20 items, **Claude** won **7** prompts (`Q08`, `Q10`, `Q11`, `Q13`, `Q14`, `Q15`, `Q16`), **ChatGPT** won **2** prompts (`Q05`, `Q06`), and **11** prompts ended in ties (`Q01`–`Q04`, `Q07`, `Q09`, `Q12`, `Q17`–`Q20`).

---

### Final Scoreboard by Batch

| Batch | Prompts | Focus Area | ChatGPT | Claude | Batch Winner |
| :--- | :---: | :--- | :---: | :---: | :--- |
| **Batch 1** | `Q01`–`Q05` | General Knowledge, Synthesis & Math | `124 / 125` (`99.2%`) | `121 / 125` (`96.8%`) | **ChatGPT (+3)** |
| **Batch 2** | `Q06`–`Q10` | Math, Data Interpretation & Logic | `122 / 125` (`97.6%`) | `121 / 125` (`96.8%`) | **ChatGPT (+1)** |
| **Batch 3** | `Q11`–`Q15` | Constraints, Ambiguity & False Premise | `113 / 125` (`90.4%`) | `124 / 125` (`99.2%`) | **Claude (+11)** |
| **Batch 4** | `Q16`–`Q20` | False Premise, Grounding & Structured Output | `124 / 125` (`99.2%`) | `125 / 125` (`100.0%`) | **Claude (+1)** |
| **Overall** | **`Q01`–`Q20`** | **Full 20-Prompt Evaluation** | **`483 / 500` (`96.6%`)** | **`491 / 500` (`98.2%`)** | **Claude (+8 pts)** |

---

### Key Findings & Failure Modes

* **Early-Commitment Arithmetic vs. Step-by-Step Verification (`Q05`–`Q06`):** ChatGPT earned `25/25` on both math prompts by working through intermediate calculations methodically, whereas Claude scored `22/25` on each after committing prematurely to an initial value before completing the full calculation.
* **Strict Constraint Adherence (`Q11`–`Q12`):** Claude handled tight multi-constraint formatting cleanly on `Q11` (`25/25`), whereas ChatGPT dropped to `17/25` by exceeding the 5-word description cap and over-applying the negative letter constraint into description text. On `Q12`, ChatGPT preserved the exact closing string (`End of brief.`) while Claude omitted the final period (`24/25` each).
* **Nuance, Ambiguity & False-Premise Correction (`Q08`, `Q10`, `Q13`–`Q16`):** Claude consistently earned `25/25` across these items by surfacing missing context, adding practical caveats and methodological detail, and correcting false premises clearly while maintaining accuracy.
* **Grounded Tasks & Structured Outputs (`Q17`–`Q20`):** Both models achieved `25/25` across grounded summarization/extraction (`Q17`–`Q18`) and schema/table formatting (`Q19`–`Q20`), demonstrating strong reliability when output rules are explicit and self-contained.

---

### Repository Artifacts
* **Results Dataset:** `01-LLM-Response-Quality-Evaluation/data/evaluation-results.csv`
* **Prompt Dataset:** `01-LLM-Response-Quality-Evaluation/data/evaluation-dataset.csv`
* **Scoring Rubric:** `01-LLM-Response-Quality-Evaluation/evaluation-rubric.md`
