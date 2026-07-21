---
name: aas-hybrid-search-implementation
description: "Combine vector and keyword search for improved retrieval. Use when implementing RAG systems, building search engines, or when neither approach alone provides sufficient recall."
risk: safe
source: community
date_added: "2026-02-27"
triggers:
  - "aas-hybrid-search-implementation"
---

# Hybrid Search Implementation

Patterns for combining vector similarity and keyword-based search.

## Use this skill when

- Building RAG systems with improved recall
- Combining semantic understanding with exact matching
- Handling queries with specific terms (names, codes)
- Improving search for domain-specific vocabulary
- When pure vector search misses keyword matches

## Do not use this skill when

- The task is unrelated to hybrid search implementation
- You need a different domain or tool outside this scope

## Instructions

- Clarify goals, constraints, and required inputs.
- Apply relevant best practices and validate outcomes.
- Provide actionable steps and verification.
- If detailed examples are required, open `resources/implementation-playbook.md`.

## Resources

- `resources/implementation-playbook.md` for detailed patterns and examples.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
