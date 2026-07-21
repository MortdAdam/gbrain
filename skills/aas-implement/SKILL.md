---
name: aas-implement
description: Implement a piece of work based on a PRD or set of issues.
risk: unknown
source: https://github.com/mattpocock/skills/tree/main/skills/engineering/implement
source_repo: mattpocock/skills
source_type: community
date_added: 2026-07-01
license: MIT
license_source: https://github.com/mattpocock/skills/blob/main/LICENSE
triggers:
  - "aas-implement"
---

## When to Use

Use this skill when you need implement a piece of work based on a PRD or set of issues.

Implement the work described by the user in the PRD or issues.

Use /tdd where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, use /review to review the work.

Commit your work to the current branch.

## Limitations

- Use this skill only when the task clearly matches its upstream source and local project context.
- Verify commands, generated code, dependencies, credentials, and external service behavior before applying changes.
- Do not treat examples as a substitute for environment-specific tests, security review, or user approval for destructive or costly actions.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
