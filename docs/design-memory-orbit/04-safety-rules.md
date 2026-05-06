# Safety Rules

## Lazy create

- 不创建空 `CONTEXT.md`。
- 不创建空 `CONTEXT-MAP.md`。
- 不创建空 `docs/adr/`。
- 只有已确认内容需要记录时，才创建对应文件或目录。

## 不确定性

- 不确定术语写入 `Open Questions`，不得伪装成定义。
- 不确定 context 所有权时，先询问人类。
- 不确定 ADR 冲突时，标注可能冲突并列出依据。

## 写入边界

- 不修改与 design memory 无关的文件。
- 不把交付 workflow、issue 状态、review artifact 策略写进本 orbit，除非它们本身是项目架构决策。
- 不把实现细节、临时计划、短期偏好写成长期记忆。

## 冲突

发生以下情况时停止写入并请求人类决策：

- 新术语与既有 `CONTEXT.md` 定义冲突。
- 新边界与既有 `Boundaries` 冲突。
- 新 ADR 与 accepted ADR 冲突。
- `CONTEXT-MAP.md` 指向多个互相矛盾的 context 所有权。
