# BOOTSTRAP.md - Design Memory Orbit

本 orbit 安装到代码仓库，用于让 agent 能读取并维护设计讨论形成的长期项目记忆：领域语言、上下文边界与 ADR。

## 初始化步骤

### 1. 确认仓库上下文

确认当前目录是目标代码仓库根目录。

### 2. 确认可读取 orbit 文档

确认以下路径存在并可读：

```text
docs/design-memory-orbit/INDEX.md
skills/design-memory-orbit/
```

### 3. 读取规则索引

读取：

```text
docs/design-memory-orbit/INDEX.md
```

再按索引递归读取相关子文档。

### 4. 扫描已有项目记忆

检查并报告当前仓库是否已有：

```text
CONTEXT.md
CONTEXT-MAP.md
docs/adr/
```

如果存在 `CONTEXT-MAP.md`，按 multi-context 规则读取其中列出的 context 位置，并检查各 context 的 `CONTEXT.md` 与 `docs/adr/`。
如果 map 指向的 context 文件不存在，报告缺失并继续处理可读取的部分。

### 5. 报告初始化结果

输出：

- 当前是 single-context 还是 multi-context。
- 已发现的 context 文档。
- 已发现的 ADR 目录和 ADR 数量。
- 是否存在明显冲突，例如 `CONTEXT-MAP.md` 指向不存在的 context。

缺少 `CONTEXT.md`、`CONTEXT-MAP.md` 或 `docs/adr/` 不视为初始化失败。

## 禁止事项

- 不创建空的 `CONTEXT.md`。
- 不创建空的 `CONTEXT-MAP.md`。
- 不创建空的 `docs/adr/`。
- 不把未经确认的术语、边界或决策写成项目记忆。
