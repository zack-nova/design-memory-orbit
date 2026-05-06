# Design Memory Model

Design memory 是设计讨论的长期记忆层，保存 agent 和人类都需要反复引用的项目语言、边界和决策。

## 记忆类型

- `CONTEXT.md`：项目正式领域语言、上下文边界和未决问题。
- `CONTEXT-MAP.md`：multi-context 仓库的 context 索引。
- `docs/adr/*.md`：已确认的架构、边界、约束和重要取舍。
- `<context>/CONTEXT.md`：context 级领域语言。
- `<context>/docs/adr/*.md`：context 级决策记录。

## 职责

- 让 agent 在工作前读取相关术语和历史决策。
- 在讨论中澄清模糊语言，沉淀正式术语。
- 把难逆转、非显然、有真实取舍的决策记录成 ADR。
- 在新输出与既有 ADR 冲突时明确提示。

## 非职责

- 不管理 issue tracker、metadata、review artifact 或交付状态。
- 不替代 Issue Tracker Contract Orbit、manager orbit 或 execution orbit。
- 不把代码实现细节包装成领域术语。
- 不为“看起来完整”而创建空记忆文件。
