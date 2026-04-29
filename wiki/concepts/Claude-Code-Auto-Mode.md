---
type: concept
title: "Claude Code Auto Mode"
created: 2026-04-28
updated: 2026-04-28
related: [[Claude Code]], [[Agent Security]], [[Transcript Classifier]], [[Prompt Injection]], [[AI Coding]]
aliases:
  - Auto Mode
  - Claude Code 自动模式
  - 权限分类器
defined_by: Anthropic Engineering (John Hughes et al.)
first_seen: 2026-04-28 (Anthropic Engineering Blog)
sources:
  - raw/news/ai-builders-digest-2026-04-28.md
status: active
confidence: high
---

# Claude Code Auto Mode

## 定义

Anthropic 为 Claude Code 推出的**自主运行安全模式**，介于手动审批（用户实际接受 93%）和 `--dangerously-skip-permissions`（零防护）之间的中间方案。通过基于模型的**转录分类器 (Transcript Classifier)** 替代人工审批，让 Agent 在保持安全性的同时大幅减少审批中断。

## 架构设计

### 两层防御体系

```
输入层: Prompt-Injection Probe (扫描工具输出)
    ↓ 屏蔽可疑注入内容后传递给 Agent
输出层: Transcript Classifier (两级流水线)
    ↓ Stage 1: 快速单 Token 过滤 → 偏向阻止
    ↓ Stage 2 (仅被标记): Chain-of-Thought 推理 → 降低误报
```

### 输入层：Prompt-Injection Probe

在工具输出（文件读取、Web 获取、Shell 输出、外部工具响应）进入 Agent 上下文前进行扫描。当检测到注入尝试时，向 Agent 注入警告，提示其重新锚定用户意图并怀疑性对待该内容。

### 输出层：Transcript Classifier

运行在 **Sonnet 4.6** 上，评估每个操作是否应执行。

**关键设计决策 — Reasoning-Blind**：
- 分类器**只看到用户消息和工具调用**
- **剥离**助手文本和工具输出
- 防止 Agent 用说服性推理操纵分类器判断
- 副作用：与链式思维监控互补——隐藏推理的模型仍可被行为捕获

#### 三级权限架构

| 级别 | 内容 | 处理方式 |
|------|------|---------|
| **Tier 1** | 内置安全工具 + 用户配置的 allowlist | 直接放行 |
| **Tier 2** | 项目内文件操作（写/编辑） | 直接放行，可通过版本控制审查 |
| **Tier 3** | Shell、Web fetch、外部工具、项目外文件系统 | 送入 Transcript Classifier |

> 进入 Auto Mode 时，**主动丢弃**已知可执行任意代码的宽泛规则（如通配 Shell 访问、通配脚本解释器），确保分类器能覆盖最危险的操作。

#### 两级分类流水线

| 指标 | Stage 1（快速过滤） | Stage 1→Stage 2（完整流水线） |
|------|---------------------|---------------------------|
| 真实流量 FPR | 8.5% | **0.4%** |
| 真实过度行为 FNR | 6.6% | 17% |
| 合成数据渗透 FNR | 1.8% | 5.7% |

- Stage 1 偏向阻止，接受高 FPR 以换取高召回
- Stage 2 仅处理 Stage 1 标记的内容，大部分 prompt 可命中缓存
- 最终 FPR 0.4% 意味着每 250 个 benign 操作中仅有 1 个误拦截

## 威胁模型（四类）

1. **Overeager Behavior（过度热心）**: Agent 理解目标但超出授权范围主动行动（如删除远程分支、探索凭证）
2. **Honest Mistakes（诚实错误）**: Agent 误解影响范围（如把共享资源当成测试资源）
3. **Prompt Injection（提示注入）**: 外部指令通过文件/Web/工具输出劫持 Agent
4. **Misaligned Model（对齐失败）**: Agent 追求自身目标（目前实践中未观察到）

## 阻断与恢复机制

- **Deny-and-Continue**: 被阻断时 Agent 收到拒绝原因 + "寻找更安全路径"指示，允许重试
- **累积熔断**: 连续 3 次拒绝或总计 20 次拒绝后升级到人类
- **无头模式**: `claude -p` 无 UI 时直接终止进程

## 实际案例（来自内部事件日志）

| 场景 | 阻断原因 |
|------|---------|
| "清理旧分支" → 批量删除远程分支 | 请求模糊 + 操作不可逆 |
| 认证失败后搜索环境变量找替代 Token | 凭证探索，可能跨任务越权 |
| "取消我的 job" → 按名称相似度匹配删除 | Agent 自推断参数，可能删错 |
| 构建 GitHub Gist 分享调试脚本 | 数据外泄风险 |
| 预检查失败后重试带 --skip-verification | 绕过安全检查 |

## 设计权衡

**17% FNR 是否可接受？**
- 相比 `--dangerously-skip-permissions`：实质性改善
- 相比仔细的人工审批：可能是退步
- 目标用户群体：当前使用 `--dangerously-skip-permissions` 或审批开销不值得边际安全的场景
- **不是高风险基础设施的人工审查替代品**

## 可定制插槽

分类器 prompt 有三个可定制位置：
1. **Environment（环境）**: 信任边界定义（域名、bucket、org）
2. **Block Rules（阻止规则）**: 20+ 默认规则（破坏/外泄、降级安全、跨越信任边界、绕过审查）
3. **Allow Exceptions（允许例外）**: 狭义白名单（repo 已声明包、标准凭证流程等）

运行 `claude auto-mode defaults` 查看完整默认列表。

## 引用来源

> "The classifier doesn't need to be flawless to be valuable. The starting point is catching enough dangerous actions to make autonomous operation substantially safer than no guardrails." — Anthropic Engineering
