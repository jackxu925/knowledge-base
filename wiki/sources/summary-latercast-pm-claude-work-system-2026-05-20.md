---

type: source-summary
title: "产品经理如何把 Claude 变成自己的工作系统（Pawel / 晚点再听 LaterCast）"
source_url: https://mp.weixin.qq.com/s/RfkVvnc1_kB4lhvXWXjiGg
original_video: https://www.youtube.com/watch?v=bITUsUsrxjM&t=1259s
author: Pawel（整理：晚点再听 LaterCast）
published: ~2026-05
ingested: 2026-05-20
raw_file: "[[latercast-pm-claude-work-system-2026-05-20]]"
concepts:
  - [[PM-Work-OS]]
  - [[Claude-Dispatch]]
  - [[Founder-OS]]
  - [[Agent-Skill-System]]
  - [[Claude-Code]]
  - [[CLAUDE-md路由]]
entities:
  - Pawel（PM skills marketplace 作者，GitHub 1万star）
  - Aakash Gupta
confidence: high
updated: 2026-05-24
---


# 来源摘要：产品经理如何把 Claude 变成自己的工作系统

## 一句话概括

Pawel 展示了一套完整的 PM + Claude 工作系统，核心是：用 Skills 积累 workflow、用 CLAUDE.md 做路由调度、用 Dispatch 实现移动端多任务派发、用 Rules/Hypotheses/Rejected Patterns 三分法让系统自我迭代。

## 核心论点

1. **不要只用聊天框**：Cowork / Claude Code / Dispatch 各有专长，聊天框无法支撑 PM 的完整工作流
2. **Skills 是最高 ROI**：让系统从反馈中自动迭代，而非每次复制粘贴 prompt
3. **CLAUDE.md 只做路由**：不堆知识，指向项目结构、规则、假设、历史反馈
4. **知识三分法**：Rules（执行）/ Hypotheses（观察）/ Rejected Patterns（避免）
5. **生产环境需硬规则**：不需要自主决策的环节必须回收到代码里
6. **PM 必须学 Claude Code**：可以先用 Cowork，但终究要接触代码库

## 重要数据

- Anthropic 52天发布74次
- Pawel PM skills repo 72小时获1300 star，最终1万star
- Aakash 16个 agent 的 job search OS，eval 错误率从12%降到2%以下

## 产品矩阵（Anthropic 三件套）

| 工具 | 适合场景 |
|------|---------|
| Cowork | 个人生产力、文件整理、知识库、Gmail/Slack |
| Claude Code | 代码库、工程任务、subagents |
| Dispatch | 手机多任务派发、移动端远程调度 |

## 新增概念

- **PM Work OS**：以 Skills + CLAUDE.md + 知识三分法为基础的产品经理工作操作系统
- **Claude Dispatch**：手机端 walkie-talkie 式任务派发，支持并行后台任务
- **Progressive Disclosure**：Skills 的加载机制——只在描述匹配时读取详细步骤

## 关联来源

- [[summary-claude-founders-playbook-2026-05-14]]（同为 Claude PM 工作方式系列）
- [[anthropic-pm-skills-overview]]（PM Skills 全景）
- [[cat-wu-claude-code-pm-3-things]]（Cat Wu PM 三要素）
