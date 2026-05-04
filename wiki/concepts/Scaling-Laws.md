---
type: concept
title: "Scaling Laws (扩展定律)"
created: 2026-05-04
updated: 2026-05-04
related: [[OpenAI]], [[Greg-Brockman]], [[Yi-Ma]], [[LLM-Training]]
confidence: high
aliases: [扩展定律, 缩放定律]
defined_by: ["OpenAI Research", "Chinchilla Paper"]
first_seen: "2020-01"
status: active
---

# Scaling Laws (扩展定律)

## 核心定义

扩展定律指的是在大规模语言模型训练中观察到的一种经验规律：随着计算资源（compute）、模型参数数量（parameters）和训练数据量（data）的增加，模型性能会以可预测的方式提升。

## 关键洞见

### Greg Brockman 的观点 (2026-05)

> "扩展定律是深层而美丽的奥秘。它们感觉非常基础，就像物理学定律一样。这些是经验性的，我们不一定有完整的理论来解释为什么它有效。"

- 神经网络早在 1940 年代就被设计出来，远在计算机之前
- 我们能够采用当时开发的想法，并应用越来越多的计算
- 只要向模型投入更多计算，它们就会变得更强大
- "没有墙"——扩展仍在继续

### Yi Ma 的理论解释 (2026-05)

> "没有魔法——涌现能力来自模型目标（损失函数）与训练分布之间的交互。随着规模增加，这些交互变得更加复杂，产生意外的能力。"

### 核心原则

1. **计算预算最优分配**: Chinchilla 论文表明，在固定的计算预算下，数据和参数需要大致等比例缩放
2. **涌现能力**: 当规模超过某个阈值时，模型会突然获得新能力
3. **无免费午餐**: 通用 post-training 对特定任务仍然很重要

## 相关人物

- [[Greg-Brockman]] (OpenAI) - 扩展定律的实践者
- [[Yi-Ma]] (Microsoft Research) - 理论研究者
- Ilya Sutskever - 扩展定律早期研究者

## 参考来源

- [[summary-ai-builders-digest-2026-05-04]]