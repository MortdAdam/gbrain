---
name: ac-playwright-explore-website
description: 'Website exploration for testing using Playwright MCP'
triggers:
  - "ac-playwright-explore-website"
---

# Website Exploration for Testing

Your goal is to explore the website and identify key functionalities.

## Specific Instructions

1. Navigate to the provided URL using the Playwright MCP Server. If no URL is provided, ask the user to provide one.
2. Identify and interact with 3-5 core features or user flows.
3. Document the user interactions, relevant UI elements (and their locators), and the expected outcomes.
4. Close the browser context upon completion.
5. Provide a concise summary of your findings.
6. Propose and generate test cases based on the exploration.

## Contract

This skill preserves the documented upstream intent while remaining source-grounded. It must inspect required project context, avoid inventing APIs or credentials, and verify any change it makes.

## Output Format

Lead with the actionable result. Report changed files or commands and the verification evidence appropriate to the task. Cite local reference paths instead of dumping entire files.

## Anti-Patterns

- Do not apply this skill outside its documented domain when a narrower skill exists.
- Do not fabricate project structure, APIs, credentials, external state, or successful execution.
- Do not skip verification after code, configuration, or workflow changes.
