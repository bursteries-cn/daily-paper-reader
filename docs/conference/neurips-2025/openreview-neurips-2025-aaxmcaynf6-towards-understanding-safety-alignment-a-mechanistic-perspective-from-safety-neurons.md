---
title: "Towards Understanding Safety Alignment: A Mechanistic Perspective from Safety Neurons"
title_zh: 理解安全对齐：从安全神经元的机械视角
authors: "Jianhui Chen, Xiaozhi Wang, Zijun Yao, Yushi Bai, Lei Hou, Juanzi Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=AAXMcAyNF6"
tags: ["query:model-edit"]
score: 4.0
evidence: 通过安全神经元分析安全对齐机制
tldr: "本文从机械可解释性角度研究安全对齐，通过推理时激活对比定位安全神经元，并利用动态激活补丁评估其因果作用。实验发现约5%的神经元控制安全行为，仅调整这些神经元的激活即可恢复超过90%的安全性能。该工作为理解安全对齐的内部机制提供了新视角，并暗示通过精确编辑安全神经元可能成为一种高效的安全对齐编辑方法。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1342, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1388, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1376, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 1440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 1512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1440, \"height\": 1515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1433, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aaxmcaynf6/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1451, \"height\": 627, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 695, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 711, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 662, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 708, \"height\": 748, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 559, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 1665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1420, \"height\": 1525, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 813, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aaxmcaynf6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 777, \"height\": 213, \"label\": \"Table\"}]"
motivation: 即使经过安全对齐，LLM仍会产生有害内容，但安全对齐的内部工作机制尚不明确。
method: 提出推理时激活对比定位安全神经元，并应用动态激活补丁验证其因果影响。
result: "在多个LLM中一致识别出约5%的安全神经元，通过补丁可恢复90%以上的安全性能。"
conclusion: 安全神经元是决定模型安全行为的关键，激活补丁为安全对齐编辑提供了精准靶点。
---

## Abstract
Large language models (LLMs) excel in various capabilities but pose safety risks such as generating harmful content and misinformation, even after safety alignment. In this paper, we explore the inner mechanisms of safety alignment through the lens of mechanistic interpretability, focusing on identifying and analyzing safety neurons within LLMs that are responsible for safety behaviors. We propose inference-time activation contrasting to locate these neurons and dynamic activation patching to evaluate their causal effects on model safety. Experiments on multiple prevalent LLMs demonstrate that we can consistently identify about 5% safety neurons, and by only patching their activations we can restore over 90% of the safety performance across various red-teaming benchmarks without influencing general ability. The finding of safety neurons also helps explain the ''alignment tax'' phenomenon by revealing that the key neurons for model safety and helpfulness significantly overlap, yet they require different activation patterns for the same neurons. Furthermore, we demonstrate an application of our findings in safeguarding LLMs by detecting unsafe outputs before generation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型语言模型（LLM）在安全对齐后仍易受攻击，生成有害内容或错误信息，但安全对齐的内部工作机制尚未被深入理解。本文旨在从机械可解释性（Mechanistic Interpretability）角度，**揭示安全对齐背后负责安全行为的神经元（称为“安全神经元”）**，并解释对齐税（alignment tax）现象——安全性与有用性之间的权衡。
- **整体含义**：通过定位并验证安全神经元的因果作用，为理解安全对齐的内部机制提供新视角，并探索利用这些神经元增强模型安全性的应用。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将安全行为归因于稀疏的神经元子集，通过两步框架实现：
  1. **关联定位**：利用推理时激活对比（Inference-time Activation Contrasting）识别与安全行为相关的候选神经元。
  2. **因果验证**：通过动态激活补丁（Dynamic Activation Patching）评估这些神经元对模型安全输出的因果影响。

- **关键技术细节**：
  - **推理时激活对比**：对于同一提示，分别获取未对齐模型（M1，如SFT）和对齐模型（M2，如DPO）在生成序列上的神经元激活值，计算每个神经元的**变化分数（change score）**：根均方（RMS）差异的平均值。公式：  
    \( S_i^{(l)} = \sqrt{ \frac{ \sum_{w \in D} \sum_{j=|w|}^{|\bar{w}_1|-1} (a_i^{(l)}(M1;\bar{w}_1)[j] - a_i^{(l)}(M2;\bar{w}_1)[j])^2 }{ \sum_w |w_1| } } \)
    取分数最高的约5%神经元作为候选。
  - **动态激活补丁**：在解码过程中，逐一缓存M2目标神经元的激活，然后将其替换到M1对应神经元中，保持其他神经元不变，生成完整响应。定义因果效应 \( C = \frac{\mathbb{E}[F(\tilde{w}_1) - F(\bar{w}_1)]}{\mathbb{E}[F(\bar{w}_2) - F(\bar{w}_1)]} \)，其中F为安全评分（如cost模型得分）。C接近1表示该组神经元能完全解释安全对齐效果。

- **训练设置**：采用参数高效微调方法(IA)³进行DPO对齐，仅调整MLP层的缩放因子，保证神经元功能不变。

