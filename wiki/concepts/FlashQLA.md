---

type: concept
title: FlashQLA
aliases: [线性注意力加速, GDN 算子库]
defined_by: [[Qwen]]
first_seen: 2026-04-30
sources:
  - [[summary-ai-daily-2026-04-30]]
related:
  - [[AI-Coding]]
  - [[Qwen]]
status: active
updated: 2026-05-03
---


# FlashQLA

阿里通义千问团队开源的**高性能线性注意力算子库**，基于 TileLang 实现，专为 **Gated Delta Network (GDN)** 打造。

## 技术要点

| 维度 | 表现 |
|------|------|
| 目标架构 | Gated Delta Network (GDN) — Qwen 全系列主力注意力层 |
| 实现方式 | 基于 TileLang 的算子融合与代数优化 |
| 前向推理加速 | **2-3 倍**（NVIDIA Hopper 架构） |
| 反向训练加速 | **2 倍** |
| 对比基线 | FLA triton Kernel |

## 意义

- **降低 AI 推理成本**：同等算力吞吐量翻倍，或同等性能成本减半
- **影响 AI Coding 生态**：Qwen 系列被 Cursor、Windsurf 等广泛采用为基座模型，底层加速直接降低开发者 API 调用延迟和成本
- **技术路线信号**：线性注意力替代全量 Attention 正在成为行业共识
- **开源推动**：社区可基于此进一步优化，推动从学术到工业落地

## 来源

[腾讯新闻](https://news.qq.com/rain/a/20260429A0826C00) · [知乎技术详解](https://zhuanlan.zhihu.com/p/2032898276207350901)
