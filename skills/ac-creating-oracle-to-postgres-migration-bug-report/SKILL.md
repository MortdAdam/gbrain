---
name: ac-creating-oracle-to-postgres-migration-bug-report
description: 'Creates structured bug reports for defects found during Oracle-to-PostgreSQL migration. Use when documenting behavioral differences between Oracle and PostgreSQL as actionable bug reports with severity, root cause, and remediation steps.'
triggers:
  - "ac-creating-oracle-to-postgres-migration-bug-report"
---

# Creating Bug Reports for Oracle-to-PostgreSQL Migration

## When to Use

- Documenting a defect caused by behavioral differences between Oracle and PostgreSQL
- Writing or reviewing a bug report for an Oracle-to-PostgreSQL migration project

## Bug Report Format

Use the template in [references/BUG-REPORT-TEMPLATE.md](references/BUG-REPORT-TEMPLATE.md). Each report must include:

- **Status**: ✅ RESOLVED, ⛔ UNRESOLVED, or ⏳ IN PROGRESS
- **Component**: Affected endpoint, repository, or stored procedure
- **Test**: Related automated test names
- **Severity**: Low / Medium / High / Critical — based on impact scope
- **Problem**: Expected Oracle behavior vs. observed PostgreSQL behavior
- **Scenario**: Ordered reproduction steps with seed data, operation, expected result, and actual result
- **Root Cause**: The specific Oracle/PostgreSQL behavioral difference causing the defect
- **Solution**: Changes made or required, with explicit file paths
- **Validation**: Steps to confirm the fix on both databases

## Oracle-to-PostgreSQL Guidance

- **Oracle is the source of truth** — frame expected behavior from the Oracle baseline
- Call out data layer nuances explicitly: empty string vs. NULL, type coercion strictness, collation, sequence values, time zones, padding, constraints
- Client code changes should be avoided unless required for correct behavior; when proposed, document and justify them clearly

## Writing Style

- Plain language, short sentences, clear next actions
- Present or past tense consistently
- Bullets and numbered lists for steps and validations
- Minimal SQL excerpts and logs as evidence; omit sensitive data and keep snippets reproducible
- Stick to existing runtime/language versions; avoid speculative fixes

## Filename Convention

Save bug reports as `BUG_REPORT_<DescriptiveSlug>.md` where `<DescriptiveSlug>` is a short PascalCase identifier (e.g., `EmptyStringNullHandling`, `RefCursorUnwrapFailure`).

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
