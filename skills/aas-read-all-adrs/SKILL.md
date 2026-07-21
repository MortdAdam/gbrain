---
name: aas-read-all-adrs
description: "Read every ADR in a project before summarizing architectural context or decisions."
category: productivity
risk: safe
source: community
source_repo: davidondrej/skills
source_type: community
date_added: "2026-07-07"
author: davidondrej
tags: [adr, documentation, architecture]
tools: [claude, codex]
license: "MIT"
license_source: "https://github.com/davidondrej/skills/blob/main/LICENSE"
disable-model-invocation: true
triggers:
  - "aas-read-all-adrs"
---

<!-- TODO(David): write the strong wording here -->

## When to Use

- Use when the user explicitly asks to load ADR context.
- Use when architectural decisions must be understood before changing or judging a project.

Read EVERY single ADR `.md` file in this project's `docs/adr/` folder, start to
finish.

Do not skim. Read each ADR completely before summarizing.

Read every single ADR file, for this project, in full.

## Limitations

- Adapted from `davidondrej/skills`; verify local paths, tools, credentials, and agent features before acting.
- For commands, remote access, scheduling, browser automation, or file-changing workflows, get explicit user approval and confirm the target environment first.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
