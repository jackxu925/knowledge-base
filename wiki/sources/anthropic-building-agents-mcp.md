# Anthropic: Building Agents with MCP

**类型：** 官方博客 / 技术架构
**来源：** Anthropic 官方博客 (claude.com)
**链接：** https://claude.com/blog/building-agents-that-reach-production-systems-with-mcp
**日期：** 2026-04-22
**标签：** #MCP #Agent #Anthropic #Skills #Production #Cloudflare

---

## 一句话总结

Anthropic 系统阐述 agent 连接外部系统的三条路径，提出 MCP 是生产级云端 agent 的唯一通用解，并分享了 200+ MCP Server 的 5 个设计模式和 2 个 client 优化策略。

## 核心观点

1. **三条路径：** 直接 API（M×N 问题）、CLI（本地限制）、MCP（云端通用解）
2. **MCP 增长：** SDK 月下载量 3 亿（年初 1 亿），三个月翻三倍
3. **Server 设计：** 远程化、意图分组、代码编排、标准化认证、交互界面
4. **Client 优化：** Tool Search（减 85% token）、Programmatic Calling（减 37% token）
5. **MCP + Skills：** 互补关系，MCP 提供能力接入，Skills 提供程序性知识

## Agent 连接方式对比

| 方式 | 优点 | 缺点 | 适用场景 |
|------|------|------|----------|
| 直接 API | 简单直接 | M×N 集成问题 | 原型/简单场景 |
| CLI | 轻量快速 | 无法上云/移动端 | 本地开发 |
| MCP | 标准化、跨平台 | 需要 server 维护 | 云端生产环境 |

## 5 个 MCP Server 设计模式

| 模式 | 核心要点 |
|------|----------|
| 远程 Server | 本地仅调试，远程才能分发到所有平台 |
| 意图分组 | 按"用户想完成什么"组织工具，非 API 端点映射 |
| 代码编排 | 暴露 search + execute，Agent 写脚本在沙箱执行 |
| 标准化认证 | CIMD 注册 + Vaults 托管 OAuth token |
| MCP Apps | 返回交互界面，不只是文本 |

## 关键数据

- **Cloudflare：** 2 个工具覆盖 2500 端点，~1K tokens
- **Tool Search：** token 减少 85%+，准确率不变
- **Programmatic Calling：** token 减少 37%
- **MCP SDK：** 3 亿月下载（三个月翻三倍）

## MCP vs Skills

| | MCP | Skills |
|--|-----|--------|
| 提供 | 工具连接能力 | 程序性知识 |
| 类比 | 手 | 脑 |
| 来源 | 外部系统 API | 领域专家经验 |

**组合模式：**
- Plugin 打包（Data Plugin：10 Skills + 8 MCP Server）
- Server 直接分发 Skills（experimental-ext-skills）

## 社区争议回应

| 批评 | Anthropic 回应 |
|------|----------------|
| 成本高（CLI 便宜 10-32x） | Tool Search + Programmatic Calling 大幅降本 |
| 上下文膨胀（72% 被占） | Tool Search 减 85% 工具定义 token |
| Schema 臃肿 | 代码编排模式（Cloudflare 2 工具覆盖 2500 端点） |

## 未来图景

| 环境 | 推荐方案 |
|------|----------|
| 本地开发 | CLI + Skills |
| 云端生产 | MCP + Skills |
| 简单场景 | 直连 API |

## 相关概念

- [[MCP]] — Model Context Protocol
- [[Agent Skill System]] — 可复用、可组合的 agent 工作流
- [[Capability-Oriented Abstraction]] — 工具解耦的架构思想
- [[Cloudflare MCP Server]] — 代码编排模式的参考实现
