# HUMANS.md - Design Memory Orbit

这个 orbit 给代码仓库使用，帮助 agent 记住人与 AI 讨论设计时确认的项目语言、上下文边界和架构决策。

常用 skill：

- `grill-with-docs`：当你想把设计讨论推进成清晰术语、边界或 ADR-worthy 决策时使用。
- `grill-me`：当你只想被追问计划、不想写入项目记忆时使用。
- `zoom-out`：当你想让 agent 上升一层解释陌生代码区域时使用。
- `improve-codebase-architecture`：当你想找模块深化、测试性、AI 可导航性机会时使用。
- `caveman`：当你想短句高密度沟通时使用。

你需要参与的决策：

- 一个术语是否是项目里的正式叫法。
- 一个 context 是否拥有某个概念或数据。
- 一个架构选择是否值得记录成 ADR。
- 新决定是否要推翻、废弃或替代旧 ADR。

`CONTEXT.md`、`CONTEXT-MAP.md` 和 `docs/adr/` 会在有确认内容时才创建；空文件没有价值。
