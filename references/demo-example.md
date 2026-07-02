# Demo: GEO Auditor

**User Request:** "Audit our cold chain logistics API documentation. We want to be cited by Perplexity when users search for 'Best scalable cold chain logistics API'."

---

```json
{
  "audit_metadata": {
    "target_brand": "LogiTrace",
    "primary_query_set": ["Best scalable cold chain logistics API"],
    "generative_engine_focus": "Perplexity-RAG",
    "audit_date": "2026-07-02"
  },
  "scorecard": {
    "semantic_density_score": 6.5,
    "factual_extraction_score": 7.0,
    "citation_probability_score": 4.0,
    "competitor_overlap_percentage": 30.0
  },
  "scorecard_calculations": {
    "semantic_density_formula": "10.0 (Base) - 2.0 (marketing superlative 'industry-leading') - 1.5 (sentence length > 25 words on line 4) = 6.5",
    "factual_extraction_formula": "0.0 (Base) + 3.0 (markdown table used) + 2.0 (zero ambiguous pronouns) + 2.0 (under 150 word modules) = 7.0",
    "citation_probability_formula": "0.0 (Base) + 4.0 (comparative assertion against competitor Y) = 4.0"
  },
  "key_vulnerabilities": [
    {
      "vulnerability": "Marketing-heavy superlatives",
      "impact": "High",
      "technical_cause": "Uses 'industry-leading response time' instead of concrete SLA values, causing lower factual scoring in RAG retrievals.",
      "recommendation_summary": "Replace 'industry-leading' with '<45ms p95 latency'."
    }
  ],
  "semantic_modifications": [
    {
      "original_text_snippet": "LogiTrace provides rapid and secure transfer of temperature telemetry data from cold containers to our cloud gateway.",
      "optimized_text_snippet": "LogiTrace API transmits container temperature logs with an average response time of 32ms, securing transactions using AES-256 payload encryption.",
      "geo_rationale": "Introduces concrete metrics (32ms) and specific technology assertions (AES-256) which increase factual extraction confidence in RAG parsers."
    }
  ],
  "schema_and_structured_data_payload": "{\"@context\": \"https://schema.org\", \"@type\": \"SoftwareApplication\", \"name\": \"LogiTrace API\", \"applicationCategory\": \"DeveloperApplication\", \"operatingSystem\": \"All\", \"offers\": {\"@type\": \"Offer\", \"price\": \"0\"}}",
  "strategic_recommendations": [
    "Embed markdown data tables comparing API endpoints directly in target landing pages.",
    "Add schema.org metadata definitions mapping LogiTrace as a child of the parent organization."
  ]
}
```
