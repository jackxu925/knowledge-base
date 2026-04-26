# Tool Search

**标签：** #MCP #Optimization #Token-Efficiency #Agent

---

## 定义

Tool Search（工具搜索/懒加载）是 MCP Client 端的优化策略：不在 context 中预加载所有工具定义，而是让 Agent 在运行时按需搜索工具目录，只把匹配的工具定义拉进上下文。

## 解决的问题

**传统方式的痛点：**
- 连接 5 个 MCP server，每个 20 个工具 = 100 个工具定义常驻 context
- 58 个工具（GitHub 35 + Slack 11 + Sentry 5 + Grafana 5 + Splunk 2）= ~55K tokens
- 还没开始干活，工作台就被说明书堆满

## 工作原理

```
Agent 描述意图 → 搜索工具目录 → 匹配相关工具 → 只加载匹配的定义
```

1. Agent 先描述它想做什么
2. 系统在运行时搜索相关工具
3. 只把匹配的几个工具定义拉进 context

## 实测效果

| 指标 | 结果 |
|------|------|
| 工具定义 token | 减少 85%+ |
| 工具选择准确率 | 基本不变 |
| Opus 4 准确率 | 49% → 74% |
| Opus 4.5 准确率 | 79.5% → 88.1% |

**示例：**
- 传统：58 个工具 = ~55K tokens
- Tool Search：~8.7K tokens

## 设计原则

**工具要按意图分组，别按 API 分。**

- 按"用户想完成什么"组织
- 减少工具数量，提高每个工具的价值密度
- Agent 一次调用完成任务，减少协调成本

## 与 Programmatic Calling 的关系

Tool Search 解决的是**工具定义过多**的问题：
- 减少进入 context 的工具描述数量

Programmatic Tool Calling 解决的是**工具结果过多**的问题：
- 减少工具返回结果进入 context 的数量

**两者叠加：** context 更精简、往返次数更少、响应更快、成本更低。

## 相关概念

- [[MCP]] — Tool Search 是 MCP Client 的优化策略
- [[Programmatic Tool Calling]] — 互补的 client 端优化
- [[Agent Skill System]] — 工具组织的上层架构
