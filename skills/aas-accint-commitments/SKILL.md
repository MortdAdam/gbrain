---
name: aas-accint-commitments
description: Triage acc's open promises and close them with honest real-world verdicts via acc_act(runtime="outcome").
risk: unknown
source: https://github.com/maxbaluev/accreted-intelligence/tree/main/plugins/claude/skills/commitments
source_repo: maxbaluev/accreted-intelligence
source_type: community
date_added: 2026-07-01
license: Apache-2.0
license_source: https://github.com/maxbaluev/accreted-intelligence/blob/main/LICENSE
triggers:
  - "aas-accint-commitments"
---

# commitments
## When to Use

Use this skill when you need triage acc's open promises and close them with honest real-world verdicts via acc_act(runtime="outcome").


Routing sugar over the two MCP verbs — no logic lives here.

1. List open promises: `acc commitments` (CLI, read-only observation).
2. For each closeable one: `acc_act(runtime="outcome", input={"ref": "<id>", "good": true|false, "note": "..."})`.
3. Provenance discipline: the default `self_graded` is a WEAK prior (credits at 0.25×).
   Pass `owner` only when the owner validated, `external`/`runtime` only when reality did
   (a real reply, a passing test, a world result). Never tag your own grade as reality.
4. Leave genuinely-waiting commitments open — `waiting` is a first-class clean state.

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
