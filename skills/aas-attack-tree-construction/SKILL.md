---
name: aas-attack-tree-construction
description: "Build comprehensive attack trees to visualize threat paths. Use when mapping attack scenarios, identifying defense gaps, or communicating security risks to stakeholders."
risk: offensive
source: community
date_added: "2026-02-27"
triggers:
  - "aas-attack-tree-construction"
---

> AUTHORIZED USE ONLY: Use this skill only for authorized security assessments, defensive validation, or controlled educational environments.

# Attack Tree Construction

Systematic attack path visualization and analysis.

## Use this skill when

- Visualizing complex attack scenarios
- Identifying defense gaps and priorities
- Communicating risks to stakeholders
- Planning defensive investments or test scopes

## Do not use this skill when

- You lack authorization or a defined scope to model the system
- The task is a general risk review without attack-path modeling
- The request is unrelated to security assessment or design

## Instructions

- Confirm scope, assets, and the attacker goal for the root node.
- Decompose into sub-goals with AND/OR structure.
- Annotate leaves with cost, skill, time, and detectability.
- Map mitigations per branch and prioritize high-impact paths.
- If detailed templates are required, open `resources/implementation-playbook.md`.

## Safety

- Share attack trees only with authorized stakeholders.
- Avoid including sensitive exploit details unless required.

## Resources

- `resources/implementation-playbook.md` for detailed patterns, templates, and examples.

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
