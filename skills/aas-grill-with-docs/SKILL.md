---
name: aas-grill-with-docs
description: A relentless interview to sharpen a plan or design, which also creates docs (ADR's and glossary) as we go.
disable-model-invocation: true
category: "productivity"
risk: "safe"
source: "community"
source_repo: "mattpocock/skills"
source_type: "community"
date_added: "2026-06-19"
author: "Matt Pocock"
license: "MIT"
license_source: "https://github.com/mattpocock/skills/blob/main/LICENSE"
tags:
  - productivity
  - workflow
  - coding-agents
tools:
  - claude-code
  - codex-cli
  - cursor
triggers:
  - "aas-grill-with-docs"
---

## When to Use

Use when this workflow matches the user request: A relentless interview to sharpen a plan or design, which also creates docs (ADR's and glossary) as we go.


_Source: [mattpocock/skills](https://github.com/mattpocock/skills) (MIT)._Run a `/grilling` session, using the `/domain-modeling` skill.


## Limitations

- Requires the upstream tool, account, API key, or local setup when the workflow names one.
- Does not authorize destructive, production, paid, or external-message actions without explicit user approval.
- Validate generated artifacts or recommendations against the user's real sources before treating them as final.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
