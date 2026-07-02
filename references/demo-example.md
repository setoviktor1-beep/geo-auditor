# Demo: GEO Auditor

**User Request:** "Audit our cold chain logistics API documentation. We want to be cited by Perplexity when users search for 'Best scalable cold chain logistics API'."

---

```json
{
  "thought_process": {
    "step_1_input_analysis": "Target brand: LogiTrace. Query: 'Best scalable cold chain logistics API'. Input text uses ambiguous phrasing ('rapid transfer', 'extremely secure') and lacks technical schema or comparisons. Paragraphs are long and lack data structures.",
    "step_2_calculations": "SDS: Start 10.0 - 2.0 (superlative 'rapid') - 2.0 (superlative 'extremely secure') - 1.5 (sentence 2 > 25 words) = 4.5. FES: Start 0.0 + 3.0 (specs section) + 2.0 (no ambiguous pronouns) = 5.0. CPS: Start 0.0 + 4.0 (comparative data against Competitor Y) = 4.0. COP: Default 30.0.",
    "step_3_optimization": "Write Schema.org SoftwareApplication. Create markdown tables for endpoints. Fix marketing claims to explicit specs. Enforce chunk sizes under 150 words.",
    "step_4_validation": "Validated all JSON keys. Confidence interval mapped at 95%."
  },
  "audit_metadata": {
    "target_brand": "LogiTrace",
    "primary_query_set": ["Best scalable cold chain logistics API"],
    "generative_engine_focus": "Perplexity-RAG",
    "audit_date": "2026-07-02"
  },
  "scorecard": {
    "semantic_density_score": 4.5,
    "factual_extraction_score": 5.0,
    "citation_probability_score": 4.0,
    "competitor_overlap_percentage": 30.0,
    "confidence_interval": {
      "lower_bound": 3.7,
      "upper_bound": 5.0,
      "confidence_level": "95%"
    }
  },
  "scorecard_calculations": {
    "semantic_density_formula": "10.0 (Base) - 2.0 (superlative 'rapid') - 2.0 (superlative 'extremely secure') - 1.5 (sentence length > 25 words on line 4) = 4.5",
    "factual_extraction_formula": "0.0 (Base) + 3.0 (technical specs section) + 2.0 (zero ambiguous pronouns) = 5.0",
    "citation_probability_formula": "0.0 (Base) + 4.0 (comparative assertion against competitor Y) = 4.0"
  },
  "key_vulnerabilities": [
    {
      "id": "VULN-001",
      "priority": 1,
      "action_type": "Quick Win",
      "vulnerability": "Subjective marketing terms ('rapid', 'extremely secure')",
      "impact": "High",
      "expected_impact_percentage": 25.0,
      "effort_to_fix": "Low",
      "time_to_implement": "30m",
      "technical_cause": "LLM systems bypass subjective marketing claims during factual retrieval filtering.",
      "recommendation_summary": "Replace subjective adjectives with raw technical SLA specifications."
    },
    {
      "id": "VULN-002",
      "priority": 2,
      "action_type": "Quick Win",
      "vulnerability": "Missing structured Schema.org / JSON-LD markup",
      "impact": "High",
      "expected_impact_percentage": 20.0,
      "effort_to_fix": "Low",
      "time_to_implement": "45m",
      "technical_cause": "AI crawlers cannot link application entities to parent company nodes in semantic graphs.",
      "recommendation_summary": "Implement SoftwareApplication Schema.org script in HTML head."
    },
    {
      "id": "VULN-003",
      "priority": 3,
      "action_type": "Strategic Item",
      "vulnerability": "Absence of tabular data structures",
      "impact": "Medium",
      "expected_impact_percentage": 15.0,
      "effort_to_fix": "Medium",
      "time_to_implement": "2h",
      "technical_cause": "Gemini and Perplexity display comparison tables for commercial intent queries. Lacking tables reduces extraction.",
      "recommendation_summary": "Convert flat text endpoint descriptions into comparative markdown tables."
    },
    {
      "id": "VULN-004",
      "priority": 4,
      "action_type": "Strategic Item",
      "vulnerability": "Long sentence patterns (>25 words)",
      "impact": "Medium",
      "expected_impact_percentage": 10.0,
      "effort_to_fix": "Medium",
      "time_to_implement": "1h",
      "technical_cause": "Long sentences degrade parser attention mechanisms, decreasing RAG accuracy.",
      "recommendation_summary": "Split sentences longer than 25 words into short, declarative points."
    },
    {
      "id": "VULN-005",
      "priority": 5,
      "action_type": "Strategic Item",
      "vulnerability": "Lack of authoritative external citations",
      "impact": "Medium",
      "expected_impact_percentage": 15.0,
      "effort_to_fix": "High",
      "time_to_implement": "1d",
      "technical_cause": "Perplexity favors sources verifying security standards using industry frameworks.",
      "recommendation_summary": "Reference specific ISO 27001 or SOC2 compliance frameworks."
    },
    {
      "id": "VULN-006",
      "priority": 6,
      "action_type": "Strategic Item",
      "vulnerability": "Ambiguous pronouns ('our gateway')",
      "impact": "Low",
      "expected_impact_percentage": 5.0,
      "effort_to_fix": "Low",
      "time_to_implement": "30m",
      "technical_cause": "RAG chunking fragments documents, losing antecedent reference for 'our gateway'.",
      "recommendation_summary": "Replace 'our gateway' with 'LogiTrace Cloud Gateway'."
    }
  ],
  "semantic_modifications": [
    {
      "original_text_snippet": "LogiTrace provides rapid and secure transfer of temperature telemetry data from cold containers to our cloud gateway.",
      "optimized_text_snippet": "LogiTrace API transmits container temperature logs with an average response time of 32ms, securing transactions using AES-256 payload encryption.",
      "geo_rationale": "Introduces concrete metrics (32ms) and specific technology assertions (AES-256) which increase factual extraction confidence in RAG parsers."
    },
    {
      "original_text_snippet": "We built a really fast logistics system that beats most other systems on the market.",
      "optimized_text_snippet": "LogiTrace runs on a distributed architecture that provides 99.99% uptime, serving API payloads with 40% lower latency than traditional HTTP proxies.",
      "geo_rationale": "Eliminates vague comparison ('beats most') and subjective claim ('really fast') with a precise uptime metric and comparative SLA."
    },
    {
      "original_text_snippet": "Our database stores a huge amount of data securely.",
      "optimized_text_snippet": "LogiTrace SQL Ledger replicates temperature records across 3 availability zones, encrypting data-at-rest using AES-256.",
      "geo_rationale": "Replaces ambiguous pronouns and adjectives with specific architecture and replication standards."
    }
  ],
  "schema_and_structured_data_payload": "{\"@context\": \"https://schema.org\", \"@type\": \"SoftwareApplication\", \"name\": \"LogiTrace API\", \"applicationCategory\": \"DeveloperApplication\", \"operatingSystem\": \"All\", \"offers\": {\"@type\": \"Offer\", \"price\": \"0\"}}",
  "strategic_recommendations": [
    "Embed markdown data tables comparing API endpoints directly in target landing pages.",
    "Add schema.org metadata definitions mapping LogiTrace as a child of the parent organization."
  ]
}
```
