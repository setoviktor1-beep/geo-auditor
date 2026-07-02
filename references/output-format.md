# GEO Auditor — Output Formats

## Standard Audit Output Schema (JSON)
All audits must return this JSON structure. The `thought_process` object is mandatory and must show the exact step-by-step reasoning before outputting the results.

```json
{
  "thought_process": {
    "step_1_input_analysis": "string (Identify entities, technical terms, claims, missing schema)",
    "step_2_calculations": "string (Step-by-step arithmetic showing SDS, FES, CPS, COP calculation)",
    "step_3_optimization": "string (Step-by-step plan for optimizing text and metadata)",
    "step_4_validation": "string (Verify JSON outputs against output-format.md key-by-key)"
  },
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
