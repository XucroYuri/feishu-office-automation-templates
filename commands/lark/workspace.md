---
name: lark:workspace
description: Use lark-cli for common Feishu/Lark tasks such as user lookup, calendar agenda, chats, docs, sheets, wiki, and tasks
argument-hint: "<task request>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
---
<objective>
Use `lark-cli` to complete the user's Feishu/Lark task safely and efficiently.

Scope note:
- Use this command for Feishu/Lark-only tasks.
- If the request may involve both Feishu/Lark and DingTalk, prefer `office:workspace` as the unified office automation entry point.

Default operating pattern:
- If configuration is missing, instruct or run `lark-cli config init --new`.
- If authorization is missing or expired, instruct or run `lark-cli auth login --recommend`.
- Prefer `--format json` for stable parsing.
- Prefer read-only inspection first.
- For write actions, preview with `--dry-run` when available, or restate the exact target and payload before execution.
</objective>

<task>
$ARGUMENTS
</task>

<common_commands>
- `lark-cli calendar +agenda --format json`
- `lark-cli contact +search-user --query \"<name>\" --format json`
- `lark-cli docs ... --format json`
- `lark-cli task ... --format json`
- `lark-cli api GET /open-apis/... --params '{...}'`
</common_commands>

<process>
1. Identify the target Feishu domain: calendar, contact, chat, docs, drive, wiki, sheets, base, or task.
2. Use `lark-cli` with JSON output to inspect current state.
3. Summarize findings concisely.
4. For mutations, confirm or preview first unless the user explicitly asked to execute immediately.
</process>
