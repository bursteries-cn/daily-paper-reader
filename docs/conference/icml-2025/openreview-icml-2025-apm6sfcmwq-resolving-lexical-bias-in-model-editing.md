---
title: Resolving Lexical Bias in Model Editing
title_zh: 解决模型编辑中的词汇偏差
authors: "Hammad Rizwan, Domenic Rosati, Ga Wu, Hassan Sajjad"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=aPm6SfcMWQ"
tags: ["query:model-edit"]
score: 9.0
evidence: 解决基于适配器的模型编辑中的词汇偏差
tldr: 当前基于适配器的模型编辑方法受词汇偏差影响，会将编辑应用到无关提示。本文通过学习解耦表示空间，使编辑仅触发于语义相关提示，避免词汇重叠导致的误触发。实验证明，该方法显著降低了错误应用率，提高了编辑的精确性，对模型编辑的实际部署具有重要意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1752, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1765, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1759, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 885, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1415, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1223, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-apm6sfcmwq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1224, \"height\": 661, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1780, \"height\": 922, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 718, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 1756, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1608, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1606, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1776, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1777, \"height\": 1267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1775, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-apm6sfcmwq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1761, \"height\": 1497, \"label\": \"Table\"}]"
motivation: 现有适配器方法因词汇偏差导致编辑误触发，需更精确的编辑定位。
method: 学习解耦表示空间，维持无关提示距离，保持相关提示邻近。
result: 在多个编辑场景下误触发率大幅降低，编辑精度提升。
conclusion: 解耦表示能有效消除词汇偏差，提升模型编辑的可靠性。
---

## Abstract
Model editing aims to modify the outputs of large language models after they are trained. Previous approaches have often involved direct alterations to model weights, which can result in model degradation. Recent techniques avoid making modifications to the model's weights by using an adapter that applies edits to the model when triggered by semantic similarity in the representation space. We demonstrate that current adapter methods are *critically vulnerable* to strong lexical biases, leading to issues such as applying edits to irrelevant prompts with overlapping words. This paper presents a principled approach to learning a disentangled representation space that facilitates precise localization of edits by maintaining distance between irrelevant prompts while preserving proximity among paraphrases. In our empirical study, we show that our method (Projector Editor Networks for Model Editing - PENME) achieves state-of-the-art model editing results while being more computationally efficient during inference than previous methods and adaptable across different architectures.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：当前基于适配器（adapter）的模型编辑方法（如 GRACE、MELO）虽然避免了直接修改模型权重，但严重依赖表示空间中的距离函数来判断何时触发编辑。然而，这些表示空间存在**词汇偏差（lexical bias）**——即词汇重叠较多但语义无关的提示（irrelevant prompts）在表示空间中比语义相关的释义（paraphrases）更接近编辑提示，导致编辑被误触发到无关输入。
- **整体含义**：词汇偏差使得现有方法难以同时兼顾**泛化（对释义正确编辑）** 和**局部性（对无关提示不触发编辑）**，通常需要人工调整阈值来权衡，但效果有限。解决这一偏差对于提升模型编辑的精确性和可靠性至关重要。
- **研究意义**：该工作是首个系统性地指出并解决适配器模型编辑中词汇偏差问题的研究，为后续方法提供了新思路。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：通过对比学习训练一个**投影网络（projection network）**，将原始模型某一层的表示空间映射到一个新的解耦空间，在该空间中：
  - 编辑提示（edit）与其释义（paraphrase）保持靠近；
  - 编辑提示与无关提示（irrelevant prompts）以及其他编辑（inter-edit）被推远；
  - 从而在码本检索时，只有语义真正相关的输入才会触发编辑。
- **关键技术细节**：
  - **投影网络**：2层MLP + ReLU + BatchNorm，输入输出维度均为模型隐藏层维度（d）。仅挂载在模型的某一层（实验选择第二层，因其词汇偏差最小）。
  - **对比损失函数**（公式1）：
    \[
    L(\vec{x}_i, \vec{z}) = (1-t)\frac{1}{2}\|\vec{x}_i - \vec{z}\|_2^2 + t\frac{1}{2}\left[\max(0, m - \|\vec{x}_i - \vec{z}\|_2)\right]^2
    \]
    - \(t=0\) 时为正样本对（编辑-释义），拉近距离；
    - \(t=1\) 时为负样本对（编辑-无关提示 或 编辑-其他编辑），推远距离至少 \(m\)（margin=40）。
  - **编解码簿（Key-Value Codebook）**：存储投影后的编辑表示作为键（key），值（value）包含编辑输出信息和动态阈值 \(\delta\)。
  - **动态阈值**（公式3）：\(v_{\delta_i} = \max(\|\vec{x}_i - \vec{p}_{ij}\|_2) + \tau\)，其中 \(\tau\) 通过网格搜索调整（0.05~0.20），以适应未见释义的分布偏移。
  - **推理流程**：输入经过模型 → 提取指定层表示 → 投影网络 → 与码本中所有键计算欧氏距离；若最小距离小于对应阈值，则返回编辑输出，否则返回原始模型输出。
- **算法流程**（见附录Algorithm 1、2）：包括训练数据的构建（正负采样、编辑间负样本）、投影网络训练、码本构建与检索。

## 3. 实验设计：数据集、场景、基准与对比方法
- **数据集**：
  - **Counterfact**（Meng et al., 2022）：包含编辑、释义、以及具有高词汇重叠的无关提示（挑战性强）。
  - **zsRE**（Levy et al., 2017）：包含编辑、释义、无关提示来自NQ（词汇重叠低）。
