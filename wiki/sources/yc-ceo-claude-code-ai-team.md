---

type: source
title: "YC CEO：如何让 Claude 为你的 AI 工程团队编写代码？"
url: https://mp.weixin.qq.com/s/q94y3egNYQPEWFWd6Na2xg
author: Capihom Capihom / 晚点再听LaterCast
date: 2026-04-27
platform: 微信公众号（晚点再听LaterCast）
original: Y Combinator / Gary Tan
topics: [AI Coding, Claude Code, Agent Workflow, Software Factory, YC]
updated: 2026-05-03
---


# YC CEO：如何让 Claude 为你的 AI 工程团队编写代码？

> YC 总裁兼 CEO Gary Tan 分享了他用 Claude Code + GStack 构建软件的方法论：把 agent 当作工程团队管理（角色+流程+评审），而不是更强的单个助手。

---

## TL;DR

Gary Tan 认为 AI 编程的瓶颈不是模型智能，而是缺乏让 agent 明确任务边界、知道何时停下、如何自检的生产流程。他同时运行 10-15 个 Claude Code 会话，通过 Office Hours（商业验证）→ Plan Mode（对抗性评审）→ Design Shotgun（并行设计）→ Code + Browser QA → Ship 的完整流水线，实现接近 "level 7 software factory" 的产出效率。

---

## 核心观点

### 1. 把 Agent 当团队管理，不是当实习生

- **问题**：默认状态下模型会游荡、会猜，"看起来很像"的产出最危险
- **解法**：给 agent 团队结构——角色、流程和评审
- **架构原则**：thin harness（薄框架）+ fat skills（厚专业能力）

### 2. Office Hours：先验证需求再写代码

agent 在动手前先问商业问题：
- 你有什么最强证据证明真的有人想要这个？
- 现有替代品为什么还没解决你的问题？
- 这个痛点的商业楔子是什么？

**价值**：把"我想做一个功能"提前改成"这个痛点有没有足够强的商业楔子"。

### 3. 对抗性评审：计划不是文档，是返工预防

- 模型给出多条实现路径
- 人类选择方向后，系统做多步对抗性评审
- 自动发现和修复问题（案例：16 个问题被发现和修复）
- 评分从 6 分提高到 8 分
- 不能自动修复的问题被显性化记录

### 4. AI 编程的关键是会评审，不是会写代码

- Gary 写了 Playwright + Chromium CLI，让 agent 能在真实浏览器里验证
- 能截图、点击、填表、下载、跑回归测试、根据问题更新 CSS
- **新瓶颈**：人类被困在 QA 环节，必须把验证自动化

> "如果 agent 只会写代码，你得到的是更快的风险；如果它还能在真实浏览器里验证，你才开始接近可交付的软件工厂。"

### 5. Design Shotgun：并行设计，人做选择

- 一次生成 3 个设计方向
- 人负责判断哪一个更贴近用户场景
- AI 让草案变多，品味和取舍仍然回到人

### 6. Level 7 Software Factory：多 Agent 并行

- Gary 同时运行 10-15 个 Claude Code 会话
- 每个想法/bug report 变成独立 worktree
- 不再有待办清单，所有事项自动变成 work item
- **前提**：每条线都有清楚的边界和交付门槛

**完整流水线**：
```
Office Hours → CEO Review → 工程评审 → 对抗性评审 → 最终 Review → Ship
```

### 7. 安全护栏

- 对开源 PR 非常谨慎（供应链攻击风险）
- ship tool 是合并到 main 之前的最后确认
- 把安全、质量和交付节奏变成默认动作

---

## 关键引用

> "瓶颈不是模型的智能。只要把模型设置对，它们已经足够聪明。"

> "我不再有待办清单了。每一个想法或 bug report，都会变成一个新的 work item。"

> "这是历史上最不可思议的软件构建时刻，构建门槛已经坍塌。"

---

## 相关概念

- [[GStack]] — Gary Tan 的 agent 脚手架框架
- [[Office Hours]] — agent 先验证商业假设再写代码的流程
- [[Adversarial Review]] — 对抗性评审，自动发现方案漏洞
- [[Design Shotgun]] — 一次生成多个设计方向供人选择
- [[Software Factory]] — 多 agent 并行的软件工厂模式
- [[Browser QA]] — 在真实浏览器中自动验证

---

## 相关实体

- [[Gary Tan]] — YC 总裁兼 CEO
- [[Y Combinator]] — 创业加速器
- [[Claude Code]] — Anthropic 的 coding agent
- [[Posterous]] — Gary 此前创办的公司

---

## 来源

- 原始资料：[[raw/articles/yc-ceo-claude-code-ai-team]]
- 原始视频：https://www.youtube.com/watch?v=wkv2ifxPpF8
