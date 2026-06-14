---
title: "HarnessAgent"
summary: "Vercel AI SDK 4.0的统一agent编排抽象层"
read_when:
  - Understanding agent orchestration patterns
  - Vercel AI SDK updates
---

# HarnessAgent

## 定义

**HarnessAgent** 是Vercel AI SDK 4.0引入的统一抽象层，用于将任何agent的"大脑"编排和集成到应用中。它让开发者摆脱了模型和agent的锁定。

## 核心概念

- **统一抽象**: 不再依赖特定模型或特定agent实现
- **可移植性**: 一次编写，可在多个agent后端运行
- **愉悦的开发者体验**: 设计优先考虑开发者体验

## 背景

Guillermo Rauch (Vercel CEO) 在2026年6月12日发布:

> "We just shipped HarnessAgent, a unified abstraction to orchestrate and integrate any agent's 'brain' into your app. @aisdk now frees you from both model and agent lock-in."

## 意义

1. **新战场**: 编码agent的竞争从模型本身转移到harness和scaffolding层
2. **解耦**: 模型是可替换的，harness是持久的差异化
3. **生态**: 允许多个agent provider共存

## 相关概念

- [[Agent-Architecture]]
- [[Dynamic-Workflows]]
- [[Single-Agent-Orchestration]]

## 来源

- [[raw/news/2026-06-14-ai-builders-digest.md]]
- Vercel AI SDK 4.0 announcement (2026-06-12)