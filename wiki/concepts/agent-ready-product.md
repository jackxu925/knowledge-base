---
type: concept
title: "Agent-Ready Product"
description: "为 AI agent 访问而设计的产品，APIs 和 MCPs 成为主要接口而非 GUI"
aliases: ["Agent-Native", "Agent-First"]
---

# Agent-Ready Product

> 为 AI agent 访问而设计的产品。在 AI agent 时代，APIs 和 MCPs 正在成为主要接口，而非传统的 GUI。

---

## 定义

Agent-Ready Product 是指从设计之初就考虑 AI agent 访问和使用的产品。这类产品：

- 提供稳定的 API 接口
- 支持 MCP (Model Context Protocol)
- 可被 AI agent 理解和操作
- 不仅为人类用户设计 GUI

---

## 为什么重要

### 接口转变

| 时代 | 主要接口 | 用户 |
|------|---------|------|
| PC 时代 | GUI (鼠标/键盘) | 人类 |
| 移动时代 | 触摸界面 | 人类 |
| AI 时代 | API / MCP | AI Agent |

### 数据支持

- Mercury 数据显示创业公司正在大量采用 AI agent
- OpenAI vs Anthropic 在企业市场的竞争加剧
- 产品开发流程将被永久改变

---

## 设计原则

### 1. API-First
- 所有核心功能都有 API 暴露
- API 设计考虑 agent 的可理解性
- 清晰的错误信息和状态返回

### 2. MCP Support
- 提供 MCP server 实现
- 标准化工具描述
- 支持上下文传递

### 3. Agent-Friendly
- 可机器读取的文档
- 结构化输出
- 幂等操作设计

---

## MCP vs CLI 的选择

| 维度 | MCP | CLI |
|------|-----|-----|
| 集成深度 | 深度集成 | 轻量级 |
| 学习成本 | 需要理解协议 | 命令行熟悉 |
| 适用场景 | 复杂交互 | 简单操作 |
| DAU 影响 | 可能 cannibalize | 较低风险 |

### 关键问题

- Will MCPs cannibalize your app DAU?
- 如何平衡 agent 访问和人类用户体验？

---

## 实施建议

1. **审计现有 API** — 确保所有功能可编程访问
2. **添加 MCP 支持** — 成为 agent 生态系统的一部分
3. **监控 agent 使用** — 理解 agent 行为模式
4. **设计反馈循环** — 让 agent 使用改进产品

---

## 参考

- 来源：[[sources/how-to-build-for-ai-agents-claude-code-second-brain]]
- 相关：[[MCP]], [[AI Agent]]
