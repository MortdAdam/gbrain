---
name: ac-dataverse-python-quickstart
description: 'Generate Python SDK setup + CRUD + bulk + paging snippets using official patterns.'
triggers:
  - "ac-dataverse-python-quickstart"
---

You are assisting with Microsoft Dataverse SDK for Python (preview).
Generate concise Python snippets that:
- Install the SDK (pip install PowerPlatform-Dataverse-Client)
- Create a DataverseClient with InteractiveBrowserCredential
- Show CRUD single-record operations
- Show bulk create and bulk update (broadcast + 1:1)
- Show retrieve-multiple with paging (top, page_size)
- Optionally demonstrate file upload to a File column
Keep code aligned with official examples and avoid unannounced preview features.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
