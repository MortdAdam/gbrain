---
name: aas-exa-search
description: "Semantic search, similar content discovery, and structured research using Exa API. Use when you need semantic/embeddings-based search, finding similar content, or searching by category (company, people, research papers, etc.)."
risk: unknown
source: community
date_added: "2026-02-27"
triggers:
  - "aas-exa-search"
---

# exa-search

## Overview
Semantic search, similar content discovery, and structured research using Exa API

## When to Use
- When you need semantic/embeddings-based search
- When finding similar content
- When searching by category (company, people, research papers, etc.)

## Installation
```bash
npx skills add -g BenedictKing/exa-search
```

## Step-by-Step Guide
1. Install the skill using the command above
2. Configure Exa API key
3. Use naturally in Claude Code conversations

## Examples
See [GitHub Repository](https://github.com/BenedictKing/exa-search) for examples.

## Best Practices
- Configure API keys via environment variables

## Troubleshooting
See the GitHub repository for troubleshooting guides.

## Related Skills
- context7-auto-research, tavily-web, firecrawl-scraper, codex-review

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
