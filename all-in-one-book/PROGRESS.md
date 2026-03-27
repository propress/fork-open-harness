# OpenHarness 实现原理全解 — 写作进度

## 章节规划

| # | 章节标题 | 文件名 | 核心覆盖 | 状态 |
|---|---------|--------|---------|------|
| 1 | 序言：全局视角 | ch01-overview.md | 项目定位、架构全景图、核心概念词典、代码库地图、典型交互全流程 | ✅ |
| 2 | 数据流全景 | ch02-data-flows.md | 五大典型场景的完整数据流：单轮对话、多轮会话、子代理委派、后台子代理编排、UI 流式推送 | ✅ |
| 3 | Agent 核心引擎 | ch03-agent-engine.md | Agent 类、事件流模型、工具审批装饰器、懒初始化策略、多步执行循环 | ✅ |
| 4 | Session 与中间件体系 | ch04-session-middleware.md | Session 状态管理、Compaction 两阶段策略、Retry 退避、Runner/Middleware 函数式组合、Conversation | ✅ |
| 5 | 工具系统与扩展 | ch05-tools-skills-mcp.md | 内置工具（fs/bash）、Skills 发现与注入、MCP Server 集成、自定义工具 | ✅ |
| 6 | 子代理系统 | ch06-subagents.md | task 工具生成、深度递减、后台 AgentRegistry、Promise 组合器语义、事件冒泡 | ✅ |
| 7 | UI 集成层 | ch07-ui-integration.md | UIStream 转换、SSE 数据协议、React hooks/provider、Vue composables/provider、数据部件类型 | ✅ |
| 8 | 端到端追踪 | ch08-end-to-end.md | 三个关键场景的完整代码路径追踪：CLI 单轮、Next.js 流式请求、带 Compaction 的长对话 | ✅ |

## 状态说明
- ✅ 已完成  - 🔄 进行中  - ⏳ 待开始

## 术语约定

| 英文术语 | 中文释义 | 首次出现章节 |
|---------|---------|------------|
| Agent | 无状态代理执行器 | Ch1 |
| Session | 有状态会话管理器 | Ch1 |
| Conversation | 轻量有状态 Runner 包装器 | Ch1 |
| Runner | 与 Agent.run() 同构的异步生成器函数 | Ch1 |
| Middleware | Runner → Runner 的高阶函数变换 | Ch1 |
| Compaction | 上下文窗口逼近时的消息压缩 | Ch1 |
| Subagent | 父代理通过 task 工具委派的子代理 | Ch1 |
| AgentRegistry | 后台子代理的生命周期管理器 | Ch6 |
| Skill | 按需注入的 Markdown 知识包 | Ch5 |
| MCP Server | Model Context Protocol 外部工具服务 | Ch5 |
| UIStream | SessionEvent → AI SDK 5 UIMessageChunk 的流转换 | Ch7 |
| AgentEvent | Agent.run() 产出的类型判别联合事件 | Ch1 |
| SessionEvent | AgentEvent + 会话生命周期事件的超集 | Ch4 |

## 下次续写指引

### 从哪里继续
全部 8 章已完成。

### 交接备忘
- 全书 8 章覆盖了 OpenHarness 的所有核心模块
- 认知路径：全局视角 → 数据流 → Agent 引擎 → Session/中间件 → 工具 → 子代理 → UI → 端到端验证
- 所有核心概念首次出现均有解释和配图
- 所有核心流程均有 Mermaid 图

### 待验证项
- ch08 中的行号为近似值，建议后续对照最新源码核实
