# neko-mind 🐱🧠

> 用 Rust 编写的 AI 女友核心运行时。

neko-mind 是 AI 女友项目 **neko** 的独立核心仓库，围绕文字聊天提供 AI 请求、上下文构造和记忆管理，并逐步支持角色与关系状态、对话编排和主动互动。

目前处于架构设计与早期原型阶段，尚未提供稳定 API。以下是建设方向，不代表已经实现。

## 设计方向

- 通用 AI 请求层：统一 `send_messages` 入口，启动时加载配置，内部适配 API，上层处理回复与工具调用。
- 上下文管理：组织角色、状态、历史和记忆，处理冲突及 token 预算，是聊天效果的核心。
- 记忆管理：保存偏好、共同经历和未完成事项，支持检索、纠错与来源追溯。
- 连贯的角色行为：探索生活状态与通信过程的协同，初期优先保证行为合理性。

多模态依赖模型及配置，不建设独立媒体处理系统。具体算法、存储及对外集成方式仍待确定。

## 文档

正文文档放在 `docs/`，按类别组织；简短说明要点，每份最多 300 行。

- [架构讨论纪要](docs/architecture/overview.md)：定位、职责、行为连续性与待定事项。
- [AI 请求层设计计划](docs/plans/ai-request-layer.md)：目录、协议、流式接口、适配器及验证。
- [编排与监控层原型设计计划](docs/plans/orchestration-layer.md)：LangGraph 原型、Context 装配、记忆导入与 Langfuse 监控层。
- [编排协作文档](docs/plans/orchestration-collaboration.md)：编排侧与 AI 请求侧的分工、接口交接和联调顺序。
- [Agent 协作约定](AGENTS.md)：AI 辅助边界与文档规则。

## 贡献原则

产品功能与核心逻辑由人编写并负责，让维护者能在 review 中提供指导，也保留亲自创造 AI 女友的意义。

AI Agent 可做只读分析、架构讨论、问题解答和文档维护，也可编写测试及项目辅助脚本、按要求协助提交。不得代写或修复核心实现，具体见 [AGENTS.md](AGENTS.md)。

## 许可证

Copyright (c) 2026 Aum.

[Apache License 2.0](LICENSE)
