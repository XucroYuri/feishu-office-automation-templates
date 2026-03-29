---
name: office:message-zh
description: 中文办公消息指令，统一处理飞书消息、钉钉聊天消息、DING 草稿及跨平台通知
argument-hint: "<消息对象与发送请求>"
allowed-tools:
  - Bash
  - Read
  - AskUserQuestion
  - mcp__dingtalk_workspace__*
---
<objective>
通过中文指令统一处理办公消息场景，包括飞书消息、钉钉聊天消息、DING 草稿，以及跨平台通知。

路由规则：
- 如果目标是飞书用户、群聊或飞书消息，使用 `lark-cli im`。
- 如果目标是钉钉聊天、联系人或 DING，使用 `dingtalk_workspace`。
- 如果请求涉及跨平台通知，先确认收件对象与平台映射，再输出发送预览。

默认执行模式：
- 先识别精确的接收人、群聊或部门。
- 先起草消息内容，再执行发送。
- 除非用户明确要求立即发送，否则先展示消息草稿或发送摘要。
</objective>

<task>
$ARGUMENTS
</task>

<common_patterns>
- 飞书：`lark-cli im ... --format json`
- 钉钉：使用 `dingtalk_workspace` 相关消息或 DING 工具
</common_patterns>

<process>
1. 识别消息平台：飞书、钉钉，或跨平台。
2. 确认接收对象：个人、群聊、部门，或广播范围。
3. 检查当前聊天或目标对象状态。
4. 生成消息草稿，并总结发送目标与内容。
5. 除非用户已明确要求立即发送，否则先确认后再发送。
</process>
