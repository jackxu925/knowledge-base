---
type: source
title: "GBrain：AI Agent 持久记忆系统"
created: 2026-05-03
updated: 2026-05-03
confidence: medium
---

# GBrain：AI Agent 持久记忆系统

**类型：** 技术博客 / 开源项目介绍
**来源：** 微信公众号「光影织梦」
**链接：** https://mp.weixin.qq.com/s/MG4gHYmVhV3NdN7lIw8-9A
**日期：** 2026-04-26
**标签：** #GBrain #Agent-Memory #Knowledge-System #Garry-Tan #YC #OpenClaw

---

## 一句话总结

Y Combinator 总裁 Garry Tan 开源的 GBrain 是一个为 AI Agent 提供持久记忆的"数字大脑"系统，采用"编译真理 + 时间线"知识模型和混合搜索，让 Agent 每次对话都变得更聪明。

## 核心观点

1. **Agent 的瓶颈不是算法，是记忆** — 无状态 Agent 每次对话从零开始，无法累积知识
2. **编译真理 + 时间线** — 顶部是可重写的当前最佳理解，底部是只追加的证据轨迹
3. **复合增长循环** — 信号到达 → 实体检测 → 读取大脑 → 回应 → 写入大脑 → 同步索引
4. **三层记忆架构** — gbrain（世界知识）+ Agent 内存（操作状态）+ 会话上下文（当前对话）

## 项目信息

| 项目 | 内容 |
|------|------|
| **名称** | GBrain |
| **作者** | Garry Tan（Y Combinator 总裁）|
| **许可** | MIT |
| **GitHub** | https://github.com/garrytan/gbrain |
| **推文反响** | 3603 赞，381 转发（24小时内）|

## Garry Tan 的数据规模

| 数据类型 | 数量 |
|----------|------|
| Markdown 文件 | 10,000+ |
| 人物档案 | 3,000+ |
| 日历数据 | 13 年（21,000+ 事件）|
| Apple Notes | 5,800+（追溯到2009年）|
| 会议记录 | 280+ |
| 原创想法 | 300+ |
| 媒体页面 | 500+ |

## 知识模型：编译真理 + 时间线

```markdown
---
type: concept
title: Do Things That Don't Scale
tags: [startups, growth, pg-essay]
---

[编译真理：当前最佳理解，随证据更新而重写]

----
- 2013-07-01: 发布于paulgraham.com
- 2024-11-15: 在W25启动会议中被引用
```

- **编译真理**（`---` 上方）：当前最佳理解，新证据出现时被重写
- **时间线**（`---` 下方）：只追加的证据轨迹，永不编辑

## 核心循环

```
信号到达（会议、邮件、推文、链接）
 → Agent 检测实体（人物、公司、想法）
 → 读取：先检查大脑（gbrain search / get）
 → 带着完整上下文回应
 → 写入：用新信息更新大脑页面
 → 同步：gbrain 为下次查询索引更改
```

## 三层记忆架构

| 层 | 存储内容 | 查询方式 |
|----|----------|----------|
| **gbrain** | 人物、公司、会议、想法、媒体 | `gbrain search`、`gbrain query`、`gbrain get` |
| **Agent 内存** | 偏好、决策、操作配置 | `memory_search` |
| **会话上下文** | 当前对话 | 自动 |

## 搜索机制

| 机制 | 作用 |
|------|------|
| 关键词搜索 | 精确短语匹配 |
| 向量搜索 | 语义概念匹配 |
| RRF 融合 | 结合两者优势 |
| 多查询扩展 | 捕捉未想到的表述 |

## 技术依赖

| 依赖 | 用途 | 成本 |
|------|------|------|
| Supabase (Postgres + pgvector) | 数据库 | $25/月 |
| OpenAI API | 嵌入 (text-embedding-3-large) | 按量 |
| Anthropic API | 多查询扩展 + LLM 分块 (Haiku) | 按量 |

## 关键特性

- **梦境循环**：Agent 在睡觉时扫描当天对话，丰富实体，修复引用，整理记忆
- **混合搜索**：关键词 + 向量 + RRF 融合
- **实体检测**：自动识别人物、公司、想法
- **来源归属**：所有信息可追溯
- **铁法则反向链接**：自动维护页面间引用关系

## 社区评价

> "我们基本上正在从无状态提示转向持久记忆系统。真正的解锁不是更好的提示，而是更好的记忆。"
> —— SelanVeydris

> "无状态 Agent 是死路一条，这是缺失的持久层。"
> —— vishalojha_me

## 相关概念

- [[Agent Memory]] — Agent 持久记忆架构
- [[Knowledge Model]] — 编译真理 + 时间线模式
- [[Hybrid Search]] — 关键词与向量融合的搜索机制
- [[Compound Growth]] — 知识的复合增长效应
- [[OpenClaw]] — 与 GBrain 集成的 Agent 平台
