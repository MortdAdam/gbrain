---
name: aas-debugging-toolkit
description: "Use when working with debugging toolkit smart debug (Alias for debugging-toolkit-smart-debug)"
risk: unknown
source: "alias"
date_added: "2026-06-02"
triggers:
  - "aas-debugging-toolkit"
---

# Debugging Toolkit

> **This is an alias.** The canonical skill is **`debugging-toolkit-smart-debug`**.

This skill redirects to `debugging-toolkit-smart-debug`. Load it from the vault:

`skill-libraries/code-quality/debugging-toolkit-smart-debug/SKILL.md`

## When to Use
- Use this skill when working with debugging toolkit smart debug (Alias for debugging-toolkit-smart-debug)

## Why this alias exists

Users commonly search for `debugging-toolkit` but the full skill name in this collection is `debugging-toolkit-smart-debug`. This alias ensures discoverability.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.

## Examples
```text
Use @debugging-toolkit for this task: Use when working with debugging toolkit smart debug (Alias for debugging-toolkit-smart-debug).

Apply the skill to my current work and walk me through the safest next steps,
key checks, and the concrete output I should produce.
```

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
