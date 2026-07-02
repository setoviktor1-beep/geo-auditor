# GEO Auditor — Generative Engine Optimization & Semantic Search Auditor

Enterprise-grade OpenClaw skill to audit and optimize digital assets, web pages, whitepapers, and API docs for AI-first search engines and RAG retrieval pipelines (Perplexity, SearchGPT, Gemini AI Overviews).

## Features

- **Algorithmic Evaluation:** Uses strict mathematical checklists to evaluate semantic density, factual extraction, and citation probability.
- **Actionable Remediation:** Outputs prioritized vulnerabilities, effort metrics, expected impact, and copy-pasteable semantic modifications.
- **RAG-first Design:** Analyzes text structures for optimal RAG chunk sizes and removes ambiguous pronouns and superlatives.
- **JSON-LD Schema Recommendations:** Generates structured data schemas to boost LLM entity mapping.

## File Structure

```text
├── README.md
├── CHANGELOG.md
├── SKILL.md
└── references/
    ├── scoring-methodology.md
    ├── output-format.md
    └── demo-example.md
```

## How to Integrate in OpenClaw

Load the skill using Python:

```python
from openclaw import Agent, Skill

geo_skill = Skill.from_markdown("geo-auditor/SKILL.md")
agent = Agent(
    name="GEO Auditor",
    skills=[geo_skill],
    model="gemini-3.5-flash",
    model_settings={"temperature": 0.0}
)
```

## License
MIT
