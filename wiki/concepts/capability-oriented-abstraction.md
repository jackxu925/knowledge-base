# Capability-Oriented Abstraction

**标签：** #Architecture #Agent-Design #Connector #Skill-System

---

## 定义

Capability-Oriented Abstraction（面向能力的抽象）是一种架构设计思想：系统不直接绑定具体的工具或产品，而是声明"需要什么能力"，由运行环境将能力映射到具体的实现。

## 核心思想

- **声明能力类别**：例如 `~~project tracker`、`~~knowledge base`、`~~chat`、`~~product analytics`
- **不绑定品牌**：关键不在工具产品的品牌，而在它能否提供所需上下文（backlog、ticket、status、owner、dependency）
- **运行环境映射**：skill 声明能力类别 → 运行环境映射到具体 MCP server / tool adapter / API

## 在 Anthropic PM Skills 中的应用

Anthropic 的 `CONNECTORS.md` 采用此抽象：
- skill 不直接调用 Jira、Notion、Linear
- 而是声明需要 "project tracker" 能力
- 具体使用哪个 tracker，由部署环境决定

## 优势

1. **可迁移性**：同一套 skill 可在不同团队间迁移
2. **稳定性**：workflow 本身保持稳定，变化的是 connector
3. **解耦**：skill 与 SaaS 产品解耦，降低依赖风险

## 与 MCP 的关系

- connector 本身**不是** MCP
- connector 是"需要什么能力"的抽象声明
- MCP 是实际连接外部工具的协议/实现方式
- 落地时：skill 声明能力类别 → 运行环境映射到 MCP server

## 对比

| 方式 | 绑定对象 | 灵活性 | 示例 |
|------|----------|--------|------|
| 直接绑定 | 具体 SaaS | 低 | "调用 Jira API" |
| Capability-Oriented | 能力类别 | 高 | "需要 project tracker 能力" |

## 相关概念

- [[MCP]] — Model Context Protocol
- [[Agent Skill System]] — 可复用、可组合的 agent 工作流
- [[Tool Adapter]] — 将能力映射到具体工具的适配层
