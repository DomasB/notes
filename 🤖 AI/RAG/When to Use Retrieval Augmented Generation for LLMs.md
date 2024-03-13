---
tags:
- LLMs
- RAG
- AI 
Link: https://crunchingthedata.com/when-to-use-retrieval-augmented-generation-for-llms/

---

Main idea: Retrieval Augmented Generation (RAG) enhances Large Language Models (LLMs) by providing additional, relevant context from a curated document library. This article explains RAG's working mechanism, required data, advantages, disadvantages, and scenarios for its effective use.

## Sections:

### What is Retrieval Augmented Generation

- RAG adds context to LLMs from a curated library of documents relevant to user prompts.

### What Data is Needed for RAG

- RAG requires a collection of text-based data and embeddings of these documents for effective context retrieval.

### Advantages of RAG

- Provides domain-specific context, improves predictive performance, and is cost-effective.
- Requires less labor and computational resources than fine-tuning LLMs.
- Applicable to state-of-the-art models without removing built-in guardrails.

### Disadvantages of RAG

- May introduce additional latency and privacy concerns.
- Requires data curation and introduces extra tokens, potentially increasing costs.

### When to Use RAG

- Useful when LLMs need more context for effective response and to reduce hallucinations.

### When Not to Use RAG

- Not suitable for contexts that can be shared across all prompts or need extensive context.
- Avoid if additional latency is a concern.

## Related ideas

- Improving LLM Performance
- Fine-tuning LLMs
- Prompt Engineering Techniques