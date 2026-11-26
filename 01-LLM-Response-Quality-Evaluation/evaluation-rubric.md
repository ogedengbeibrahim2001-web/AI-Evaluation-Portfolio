# LLM Response Quality Evaluation Rubric

Each model response is scored across **5 dimensions** on a **1–5 scale** (Maximum Score: **25 points** per prompt; **500 points** across all 20 prompts).

## Scoring Criteria

### 1. Accuracy (1–5)
* **5:** Completely factually accurate, mathematically sound, and free of hallucinations or unsupported claims.
* **4:** Mostly accurate with minor omissions or imprecise phrasing that does not alter the core answer.
* **3:** Partially accurate; contains noticeable factual, logical, or computational errors alongside valid points.
* **2:** Largely inaccurate or misleading; misinterprets core facts or accepts a false premise as true.
* **1:** Completely incorrect, fabricated, or nonsensical.

### 2. Relevance (1–5)
* **5:** Directly addresses the exact prompt intent with zero off-topic filler.
* **4:** Addresses the prompt well with minimal tangential context.
* **3:** Partially addresses the prompt but drifts into unnecessary background or misses secondary intent.
* **2:** Mostly tangential; fails to answer the core question directly.
* **1:** Completely off-topic.

### 3. Completeness (1–5)
* **5:** Thoroughly covers all parts of the prompt, edge cases, and necessary caveats.
* **4:** Covers all main points well, missing only minor secondary nuance.
* **3:** Covers the primary question superficially; omits important steps, conditions, or sub-questions.
* **2:** Incomplete response that leaves major parts of the prompt unanswered.
* **1:** Fails to provide a substantive answer.

### 4. Instruction Following (1–5)
* **5:** Strictly obeys all explicit constraints (word/sentence counts, output format, tone, negative constraints, and uncertainty handling).
* **4:** Follows almost all instructions with one minor formatting or length deviation.
* **3:** Follows the general task but violates at least one explicit constraint (e.g., wrong format or exceeded word limit).
* **2:** Ignores multiple explicit constraints.
* **1:** Completely disregards formatting and operational instructions.

### 5. Clarity (1–5)
* **5:** Exceptionally clear, well-structured, concise, and easy to verify.
* **4:** Clear and readable with minor structural or phrasing friction.
* **3:** Understandable but wordy, disorganized, or ambiguous in parts.
* **2:** Difficult to follow due to poor organization or convoluted phrasing.
* **1:** Incoherent or unreadable.
