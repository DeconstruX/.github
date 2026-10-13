# DeconstruX

> Deconstruct Everything — 拆开每一个技术，亲手重造它的核心。

## 这是做什么的

这是一个「以造代学」的组织。

想真正搞懂一门技术，光读论文和博客是不够的。唯一可靠的办法是：**把它最核心的那部分，从零写出来一遍**。

所以这里的每一个仓库，对应**一门技术**，只做一件事——实现它**最小但完整的核心**（core implementation），不追求生产可用，只追求真正理解。

## 写仓库的四条原则

1. **从零实现核心**。不用现成框架当黑盒绕过难点（可以用，但要能解释它替我们做了什么）。
2. **小到能一次读完**。核心版 ≠ 玩具，但也不是产品：去掉工程外壳，保留本质机制。
3. **有测试、能跑**。对着论文/原理验证行为，而不是「看起来像」。
4. **写笔记**。每个仓库的 README 讲清：这技术解决什么问题、核心思想是什么、这个实现的关键取舍在哪。

## 规划中的方向

每个仓库 = 一个技术核心。以下按主题分组，目前都是计划方向；仓库建好后会把名字换成链接。

### 基础与模型

| 仓库 | 核心内容 |
| --- | --- |
| `micrograd` | 从零的自动微分引擎 + 反向传播 |
| `transformer` | Attention / Multi-Head / 位置编码 / 残差，完整可训练 |
| `tokenizer` | BPE / WordPiece 分词器 |
| `attention-variants` | MQA / GQA / MLA、滑动窗口、稀疏注意力 |

### 推理与训练

| 仓库 | 核心内容 |
| --- | --- |
| `kv-cache` | KV Cache、PagedAttention |
| `sampling` | 温度 / Top-k / Top-p / 重复惩罚解码 |
| `lora` | LoRA 低秩微调与合并 |
| `moe` | 混合专家路由与负载均衡 |
| `quantization` | 量化原理与反量化推理 |
| `ddp` | 数据并行 / 梯度 All-Reduce，从零实现分布式训练 |

### Agent

| 仓库 | 核心内容 |
| --- | --- |
| `agent-loop` | ReAct / Plan-Execute 最小智能体循环 |
| `tool-calling` | 结构化工具调用与结果回灌 |
| `mcp` | Model Context Protocol 的最小实现 |
| `multi-agent` | 多智能体编排与消息传递 |
| `memory` | 短期/长期记忆与检索式记忆 |

### 检索与数据

| 仓库 | 核心内容 |
| --- | --- |
| `rag` | 检索增强生成的完整链路 |
| `vector-index` | HNSW / IVF 向量索引 |
| `embedding` | 文本嵌入的训练与对比学习 |

### 系统与底层

| 仓库 | 核心内容 |
| --- | --- |
| `raft` | 共识算法与复制状态机 |
| `lsm-tree` | 键值存储引擎 |
| `kv-server` | 从零的 Redis 核心 |
| `interpreter` | 词法/语法分析到解释执行 |
| `tiny-cuda` | 手写算子与 CUDA Kernel |

## 约定

- 每个仓库独立、自包含，一个仓库只讲一门技术。
- 语言按技术特点选：AI 相关多为 Python，系统相关多用 C++/Rust/Go。
- 目录基本固定：`README.md`（原理与笔记）、`src/`、`test/`、`examples/`。
- 目标是**能跑通、能验证**的最小实现，而不是又造一个轮子。

## 关于本仓库

`.github` 是这个组织的 profile 仓库，主页展示内容在 [`profile/README.md`](./profile/README.md)。
