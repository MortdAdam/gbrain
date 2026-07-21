---
name: aas-cqrs-implementation
description: "Implement Command Query Responsibility Segregation for scalable architectures. Use when separating read and write models, optimizing query performance, or building event-sourced systems."
risk: unknown
source: community
date_added: "2026-02-27"
triggers:
  - "aas-cqrs-implementation"
---

# CQRS Implementation

Comprehensive guide to implementing CQRS (Command Query Responsibility Segregation) patterns.

## Use this skill when

- Separating read and write concerns
- Scaling reads independently from writes
- Building event-sourced systems
- Optimizing complex query scenarios
- Different read/write data models are needed
- High-performance reporting is required

## Do not use this skill when

- The domain is simple and CRUD is sufficient
- You cannot operate separate read/write models
- Strong immediate consistency is required everywhere

## Instructions

- Identify read/write workloads and consistency needs.
- Define command and query models with clear boundaries.
- Implement read model projections and synchronization.
- Validate performance, recovery, and failure modes.
- If detailed patterns are required, open `resources/implementation-playbook.md`.

## Resources

- `resources/implementation-playbook.md` for detailed CQRS patterns and templates.

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
