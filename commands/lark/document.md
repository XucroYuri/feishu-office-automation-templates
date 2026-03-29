---
name: lark:document
description: Inspect or modify Feishu/Lark docs, wiki, drive files, or sheets
argument-hint: "<document request>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
---
Use `lark-cli docs`, `drive`, `wiki`, or `sheets` commands with `--format json`.

Process:
1. Determine the target document type and object.
2. Inspect current content or metadata first.
3. Summarize key findings.
4. For mutations, restate exact edits before execution.
