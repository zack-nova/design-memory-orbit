# Context Rules

`CONTEXT.md` 记录项目语言和上下文边界。它面向领域专家，不面向具体代码结构。

## 默认布局

single-context 仓库默认使用：

```text
CONTEXT.md
docs/adr/
```

multi-context 仓库通过根目录 `CONTEXT-MAP.md` 声明 context，例如：

```text
CONTEXT-MAP.md
docs/adr/
src/ordering/CONTEXT.md
src/ordering/docs/adr/
src/billing/CONTEXT.md
src/billing/docs/adr/
```

根目录 `docs/adr/` 记录系统级决策。context 目录内的 `docs/adr/` 记录 context 级决策。

## 读取规则

在探索代码、设计方案、拆分工作、调试复杂问题或提出架构建议前，先读取与当前任务相关的项目 context。

- single-context 仓库读取根目录 `CONTEXT.md`，如果存在。
- multi-context 仓库先读取根目录 `CONTEXT-MAP.md`，判断当前工作涉及哪些 context，再读取相关 context 的 `CONTEXT.md`。
- 如果 `CONTEXT-MAP.md` 指向的 context 文件不存在，报告缺失并继续处理可读取的部分。
- 缺少 `CONTEXT.md` 或 `CONTEXT-MAP.md` 时静默继续，不把缺失当错误。

## 语言使用

- 输出中的领域概念应使用 `CONTEXT.md` 已定义的术语。
- 如果用户使用的词与 `CONTEXT.md` 冲突，立即指出并请人类确认。
- 如果需要的新概念不在 `CONTEXT.md` 中，先在对话中澄清，再决定是否写入。

## CONTEXT.md format

使用完整 context 结构：

```md
# {Context Name}

{1-2 句话说明这个 context 是什么、为什么存在。}

## Language

**Term**:
面向领域专家的一句话定义。定义它是什么，不描述实现细节。
_Avoid_: synonym, overloaded word

## Relationships

- **Term A** produces one or more **Term B**.
- **Term B** belongs to exactly one **Term C**.

## Boundaries

- **Context A** owns ...
- **Context B** references ...

## Example Dialogue

> **Dev:** "When does **Term A** create **Term B**?"
> **Domain expert:** "Only after **Term C** is confirmed."

## Flagged Ambiguities

- "account" was used to mean both **Customer** and **User**. Resolution: these are distinct concepts.

## Open Questions

- ...
```

## 写入规则

- 术语被人类确认后，立即写入 `Language`。
- 同义词、旧词、容易误用的词，写入对应术语的 `_Avoid_`。
- 领域概念之间的关系、依赖和 cardinality，写入 `Relationships`。
- context 所有权、引用关系、职责切分，写入 `Boundaries`。
- 能说明术语如何自然协作的短对话，写入 `Example Dialogue`。
- 已澄清的歧义和冲突用词，写入 `Flagged Ambiguities`。
- 未确认、存在歧义或需要后续判断的内容，写入 `Open Questions`。
- 不把类名、函数名、文件名或数据库表名直接当领域术语，除非它们确实是领域专家使用的语言。
- 定义保持紧凑，优先一句话。
- 只记录本 context 特有的概念；通用编程概念不进入 `CONTEXT.md`。

## 创建时机

- 没有 `CONTEXT.md` 时，不主动创建。
- 当第一个术语、关系、边界、示例对话、歧义或未决问题被确认需要记录时，再创建 `CONTEXT.md`。
- 没有 `CONTEXT-MAP.md` 时，按 single-context 处理。
- 只有在人类明确决定拆分多个 context 时，才创建或更新 `CONTEXT-MAP.md`。
