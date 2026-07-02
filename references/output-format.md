# GEO Auditor — Output Formats

Jei modelis negali sugeneruoti validaus JSON, grąžinkite tik markdown code block su JSON struktūra. Jokio teksto už JSON bloko ribų.

## Standard Audit Output Schema (JSON)
All audits must return this JSON structure. The `thought_process` object is mandatory and must show the exact step-by-step reasoning before outputting the results.

```json
{
  "thought_process": {
    "step_1_input_analysis": "string (Identify entities, technical terms, claims, missing schema)",
    "step_2_calculations": "string (Step-by-step arithmetic showing SDS, FES, CPS, COP calculation)",
    "step_3_optimization": "string (Step-by-step plan for optimizing text and metadata)",
    "step_4_validation": "string (Verify JSON outputs against output-format.md key-by-key)",
    "step_5_math_validation": "string (Patikrink ar SDS, FES, CPS skaičiavimai matematiškai teisingi)"
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
    "competitor_overlap_percentage": 0.0,
    "confidence_interval": {
      "lower_bound": 0.0,
      "upper_bound": 10.0,
      "confidence_level": "90% | 95% | 99%"
    }
  },
  "scorecard_calculations": {
    "semantic_density_formula": "string",
    "factual_extraction_formula": "string",
    "citation_probability_formula": "string",
    "calculation_audit_trail": [
      {
        "rule_applied": "string",
        "text_segment": "string",
        "points_change": 0.0,
        "running_total": 0.0
      }
    ]
  },
  "key_vulnerabilities": [
    {
      "id": "string (e.g., VULN-001)",
      "priority": 1,
      "action_type": "Quick Win | Strategic Item",
      "vulnerability": "string",
      "impact": "High | Medium | Low",
      "expected_impact_percentage": 0.0,
      "effort_to_fix": "High | Medium | Low",
      "time_to_implement": "string (e.g., 30m, 2h, 1d, 1w)",
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
