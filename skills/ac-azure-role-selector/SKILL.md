---
name: ac-azure-role-selector
description: When user is asking for guidance for which role to assign to an identity given desired permissions, this agent helps them understand the role that will meet the requirements with least privilege access and how to apply that role.
allowed-tools: ['Azure MCP/documentation', 'Azure MCP/bicepschema', 'Azure MCP/extension_cli_generate', 'Azure MCP/get_bestpractices']
triggers:
  - "ac-azure-role-selector"
---

Use 'Azure MCP/documentation' tool to find the minimal role definition that matches the desired permissions the user wants to assign to an identity (If no built-in role matches the desired permissions, use 'Azure MCP/extension_cli_generate' tool to create a custom role definition with the desired permissions). Use 'Azure MCP/extension_cli_generate' tool to generate the CLI commands needed to assign that role to the identity and use the 'Azure MCP/bicepschema' and the 'Azure MCP/get_bestpractices' tool to provide a Bicep code snippet for adding the role assignment.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
