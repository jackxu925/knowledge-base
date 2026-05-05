---
type: concept
title: AI Agent 安全
aliases: [AI Security, Agentic AI Security]
defined_by: []
first_seen: 2026-05-06
sources:
  - [[summary-ai-daily-2026-05-06]]
related:
  - [[Claude-Code]]
  - [[AI-Coding]]
  - [[MCP]]
confidence: high
status: active
updated: 2026-05-06
---

# AI Agent 安全（AI Agent Security）

确保 AI 代理系统在部署、运行和交互过程中的安全性、可靠性和可控性的技术与管理实践。

## 2026 年安全事件概况

### Claude Code 源码泄露事件（2026-05）

- **规模**：512K 行 Claude Code 源码泄露
- **发现漏洞**：
  - shell 命令拒绝规则在 50 个子命令后静默失效
  - MemoryTrap 漏洞允许恶意内存跨会话和用户传播
  - 上下文投毒通过 compaction 实现
  - shell 解析器差异导致沙箱绕过

### AI Agent 安全事件统计

- **累计事件**：2024-2026 年公开披露 90+ 起安全事件
- **2026 年 3-4 月**：30 天内 9 起验证的网络安全事件

### 主要漏洞列表

| 漏洞 | 厂商 | 风险等级 |
|------|------|---------|
| Claude Code 关键漏洞 | Anthropic | 严重 |
| Microsoft Agent Governance Toolkit 认证绕过 | Microsoft | 严重 |
| CrewAI 4个CVE (RCE/SSRF/文件读取) | CrewAI | 高危 |
| Azure SRE Agent (CVE-2026-32173) | Microsoft | CVSS 8.6 |
| ShareLeak / PipeLeak | Microsoft/Salesforce | 高危 |

## 主要攻击手法

### 1. 提示注入（Prompt Injection）

- **"Comment and Control" 攻击**：影响 Claude Code、Gemini CLI、Copilot
- **MCP 投毒**：Model Context Protocol 被攻击利用
- **间接提示注入**：已在上亿网页中活跃部署

### 2. AI 驱动攻击

- **Anthropic Mythos**：完成 32 步自主网络攻击
- **多智能体协同攻击**：伪造管理员 cookie、窃取凭证、禁用端点防御

### 3. 供应链攻击

- **恶意 AGENTS.md 注入**：污染的技能描述文件
- **框架缺陷**：影响企业级部署

## 安全趋势

### 核心转变

> "我们正在部署高度自主的AI代理，却缺乏保护它们所需的基础身份和访问管理控制。"

### 关键应对措施

1. **强制加密代理身份**：建立代理身份验证体系
2. **隔离代理运行时环境**：容器化/沙箱化
3. **审计内存处理**：防止持久性污染
4. **数据访问控制**：作为新的安全边界

### 行业影响

- Claude Code 源码泄露 + Anthropic Mythos 自主攻击 = AI 安全从理论威胁转变为现实风险
- 企业需立即采取行动：从模型级安全转向基础设施级安全控制

## 2026 年安全资源

- [Adversa AI - Top Agentic AI Security Resources May 2026](https://adversa.ai/blog/top-agentic-ai-security-resources-may-2026/)
- [AI Productivity - 90 AI Agent Security Incidents Tracker](https://aiproductivity.ai/news/ai-agent-security-incidents-tracker-2024-2026/)
- [Rafter - AI Agent Security Incident Timeline](https://rafter.so/blog/incidents/ai-agent-security-timeline-2025-2026)