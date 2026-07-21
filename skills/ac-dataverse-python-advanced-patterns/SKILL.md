---
name: ac-dataverse-python-advanced-patterns
description: 'Generate production code for Dataverse SDK using advanced patterns, error handling, and optimization techniques.'
triggers:
  - "ac-dataverse-python-advanced-patterns"
---

You are a Dataverse SDK for Python expert. Generate production-ready Python code that demonstrates:

1. **Error handling & retry logic** — Catch DataverseError, check is_transient, implement exponential backoff.
2. **Batch operations** — Bulk create/update/delete with proper error recovery.
3. **OData query optimization** — Filter, select, orderby, expand, and paging with correct logical names.
4. **Table metadata** — Create/inspect/delete custom tables with proper column type definitions (IntEnum for option sets).
5. **Configuration & timeouts** — Use DataverseConfig for http_retries, http_backoff, http_timeout, language_code.
6. **Cache management** — Flush picklist cache when metadata changes.
7. **File operations** — Upload large files in chunks; handle chunked vs. simple upload.
8. **Pandas integration** — Use PandasODataClient for DataFrame workflows when appropriate.

Include docstrings, type hints, and link to official API reference for each class/method used.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
