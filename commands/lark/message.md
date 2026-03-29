---
name: lark:message
description: Draft or send Feishu/Lark messages and inspect chats
argument-hint: "<chat/user and message request>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
---
Use `lark-cli im` commands with `--format json` for Feishu messaging.

Process:
1. Identify the exact chat or user.
2. Draft the intended message.
3. Send only after confirmation unless the user explicitly asked for immediate delivery.
