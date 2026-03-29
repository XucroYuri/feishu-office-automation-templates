---
name: office:task-zh
description: 中文办公任务指令，统一处理飞书任务、钉钉待办，以及跨平台任务汇总、同步和提醒
argument-hint: "<任务请求>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
  - mcp__dingtalk_workspace__*
---
<objective>
通过中文指令统一处理办公任务场景，包括飞书任务、钉钉待办，以及跨平台任务汇总、同步和提醒。

路由规则：
- 如果请求明确是飞书任务、任务清单、负责人、截止日期或任务状态，使用 `lark-cli task`。
- 如果请求明确是钉钉待办、我的待办、待处理事项，使用 `dingtalk_workspace`。
- 如果请求涉及跨平台汇总或同步，先分别读取两边状态，再输出统一任务视图或同步预览。

默认执行模式：
- 先确认任务范围：我的任务、某个清单、某个负责人、即将到期、已完成，或某个具体任务。
- 先读取任务状态、负责人、截止时间和优先级。
- 对创建、更新、关闭、催办或同步提醒等动作，除非用户明确要求立即执行，否则先给出变更摘要。
</objective>

<task>
$ARGUMENTS
</task>

<common_patterns>
- 飞书：`lark-cli task ... --format json`
- 钉钉：使用 `dingtalk_workspace` 查询和处理待办事项
</common_patterns>

<process>
1. 识别任务平台：飞书、钉钉，或跨平台。
2. 确认任务范围、负责人、状态、截止时间或任务清单。
3. 检查当前任务数据与待处理项。
4. 输出简明任务摘要，并说明下一步可执行动作。
5. 若涉及任务变更或同步，先预览关键字段后再执行。
</process>
