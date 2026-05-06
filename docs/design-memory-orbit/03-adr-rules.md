# ADR Rules

ADR 记录难逆转、非显然、存在真实取舍的项目决策。

## 存放位置

- 系统级 ADR：`docs/adr/`
- context 级 ADR：`<context>/docs/adr/`

目录只在第一个 ADR 被确认后创建。

## 读取与使用规则

在探索代码、设计方案、拆分工作、调试复杂问题或提出架构建议前，读取与当前任务相关的 ADR。

- single-context 仓库读取根目录 `docs/adr/` 中的相关 ADR。
- multi-context 仓库先读取根目录 `docs/adr/` 中的相关系统级 ADR，再读取相关 context 的 `docs/adr/`。
- 缺少 ADR 目录或相关 ADR 时静默继续，只说明未找到相关记录；不把 ADR 缺失解读为“没有约束”。
- 不重复争论已被 accepted ADR 确认的取舍。
- 若确有现实理由挑战旧 ADR，明确指出冲突并请人类决策。

## 文件名与标题

文件名：

```text
docs/adr/0001-short-slug.md
```

标题：

```md
# 0001 Short Decision Title
```

编号从目标 ADR 目录中已有最大编号加一。

## 格式

```md
---
status: accepted
---

# 0001 Short Decision Title

1-3 句话说明：背景是什么、决定是什么、为什么。
```

可选段落只在真的有价值时加入：

```md
## Considered Options

## Consequences

## Supersedes
```

## 状态

允许状态：

- `proposed`
- `accepted`
- `deprecated`
- `superseded`

默认状态是 `accepted`。

## 何时创建 ADR

只有三项同时成立时才建议创建：

- 难逆转：以后改主意的成本明显。
- 非显然：未来读者会想知道为什么这样做。
- 有真实取舍：存在合理替代方案，并且做出了选择。

如果只是临时偏好、显而易见的实现选择、容易改回的细节，不写 ADR。

## 冲突处理

如果新建议或新决策与既有 ADR 冲突：

- 明确指出冲突的 ADR 编号和标题。
- 说明冲突点。
- 等待人类决定是保留旧 ADR、更新旧 ADR、废弃旧 ADR，还是新增 superseding ADR。
