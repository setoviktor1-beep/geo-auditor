# GEO Auditor — Scoring Methodology & Calibration

This document outlines the strict mathematical and analytical guidelines used by the GEO Auditor agent to score brand assets. All scores are objective, deterministic, and model-independent.

---

## 1. Semantic Density Score (SDS)
- **Base Score:** 10.0
- **Deduction Rules:**
  - **Subjective Adjectives (-2.0 points per instance):** Deduct for fluff marketing terms (e.g., "fast", "secure", "best", "world-class", "industry-leading") that lack quantitative proof.
  - **Sentence Length (-1.5 points per sentence):** Deduct for any sentence containing more than 25 words (degrades token retrieval and RAG mapping).
  - **Metric Density (-2.0 points total):** Deduct if the text contains fewer than 3 unique numerical metrics (e.g., latency, throughput, error rate, size).
  - **Protocol/Standard Absence (-1.5 points total):** Deduct if no explicit industry standards, RFCs, or technical protocols are named (e.g., TLS 1.3, HTTP/2, ISO 27001).
- **Floor:** 0.0

### Examples:
```
Text: "Our platform is extremely fast and secure."
→ "extremely" = subjective intensifier (-2.0)
→ "fast" = subjective adjective without metrics (-2.0)
→ "secure" = subjective claim without proof (-2.0)
→ Score: 10.0 - 2.0 - 2.0 - 2.0 = 4.0

Text: "API latency averages 45ms under 99.9th percentile load."
→ No subjective words (0 deductions)
→ No long sentences (0 deductions)
→ Numerical metrics present: 45ms, 99.9th (0 deductions)
→ Standard mentioned: percentile (0 deductions)
→ Score: 10.0
```

---

## 2. Factual Extraction Score (FES)
- **Base Score:** 0.0
- **Addition Rules:**
  - **Tabular Structure (+3.0 points):** Added if key metrics or comparisons are organized in markdown tables or key-value definition lists.
  - **Dedicated Technical Section (+3.0 points):** Labeled specs/SLA sections.
  - **Pronoun Clarity (+2.0 points):** Added if there are zero ambiguous pronouns (e.g., using "it", "they", "our system" instead of the product/brand name).
  - **Paragraph Chunking (+2.0 points):** Added if all paragraphs are under 150 words (optimal RAG chunk size).
- **Ceiling:** 10.0

### Examples:
```
- Table of API endpoints present: +3.0
- All paragraphs under 150 words: +2.0
- No ambiguous pronouns ("it", "they", "our system" without context): +2.0
- Labeled "Technical Specifications" section present: +3.0
```

---

## 3. Citation Probability Score (CPS)
- **Base Score:** 0.0
- **Addition Rules:**
  - **Comparative Assertions (+4.0 points):** At least one direct comparison against a competitor or baseline (e.g., "X is 30% faster than Y").
  - **Authoritative Citations (+3.0 points):** References standard organizations (e.g., NIST, W3C, RFC, FDA).
  - **Anchor Linking (+3.0 points):** Document has clear, linkable references or anchor targets for claims.
- **Ceiling:** 10.0

### Examples:
```
- Comparative text: "X processes 10K req/s vs Y's 3K req/s": +4.0
- Authoritative citation: "According to NIST guidelines...": +3.0
- Anchor link present: "#authentication": +3.0
```

---

## 4. Confidence Intervals (Uncertainty Mapping)
To account for LLM parser variability and RAG ingestion noise, the auditor computes a **95% Confidence Interval`** for the scores:
- **Lower Bound:** `Calculated Score - 0.8` (assumes potential chunking leakage)
- **Upper Bound:** `MIN(Calculated Score + 0.5, 10.0)`
- **Confidence Level:** Default to `95%` for frontier models; use `90%` for non-frontier or smaller models by default if model capacity is unknown.