## 3. 实验设计：使用的数据集/场景、benchmark、对比方法

- **数据集**：
  - **训练**：SFT使用ShareGPT；DPO使用HH-RLHF-Harmless。
  - **识别神经元**：HH-RLHF-Harmless（计算change score）。
  - **安全评估（红队基准）**：Beavertails、RedTeam、HarmBench、JailBreakLLMs（共4个）。
  - **通用能力评估**：Wikitext-2（困惑度）、MMLU、GSM8K、BBH、TruthfulQA。
  - **偏好神经元分析**：额外使用RewardBench-Safety、HH-helpful、SHP、H4SE、IEFeedback等。

- **模型**：Llama2-7B、Mistral-7B、Gemma-7B、Qwen2.5-3B（共4种）。

- **对比方法**：
  - **基线**：随机神经元（相同层分布）、基于剪枝的方法（Wei et al. 2024，使用Wanda分数）、基于残差贡献的方法（SN-Tune, Zhao et al. 2025）。
  - **消融**：不同比较模型对（Base vs DPO, SFT vs DPO）、不同token位置、不同提示数据集。

- **评估指标**：安全评分使用预训练成本模型beaver-7b-v1.0-cost（越低越安全），并验证其与GPT-4评分的强相关性（-0.77）。

## 4. 资源与算力

- 论文明确说明实验在 **NVIDIA A100-SXM4-80GB GPU** 上运行，总计算量约 **1,000 GPU hours**。
- 未提及具体GPU数量，但根据工作量可推测使用多卡并行。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 安全神经元因果效应实验：在4个模型×2种源模型（Base/SFT）×5种神经元比例（0~5%）×5种随机种子（误差线），并重复验证。
  - 迁移性实验：在4个红队基准+5个通用基准上评估效果。
  - 鲁棒性实验：5种不同随机种子训练，计算重叠和相关系数。
  - 对齐税分析：7种偏好数据集识别偏好神经元→斯皮尔曼相关矩阵；交叉补丁实验（安全→有用、有用→安全）。
  - 安全神经元的应用：训练分类器进行5折交叉验证（5个数据集）。
  - 消融实验：比较不同比较模型、不同token位置、不同提示数据集。

- **充分性与公平性**：
  - 实验覆盖多种模型架构、多种红队基准和通用能力基准。
  - 对比了两种现有基线方法（剪枝、SN-Tune），并说明其在本验证设置中效果不佳。
  - 报告了95%置信区间和p值（1.15e-6至1.67e-18），统计显著性充分。
  - 消融实验完整，验证了方法中各设计选择的合理性。

## 6. 论文的主要结论与发现

1. **安全神经元稀疏且因果有效**：约5%的安全神经元，通过动态激活补丁可恢复超过90%的安全性能（甚至超过全比对模型），随机神经元效果极差。
2. **可迁移性**：在多个红队基准上均显著提升安全性，通用能力仅轻微下降（<0.05）。
3. **鲁棒性**：不同随机种子训练的安全神经元重叠率>0.95，说明机制稳定。
4. **对齐税的解释**：安全神经元与有用性神经元高度重叠（Spearman相关系数>0.8），但需要不同的激活模式。交叉补丁降低对方性能，证实竞争关系。
5. **应用**：利用安全神经元激活训练轻量分类器，可在生成前预测有害输出，平均准确率76.2%，能进一步提升未对齐和对齐模型的安全性。

## 7. 优点

- **新颖性**：首次从神经元粒度系统研究安全对齐的因果机制，提出激活对比+动态补丁的两阶段框架，克服了传统MI方法无法处理长输出开放任务的限制。
- **方法严谨**：将关联定位与因果验证结合，避免“Hydra效应”干扰（即消融可能引发补偿），采用增强而非消融的方式。
- **实验充分**：覆盖多种主流LLM、多种红队基准、多种对比方法，并进行鲁棒性、迁移性、消融等全面分析。
- **解释价值**：为对齐税提供直观的神经元级解释，且推导出可操作的差异。
- **实际应用**：展示安全神经元在防御中的直接用途，验证其工程价值。

## 8. 不足与局限

- **依赖已对齐模型**：动态激活补丁需要已对齐模型的激活作为源，无法从零训练得到安全激活（虽然可通过分类器部分缓解）。
- **仅采用PEFT方法**：仅使用(IA)³进行对齐，尚未验证全参数微调对安全神经元的影响。
- **未解释机制**：仅指出哪些神经元重要，未解释它们如何执行拒绝或安全行为（文末提到是未来工作）。
- **数据集偏差**：训练和评估主要基于HH-RLHF和Beavertails，可能存在领域偏差，红队基准集覆盖有限。
- **计算开销**：动态激活补丁在推理时需多次前向传播，效率较低（但分类器应用很轻量）。
- **未探索注意力头**：论文仅关注MLP神经元，虽提到注意力头（Zhou et al. 2025）是互补工作，但未对比。

（完）
