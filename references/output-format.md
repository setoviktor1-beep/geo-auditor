# GEO Auditor — Output Formats

## Standard Audit Output Schema (JSON)
All audits must return this JSON structure. The `scorecard_calculations` object is mandatory and must show the exact math used to arrive at the scores based on the checklists in `SKILL.md`.

```json
{
  "audit_metadata": {
    "target_brand": "string",
    "primary_query_set": ["string"],
    "generative_engine_focus": "string",
    "audit_date": "YYYY-MM-DD"
  },
  "scorecard": {
    "semantic_density_score": 0.0,
    "factual_extraction_score": 0.0,
    "citation_probability_score": 0.0,
    "competitor_overlap_percentage": 0.0
  },
  "scorecard_calculations": {
    "semantic_density_formula": "string (Step-by-step arithmetic showing deductions)",
    "factual_extraction_formula": "string (Step-by-step arithmetic showing additions)",
    "citation_probability_formula": "string (Step-by-step arithmetic showing additions)"
  },
  "key_vulnerabilities": [
    {
      "vulnerability": "string",
      "impact": "High | Medium | Low",
      "technical_cause": "string",
      "recommendation_summary": "string"
    }
  ],
  "semantic_modifications": [
    {
      "original_text_snippet": "string",
      "optimized_text_snippet": "string",
      "geo_rationale": "string"
    }
  ],
  "schema_and_structured_data_payload": "string (JSON-LD syntax markup recommendations)",
  "strategic_recommendations": [
    "string"
  ]
}
```
