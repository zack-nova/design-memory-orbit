# Design Memory Workflow

Design Memory Workflow 用于在设计讨论需要时维护长期项目语言、上下文边界和 ADR。

## 按需读取

- 讨论项目术语、context boundary、架构决策、`CONTEXT.md`、
  `CONTEXT-MAP.md` 或 ADR 时，先读 `docs/design-memory-orbit/INDEX.md`，
  再按索引读相关子文档。
- 需要确认现有项目语言或 ADR 约束时，读取任务相关的 `CONTEXT.md`、
  `CONTEXT-MAP.md` 和 `docs/adr/`。

## 常驻边界

- 不得编造领域术语、context boundary 或架构决策；不确定内容必须保留为
  open question。
- 缺少项目记忆不是错误；只在术语、关系、边界、open question 或决策被确认后
  lazy create。
- 任何输出若与既有 ADR 冲突，必须明确指出冲突并等待人类决策。
