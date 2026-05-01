---
type: entity
title: "Claude Opus 4.7"
aliases: []
defined_by: [[Anthropic]]
first_seen: 2026-05-02
sources:
  - [[summary-ai-ai-2026-05-02]]
related:
  - [[Anthropic]]
  - [[AI-Coding]]
  - [[Claude Sonnet 4.6]]
status: active
---

# Claude Opus 4.7

Anthropic 于 2026 年 4 月 16 日发布的旗舰大语言模型。

## 关键性能指标

| 维度 | 表现 |
|------|------|
| SWE-bench Pro | **64.3%**（超越 GPT-5.4 和 Gemini 3.1 Pro）|
| OSWorld（Computer Use）| **94%**（超越人类基线）|
| 视觉分辨率 | 3.75 MP（约前代 3 倍）|
| 上下文窗口 | 1M Token，原生支持 |
| Tokenizer | 新版（相同输入 token 效率 1.0-1.35x 提升）|

## 新功能

- **xhigh effort tier**：更深度推理模式
- **/ultrareview 命令**：深度代码审查命令
- Claude Sonnet 4.6 Computer Use 达 94%，GPT-5.4 达 75%

## 定价

- 输入：$5/百万 Token
- 输出：$25/百万 Token
- 与 Opus 4.6 定价相同

## 竞争态势

Claude Opus 4.7 在 SWE-bench Pro 上领先，但在 Terminal-Bench 2.0 上仍落后于 GPT-5.5。Claude Sonnet 4.6 以 $3/$15 的定价成为最具性价比的 Computer Use 工具。