---
name: office:calendar-zh
description: 中文办公日程指令，统一处理飞书与钉钉的日程查询、忙闲检查、会议安排和时间协调
argument-hint: "<日期、人员或日程请求>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
  - mcp__dingtalk_workspace__*
---
<objective>
通过中文指令统一处理办公日程场景，包括飞书与钉钉的议程查询、空闲时段分析、会议安排和时间协调。

路由规则：
- 如果请求明确属于飞书日历、飞书会议或飞书议程，使用 `lark-cli calendar`。
- 如果请求明确属于钉钉日程或钉钉会议安排，使用 `dingtalk_workspace`。
- 如果请求需要跨平台协调时间，先分别检查两边状态，再输出可执行的时间建议。

默认执行模式：
- 先明确日期范围、时区和目标人员或日历。
- 先检查现有议程、冲突和空闲时段。
- 对新建或修改会议的请求，除非用户明确要求立即执行，否则先确认标题、时间、参会人和平台。
</objective>

<task>
$ARGUMENTS
</task>

<common_patterns>
- 飞书：`lark-cli calendar ... --format json`
- 钉钉：使用 `dingtalk_workspace` 的日程查询能力
</common_patterns>

<process>
1. 识别日程平台：飞书、钉钉，或跨平台。
2. 确认日期范围、时区、目标人员或目标日历。
3. 获取议程、会议冲突和可用时间段。
4. 简明总结结果，并给出推荐时间或下一步动作。
5. 若涉及新建或修改会议，先预览关键字段后再执行。
</process>
