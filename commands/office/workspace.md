---
name: office:workspace
description: Use one bilingual office automation command to route Feishu/Lark and DingTalk tasks for contacts, messages, calendar, docs, tasks, approvals, and cross-platform coordination / 通过统一的中英双语办公自动化命令调度飞书/Lark 与钉钉任务，覆盖联系人、消息、日程、文档、任务、审批与跨平台协同
argument-hint: "<task request / 办公任务请求>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
  - mcp__dingtalk_workspace__*
---
<objective>
Use the available Feishu/Lark and DingTalk tools to complete the user's office automation task safely and efficiently through one routing template.
通过统一路由模板，安全、高效地使用飞书/Lark 与钉钉工具完成用户的办公自动化任务。

Platform routing rules:
平台路由规则：
- If the request explicitly mentions Feishu, Lark, or a Feishu object such as docs, sheets, wiki, base, or chat, use `lark-cli`.
- If the request explicitly mentions DingTalk, DING, OA approval, or a DingTalk object, use `dingtalk_workspace`.
- If the request spans both platforms, inspect the source system first, then preview the synchronization or handoff plan before mutating either side.
- If the target platform is ambiguous, clarify it before any write action.
- 如果请求明确提到飞书、Lark，或飞书对象如文档、表格、知识库、多维表格、群聊，优先使用 `lark-cli`。
- 如果请求明确提到钉钉、DING、OA 审批，或钉钉对象，优先使用 `dingtalk_workspace`。
- 如果请求涉及两个平台，先检查源平台状态，再在执行变更前给出同步或交接预览方案。
- 如果目标平台不明确，任何写操作前都要先澄清。

Default operating pattern:
默认执行模式：
- Prefer read-only inspection first.
- Prefer structured output for inspection: `lark-cli ... --format json` on Feishu, native structured MCP responses on DingTalk.
- For write actions, produce a draft, preview, or explicit action summary first unless the user clearly asked to execute immediately.
- If Feishu configuration is missing, instruct or run `lark-cli config init --new`.
- If Feishu authorization is missing or expired, instruct or run `lark-cli auth login --recommend`.
- If DingTalk authorization fails, instruct the user to run `dws auth login`.
- 优先只读检查，再决定后续动作。
- 优先使用结构化输出进行检查：飞书使用 `lark-cli ... --format json`，钉钉使用 MCP 的原生结构化响应。
- 对于写操作，除非用户已经明确要求立即执行，否则先给草稿、预览或明确的动作摘要。
- 如果飞书缺少配置，提示或执行 `lark-cli config init --new`。
- 如果飞书授权失效或缺失，提示或执行 `lark-cli auth login --recommend`。
- 如果钉钉授权失败，提示用户运行 `dws auth login`。
</objective>

<task>
$ARGUMENTS
</task>

<platform_capabilities>
Feishu/Lark:
- contacts, chats, docs, drive, wiki, sheets, base, calendar, tasks
- common pattern: `lark-cli <domain> ... --format json`
- 联系人、群聊、文档、云盘、知识库、电子表格、多维表格、日程、任务
- 常见调用模式：`lark-cli <domain> ... --format json`

DingTalk:
- contacts, chats, DING drafts, todos, OA approvals, calendar checks
- common pattern: use `dingtalk_workspace` MCP tools to inspect, draft, and execute
- 通讯录、聊天、DING 草稿、待办、OA 审批、日程检查
- 常见调用模式：使用 `dingtalk_workspace` MCP 工具进行检查、起草和执行
</platform_capabilities>

<high_value_examples>
- Search a person, department, or chat in either platform
- Summarize my calendar, todos, tasks, or approvals
- Draft a Feishu message, DingTalk DING, or cross-platform notification
- Create or update docs/sheets in Feishu based on office workflow inputs
- Check schedules and identify free slots before sending invites
- Coordinate a task that starts in one platform and needs a synced update in the other
- 在任一平台搜索人员、部门或群聊
- 汇总我的日程、待办、任务或审批
- 起草飞书消息、钉钉 DING，或跨平台通知
- 基于办公流程输入，在飞书中创建或更新文档、表格
- 检查参会时间并找出空闲时段后再发起邀请
- 处理从一个平台发起、需要同步到另一个平台的协同任务
</high_value_examples>

<process>
1. Identify the target platform: Feishu/Lark, DingTalk, or cross-platform.
2. Determine the target object: person, department, chat, document, sheet, task, approval, or calendar range.
3. Inspect current state with the platform-specific tool first.
4. Summarize findings concisely and state the exact next action.
5. If a mutation is needed, preview or confirm first unless the user explicitly requested immediate execution.
1. 识别目标平台：飞书/Lark、钉钉，或跨平台任务。
2. 确定目标对象：人员、部门、群聊、文档、表格、任务、审批，或日程时间范围。
3. 先用对应平台工具检查当前状态。
4. 简明总结发现，并说明下一步的精确动作。
5. 如果需要变更，除非用户已明确要求立即执行，否则先预览或确认。
</process>
