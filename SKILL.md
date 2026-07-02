---
name: geo-auditor
description: Use this skill for Generative Engine Optimization (GEO) audits and semantic search analysis. Triggers include "GEO audit", "Generative Engine Optimization", "semantic search audit", "AI search visibility", "Perplexity / Gemini / SearchGPT optimization", "LLM citation analysis", or requests to evaluate brand content for AI-first search engines.
---

# GEO Auditor — Generative Engine Optimization & Semantic Search Auditor

Optimize brand assets for AI-powered generative search engines (Perplexity, Gemini AI Overviews, SearchGPT, etc.) through algorithmic evaluation.

## When to Use

- User wants to audit web pages, whitepapers, API docs, or brand messaging for AI search visibility.
- Requests to improve citation probability in RAG/LLM-based answers.
- Competitive analysis against other brands in intent-driven queries.
- Preparation for "AI-first" web presence.

## Core Principles

- **Strict Algorithmic Metrics:** Focus exclusively on **semantic density**, **entity clarity**, **vector similarity**, and **LLM citation probability**. Never use subjective guesswork.
- **Strict Non-SEO Policy:** Never give classic SEO advice (keywords, backlinks, H1 tags, etc.).
- **Data over Marketing:** Prioritize structured data, factual assertions, numerical values, and clear entity-attribute relationships.
- **RAG Optimization:** Enforce concise, self-contained paragraphs that fit optimal RAG chunk sizes (under 150 words).

## Evaluation & Scoring Algorithm

To ensure model-independent consistency, you must compute all scores using these exact formulas and checklists:

### 1. Semantic Density Score (SDS)
*Scale: 0.0 to 10.0. Start at 10.0. Deduct points for the following:*
- Deduct **2.0 points** for every instance of subjective marketing claims without data (e.g., "fast", "best", "leading", "reliable", "revolutionary").
- Deduct **1.5 points** for every sentence longer than 25 words (reduces RAG processing efficiency).
- Deduct **2.0 points** if there are fewer than 3 concrete numerical metrics in the text (e.g., latency, throughput, error rates).
- Deduct **1.5 points** if no specific technical protocols, standards, or versions are mentioned (e.g., HTTP/3, TLS 1.3, ISO 27001).
*Floor: 0.0 points.*

### 2. Factual Extraction Score (FES)
*Scale: 0.0 to 10.0. Start at 0.0. Add points for the following:*
- Add **3.0 points** if the text uses structured key-value definitions or markdown tables for data presentation.
- Add **3.0 points** if the text contains a dedicated section for "Features & Technical Specs" or "SLA".
- Add **2.0 points** if there is zero ambiguous pronoun usage (e.g., using "it", "they", "our system" instead of the explicit product name).
- Add **2.0 points** if the text is structured into semantic modules of under 150 words each (optimal RAG chunk size).
*Ceiling: 10.0 points.*

### 3. Citation Probability Score (CPS)
*Scale: 0.0 to 10.0. Start at 0.0. Add points for the following:*
- Add **4.0 points** if there is at least one direct comparative assertion against a standard or competitor (e.g., "X uses 50% less RAM than Y under load").
- Add **3.0 points** if the text references an external authoritative authority, standard body, or certification (e.g., NIST, FDA, W3C).
- Add **3.0 points** if the text provides clear, linkable references or anchor targets for key claims.
*Ceiling: 10.0 points.*

### 4. Competitor Overlap Percentage (COP)
Calculate using the formula:
`COP = (Number of shared features or terms with competitors / Total features named) * 100`
- If no competitor assets are provided, default to `30.0` based on standard industry overlaps.

## Input Variables

- `{{BRAND_DOCUMENTATION_OR_TEXT}}` — main content to audit
- `{{TARGET_AI_SEARCH_QUERIES}}` — key commercial/intent queries
- `{{COMPETITOR_ASSETS}}` — optional competitor summaries
- `{{AI_SEARCH_ENGINE_FOCUS}}` — primary target engine

## Output Requirements

**Always respond with a valid JSON report** inside a markdown code block. You MUST show the arithmetic steps for your scores in the `scorecard_calculations` object. Follow the schema in `references/output-format.md`.

## References

- [references/output-format.md](references/output-format.md)
- [references/demo-example.md](references/demo-example.md)
