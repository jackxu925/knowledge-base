---
type: concept
title: "GStack"
description: "Gary Tan 构建的 agent 脚手架框架，核心理念是 thin harness + fat skills，把 agent 当作工程团队管理"
aliases: ["Agent Scaffold", "AI Engineering Framework"]
---

# GStack

> YC CEO Gary Tan 构建的 agent 脚手架框架，核心理念是 **thin harness + fat skills**——外层框架尽量薄，真正的能力沉到可复用的专业技能里。

---

## 定义

GStack 是一套让 Claude Code 从"更强的单个助手"升级为"可管理的工程团队"的薄脚手架。它把复杂度放在可复用的 skills 里，而不是堆一个笨重外壳。

---

## 核心架构：Thin Harness + Fat Skills

| 层级 | 职责 | 特点 |
|------|------|------|
| **Harness（薄框架）** | 连接 agent 和代码库 | 尽量薄，只负责调度 |
| **Skills（厚技能）** | 可复用的专业能力 | 真正的复杂度在这里 |

**对比**：
- 笨重外壳：把所有逻辑堆在一个大 prompt 里
- GStack 方式：把能力拆成独立 skill，每次构建沿同一套质量标准前进

---

## 包含的工具/流程

1. **Office Hours** — 商业验证流程
2. **Plan Mode** — 方案规划和对抗性评审
3. **Design Shotgun** — 并行设计生成
4. **Browser CLI** — Playwright + Chromium 自动化验证
5. **Ship Tool** — 合并前的最终确认

---

## Gary 的使用数据

- 同时运行 **10-15 个 Claude Code 会话**
- 过去两个月写的代码比 2013 年一整年还多
- Posterous（当年两年/千万美元/十人团队）现在可用 agent 复刻大部分

---

## 核心原则

1. **角色化** — 给 agent 明确的角色（CEO、工程师、设计师、QA）
2. **流程化** — 每条 work item 都跑完整流水线
3. **评审化** — 多层评审确保质量
4. **并行化** — 多 worktree 同时推进

---

## 参考

- 来源：[[sources/yc-ceo-claude-code-ai-team]]
- 作者：Gary Tan
- 相关：[[Software Factory]], [[Office Hours]], [[Adversarial Review]]
