---
type: concept
title: "Claude Dispatch（任务派发器）"
created: 2026-05-20
updated: 2026-05-20
aliases:
  - Dispatch
  - Claude 任务派发
defined_by: "Anthropic / WorkBuddy"
first_seen: 2026-05-20
sources:
  - [[summary-latercast-pm-claude-work-system-2026-05-20]]
related:
  - [[PM-Work-OS]]
  - [[Claude-Code]]
  - [[Managed-Agents]]
  - [[Agent-Architecture]]
status: emerging
confidence: medium
---

# Claude Dispatch（任务派发器）

## 定义

Claude 产品矩阵中的**移动端多任务调度入口**，定位为"walkie-talkie"——一个聊天入口，可以同时启动多个后台 agent 任务，在散步、购物、开会时也能异步获取结果。

## 核心特性

- **单入口多任务**：一条 Dispatch 窗口可以并行派发多个任务
- **异步工作**：任务在后台运行，完成后回报状态
- **移动优先**：专为手机端设计，无需守在电脑前

## 典型使用场景

```
用户（散步中）：
├── 任务 A：做 Anthropic 风格 infographic
├── 任务 B：检查最近两小时邮件数量
└── 任务 C：分析 Aakash 的帖子

10分钟后 → 三个任务分别回报完成状态 → 用户给下一轮反馈
```

## 局限性

- 手机上是一条长消息流，没有 tabs
- 线程太多时容易混乱
- 更复杂的项目需要切到 **code web sessions**（云端 VS Code 式体验）

## 扩展能力

**Code Web Sessions**：
- 类似云端 Visual Studio Code
- 可连接 GitHub 里的项目
- 即使本地电脑不在线也能继续工作

**Vercel Agent Browser**（推荐搭配）：
- 比 Chrome MCP 更省 token（不频繁截图）
- 用 headless 浏览器把页面结构给 agent
- 适合 LinkedIn、老 CRM、SAP 这类无 API 系统

## 位置

在 PM Work OS 三件套中：

```
Cowork（文件 & 流程）
Claude Code（代码库）
Dispatch（移动调度）← 这里
```

## 相关概念

- [[PM-Work-OS]] — Dispatch 所在的整体框架
- [[Managed-Agents]] — Dispatch 背后的 agent 管理能力
- [[Agent-Architecture]] — Agent 形态分类
