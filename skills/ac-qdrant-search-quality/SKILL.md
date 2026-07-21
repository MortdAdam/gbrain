---
name: ac-qdrant-search-quality
description: "Diagnoses and improves Qdrant search relevance. Use when someone reports 'search results are bad', 'wrong results', 'low precision', 'low recall', 'irrelevant matches', 'missing expected results', or asks 'how to improve search quality?', 'which embedding model?', 'should I use hybrid search?', 'should I use reranking?'. Also use when search quality degrades after quantization, model change, or data growth."
allowed-tools:
  - Read
  - Grep
  - Glob
triggers:
  - "ac-qdrant-search-quality"
---

# Qdrant Search Quality

First determine whether the problem is the embedding model, Qdrant configuration, or the query strategy. Most quality issues come from the model or data, not from Qdrant itself. If search quality is low, inspect how chunks are being passed to Qdrant before tuning any parameters. Splitting mid-sentence can drop quality 30-40%.

- Start by testing with exact search to isolate the problem [Search API](https://search.qdrant.tech/md/documentation/search/search/?s=search-api)


## Diagnosis and Tuning

Isolate the source of quality issues, tune HNSW parameters, and choose the right embedding model. [Diagnosis and Tuning](diagnosis/SKILL.md)


## Search Strategies

Hybrid search, reranking, relevance feedback, and exploration APIs for improving result quality. [Search Strategies](search-strategies/SKILL.md)

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
