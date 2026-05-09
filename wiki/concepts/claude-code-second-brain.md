---

type: concept
title: "Claude Code Second Brain"
description: "基于 Claude Code 的个人知识管理系统，通过 5 阶段方法论构建持久化的工作记忆"
aliases: ["Second Brain", "Claude Second Brain", "Personal Knowledge System"]
updated: 2026-05-03
---


# Claude Code Second Brain

> 基于 Claude Code 的个人知识管理系统，通过 5 阶段方法论构建持久化的工作记忆，将生产力提升 2 倍。

---

## 定义

Claude Code Second Brain 是一种使用 Claude Code 作为核心基础设施构建的个人知识管理系统。它将用户的工作历史、文档、反思和学习组织成一个可查询、可扩展的知识库，使 AI 能够在每次交互中访问相关上下文。

---

## 核心架构 (5 阶段方法论)

### Phase 1: Create a profile
**目标**: 建立基础身份档案

- 让 Claude 通过对话式采访收集信息
- 生成 `~/Documents/second-brain/me.md`
- 包含：
  - 角色、公司、职责
  - 优化目标（优先级、成功标准）
  - 工作风格（日常工具、沟通方式、痛点）
  - 成长边界（反馈、想要打破的模式）
  - 工作外兴趣（帮助推荐）

### Phase 2: Build the knowledge base
**目标**: 构建向量化的文档库

- 保存关键文档到本地文件夹：
  - Product specs
  - Retrospectives
  - 绩效评估
  - 重要会议记录
- 安装 QMD (Shopify CEO 的向量搜索工具)
- 使 Claude 能够引用这些文档

### Phase 3: Distill the data
**目标**: 提取战略摘要

基于 me.md 和知识库生成：
- `strategic-context.md` — 公司/团队的目标和原因
- `personal-growth.md` — 反馈模式、教练主题

### Phase 4: Auto-context injection
**目标**: 自动化上下文加载

- 创建 Claude Code hook
- 每次 prompt 自动从相关文件提取上下文
- 减少手动复制粘贴

### Phase 5: Learning loop
**目标**: 持续学习和进化

- 构建 `/learn` skill
- 每次会话后自动更新 `Claude.md`
- 设置 cron jobs：
  - 早间简报（每日）
  - 月度回顾（每月）

---

## 关键组件

| 组件 | 文件 | 作用 |
|------|------|------|
| 个人档案 | `me.md` | 基础身份和工作风格 |
| 战略上下文 | `strategic-context.md` | 公司和团队目标 |
| 个人成长 | `personal-growth.md` | 反馈模式和教练主题 |
| 知识库 | `docs/` | 原始文档存储 |
| 学习记录 | `Claude.md` | 会话总结和学习 |

---

## 使用场景

1. **驱动团队优先级** — 基于历史数据做出决策
2. **自我反思** — 通过 AI 教练进行个人成长
3. **会议准备** — 自动提取相关背景信息
4. **决策支持** — 基于过去经验提供建议

---

## 与其他系统的对比

| 特性 | Claude Code Second Brain | 传统笔记系统 | 纯 RAG |
|------|------------------------|------------|--------|
| 个性化 | 深度个人化 | 手动组织 | 通用 |
| 进化能力 | 自动学习更新 | 静态 | 依赖外部更新 |
| 上下文注入 | 自动化 | 手动搜索 | 查询时检索 |
| 反思循环 | 内置 | 无 | 无 |

---

## 参考

- 来源：[[sources/how-to-build-for-ai-agents-claude-code-second-brain]]
- 实现者：Ryan Wiggins (Mercury VP of Product)
- 工具：[[Claude Code]], [[QMD]]
