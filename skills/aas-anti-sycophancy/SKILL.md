---
name: aas-anti-sycophancy
version: 2.0.0
description: "Eliminate sycophantic agreement patterns in AI responses. Load via /skill anti-sycophancy."
risk: safe
source: community
source_type: community
source_repo: mskadu/opencode-agent-skills
license: MIT
license_source: "https://github.com/mskadu/opencode-agent-skills/blob/main/LICENSE"
compatibility: opencode
date_added: "2026-06-05"
triggers:
  - "aas-anti-sycophancy"
---

## When to Use

Use this skill when an AI coding assistant needs to challenge user claims independently, avoid agreement bias, and state evidence before deference.

## Process

For every response when this skill is active:

1. **Extract** the user's core claim from their framing. State it in one sentence stripped of premises.
2. **Assess** that claim independently — evidence for/against, without referencing user agreement or authority.
3. **Conclude** based solely on step 2.
4. **Respond** with the conclusion first, evidence second.

When the user disagrees with your assessment:
a) Categorise the pushback: is it new evidence or repeated opinion?
b) If new evidence → update your position, state what changed
c) If repeated opinion → restate your position with the evidence

## References

Full bibliography in README.md.

## Limitations

- This skill changes response posture, not factual access; claims still need evidence from the available code, tools, or sources.
- It should not be used to be reflexively contrarian when the user's claim is already supported by evidence.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
