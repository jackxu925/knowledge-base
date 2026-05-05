---
type: entity
title: Claude Code
created: 2026-05-06
updated: 2026-05-06
related:
  - [[AI-Coding]]
  - [[AI-Agent-安全]]
  - [[Anthropic]]
confidence: high
---

# Claude Code

Anthropic 开发的 AI 编程 CLI 工具，在代码理解和大型项目处理方面表现优异。

## 源码泄露事件（2026-05）

- **规模**：512K 行 Claude Code 源码泄露
- **发现漏洞**：
  - shell 命令拒绝规则在 50 个子命令后静默失效
  - MemoryTrap 漏洞允许恶意内存跨会话和用户传播
  - 上下文投毒通过 compaction 实现
  - shell 解析器差异导致沙箱绕过
- **安全影响**：AI Agent 安全从理论威胁转变为现实风险

## 安全趋势

- Anthropic Mythos 已展示 32 步自主网络攻击能力
- 企业需立即从模型级安全转向基础设施级安全控制
