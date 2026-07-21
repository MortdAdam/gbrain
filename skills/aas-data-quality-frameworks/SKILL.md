---
name: aas-data-quality-frameworks
description: "Implement data quality validation with Great Expectations, dbt tests, and data contracts. Use when building data quality pipelines, implementing validation rules, or establishing data contracts."
risk: unknown
source: community
date_added: "2026-02-27"
triggers:
  - "aas-data-quality-frameworks"
---

# Data Quality Frameworks

Production patterns for implementing data quality with Great Expectations, dbt tests, and data contracts to ensure reliable data pipelines.

## Use this skill when

- Implementing data quality checks in pipelines
- Setting up Great Expectations validation
- Building comprehensive dbt test suites
- Establishing data contracts between teams
- Monitoring data quality metrics
- Automating data validation in CI/CD

## Do not use this skill when

- The data sources are undefined or unavailable
- You cannot modify validation rules or schemas
- The task is unrelated to data quality or contracts

## Instructions

- Identify critical datasets and quality dimensions.
- Define expectations/tests and contract rules.
- Automate validation in CI/CD and schedule checks.
- Set alerting, ownership, and remediation steps.
- If detailed patterns are required, open `resources/implementation-playbook.md`.

## Safety

- Avoid blocking critical pipelines without a fallback plan.
- Handle sensitive data securely in validation outputs.

## Resources

- `resources/implementation-playbook.md` for detailed frameworks, templates, and examples.

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
