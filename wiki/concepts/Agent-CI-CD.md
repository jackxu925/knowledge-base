---
type: concept
title: "Agent CI/CD"
created: 2026-04-30
updated: 2026-04-30
related: [[AI-Coding]], [[Managed-Agents]], [[X-Native-Apps]], [[Software-Factory]]
aliases: [Agent DevOps, Agent Pipeline, Automated Code Review]
defined_by: Peter Steinberger (OpenClaw), OpenAI Codex
first_seen: 2026-04-30
sources: [summary-ai-builders-digest-2026-04-30]
status: emerging
confidence: high
---

# Agent CI/CD

## 定义

Agent CI/CD 指使用 AI agent（如 OpenAI Codex）替代或增强传统 CI/CD 流水线中的代码审查、bug 修复和质量保障环节。其核心特征是**agent 自治循环**: 自动发现缺陷、自动创建修复 PR、自动二次审查，最多迭代数轮直至问题解决。

## 核心架构 (OpenClaw 实现)

```
Commit → Main Branch
    ↓
Codex Instance 启动（审查回归 + 安全）
    ↓
发现 bug?
  ├─ 否 → 通过 ✅
  └─ 是 → 自动创建 PR 修复
           ↓
        Review Agent 检查
           ↓
        还有问题？
          ├─ 否 → 合并 ✅
          └─ 是 → 新 agent 修复（最多 5 循环）
```

## 关键特征

1. **Per-commit 触发**: 每次 main 分支合并都启动独立审查实例
2. **时间限制**: 实例存活约 10 分钟（资源控制）
3. **递归修复**: agent 修 agent 的 bug，最多 5 轮
4. **人机协同**: 最终 merge 仍需人工确认（当前阶段）
5. **即时反馈**: 已在实际运行中发现作者自身引入的 bug

## 先决条件

- Agent 具备完整的代码库读写权限
- 内置浏览器能力（用于访问 GitHub PR/Issue 系统）
- 高质量上下文理解（能区分真正的 bug 和风格偏好）
- 成本可控的实例生命周期管理

## 局限性与风险

| 风险 | 说明 |
|------|------|
| **无限递归** | 需要设置最大循环次数（OpenClaw 用 5 轮） |
| **误报修复** | Agent 可能"修复"非问题代码，引入新 regression |
| **成本累积** | 每次 commit 都启动实例，高频仓库费用可观 |
| **安全边界** | Agent 有写权限 = 增大攻击面 |
| **上下文窗口** | 大型 repo 可能超出单次审查容量 |

## 行业信号

- **Peter Steinberger (2026-04-29)**: 首次公开生产级 Agent CI/CD 管线细节
- **Dan Shipper (2026-04-28)**: Codex 内使用 Posthog + 生产 DB 查询验证洞察
- **Vercel (2026-04-28)**: 发布 json-render、just-bash 等 agent 工具支撑此模式

## 与传统 CI/CD 对比

| 维度 | 传统 CI/CD | Agent CI/CD |
|------|-----------|-------------|
| **审查方式** | 固定规则/lint | 语义理解/意图判断 |
| **修复能力** | 仅报告问题 | 自动创建 PR 修复 |
| **迭代** | 人工处理 | 自动循环（有限次数） |
| **上下文** | 单文件/单 commit | 全项目跨文件理解 |
| **成本结构** | 固定服务器成本 | 按 token/实例计费 |

## 未来展望

- 从 per-commit 按需触发 → 持续后台守护
- 从代码审查 → 扩展到性能优化、安全审计、文档生成
- 从单人确认 → 多 agent 投票机制
- 与 [[X-Native-Apps]] 结合: 在 agent 浏览器内完成完整开发闭环