- **评测指标**：
  - **Edit Success (ES)**：编辑后的模型对编辑提示输出正确目标。
  - **Locality (Loc)**：对无关提示保持原模型输出。
  - **Paraphrase Generalization (Para)**：对释义也输出编辑后的正确目标。
  - **Score**：三者均值。
- **模型**：T5-small、GPT2-XL、Llama-2-7b。
- **对比方法**：
  - 基于适配器：GRACE、MELO。
  - 基于权重修改：MEMIT。
  - 基于记忆缓存：SERAC。
  - 简单微调（FT）。
- **实验场景**：
  - **批量编辑**：2000个编辑（Counterfact）/ 1000个编辑（zsRE）。
  - **流式编辑（stream）**：使用冻结投影网络，每次添加一个编辑到码本，零样本泛化。
  - **缩放实验**：编辑数量从1000到5000。
  - **下游任务**：情感分类（DAiR-Emotions）、摘要（CNN/DailyMail）、自然语言推理（RTE）。
  - **长文本生成**：结合IKE检索式提示生成。
  - **词汇偏差分析**：提取不同层表示，比较编辑-释义距离与编辑-无关提示距离。

## 4. 资源与算力
- **投影网络训练**：NVIDIA P100 GPU（16GB VRAM），训练200 epochs，batch size 8192，学习率 \(1\times10^{-2}\)。
- **更大模型推理/基线方法**：需要使用NVIDIA A100 GPU（40GB 或 80GB VRAM）。
- **未明确说明**：投影网络的训练总时长（小时数）以及各基线方法的资源消耗对比未给出。

## 5. 实验数量与充分性
- **实验数量**：论文包含以下主要实验：
  - 词汇偏差分析（图4）：对3个模型的所有层进行统计。
  - 投影网络效果（图1）：比较投影前后无关提示比释义更近的样本比例。
  - 主结果表1：2个数据集 × 3个模型 × 7种方法（含PENME变体）。
  - 泛化-局部性权衡（图5）：改变 \(\tau\) 和 \(\phi\) 的消融。
  - 缩放编辑数量（图6）：1000~5000编辑范围。
  - 下游任务表2、长文本生成表3。
  - 附录中还包含层选择、阈值分析、PCA可视化、错误分析等。
- **充分性与公平性**：
  - **较充分**：涵盖了主要模型和数据集，对比了多个基线方法，并进行了消融和扩展实验。
  - **存在局限**：部分基线（如GRACE、MELO）的默认超参数可能未针对本文实验充分调优；SERAC在T5-small上的极低分数暗示了适配性问题；词汇偏差分析仅依赖ROUGE-1作为词汇重叠度量，可能不够全面；所有实验均在英文场景下进行。

## 6. 论文主要结论与发现
1. **词汇偏差普遍存在**：在多个模型的中层，大量（高达46% for T5-small）无关提示在表示空间中比释义更接近编辑提示，导致适配器方法误触发。
2. **投影网络有效解耦**：PENME将这一比例降至6.4%（T5-small）、2.8%（GPT2-XL）、0%（Llama-2-7b），实现了近乎完美的可分离性。
3. **编辑性能全面领先**：在Counterfact和zsRE上，PENME在编辑成功、泛化、局部性三项指标上均达到最优或接近最优，Score显著高于其他方法。
4. **推理效率高**：每个编辑只需一个码本条目，检索速度快（50编辑时0.024ms vs MELO 0.316ms）。
5. **流式编辑可行**：冻结投影网络后，零样本泛化仅小幅下降，支持持续编辑。
6. **下游任务影响极小**：编辑后模型的NLI、情感分类、摘要性能几乎不变，体现了良好的局部性。

## 7. 优点
- **问题洞察深刻**：首次明确指出并形式化适配器模型编辑中的词汇偏差漏洞。
- **方法简洁有效**：通过轻量级投影网络（2层MLP）和对比学习，以较低计算成本解决了核心问题。
- **卓越的泛化-局部性平衡**：无需手动调节每个编辑的阈值，通过动态阈值自动适配。
- **架构无关性**：可应用于不同模型（T5, GPT, Llama），且只依赖模型单层表示。
- **计算效率**：推理时只需一次前向+投影+距离检索，无模型权重复制或附加模型。
- **代码开源**：促进可复现性和后续研究。

## 8. 不足与局限
- **训练敏感**：对比学习的超参数（margin、学习率、批次大小）需要仔细调节。
- **阈值依赖**：虽然动态阈值逻辑合理，但参数 \(\tau\) 仍需针对不同模型通过网格搜索确定，缺乏自适应机制。
- **评估覆盖有限**：
  - 仅使用英文数据集（zsRE、Counterfact），未探索跨语言或多语场景。
  - 多跳编辑仅简要提及，未进行系统实验。
  - 长文本生成采用IKE检索式方法，可能引入额外幻觉。
  - 未评估对模型安全性的潜在影响（如恶意编辑）。
- **基线调优不彻底**：部分基线（如SERAC、MEMIT）在特定模型上表现异常，可能存在适配问题。
- **词汇重叠度量单一**：仅使用ROUGE-1作为词汇偏差的代理，未考虑语义重叠、词序等因素。
- **对比方法范围**：未包含近年更多新方法（如WISE、PRUNE等），但论文发表时间（ICML 2025）可能为合理范围。

（完）
