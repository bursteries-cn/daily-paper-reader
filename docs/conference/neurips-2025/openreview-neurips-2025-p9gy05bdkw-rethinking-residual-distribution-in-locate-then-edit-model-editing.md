---
title: Rethinking Residual Distribution in Locate-then-Edit Model Editing
title_zh: 重新思考定位-编辑模型编辑中的残差分布
authors: "Xiaopeng Li, Shangwen Wang, Shasha Li, Shezheng Song, Bin Ji, Ma Jun, Jie Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=P9gY05BDkW"
tags: ["query:model-edit"]
score: 9.0
evidence: 直接研究定位-编辑范式的残差分布机制
tldr: 针对大模型编辑中定位-编辑方法的核心机制——残差分布，发现其引入权重偏移误差，损害编辑精度。通过理论和实证分析，展示了误差随分布距离、批大小和编辑序列长度增加而加剧，最终导致编辑失败。该工作揭示了现有方法的根本缺陷，为改进编辑精度提供了重要指导。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 763, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 607, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 588, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 548, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 511, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1088, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1433, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1428, \"height\": 954, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1139, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1431, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1432, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1421, \"height\": 940, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1440, \"height\": 1507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p9gy05bdkw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1444, \"height\": 1484, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 729, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 1129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 918, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 1326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1457, \"height\": 1320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1273, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-p9gy05bdkw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1458, \"height\": 785, \"label\": \"Table\"}]"
motivation: 现有定位-编辑方法中残差分布机制存在权重偏移误差，影响编辑精度，本文旨在分析并揭示该问题。
method: 通过理论推导和实验分析，研究残差分布误差与分布距离、批大小、编辑序列长度等的关系。
result: 发现残差分布引入的权重偏移误差随编辑规模增大而显著增加，最终导致编辑失败。
conclusion: 揭示了残差分布的固有缺陷，为未来改进定位-编辑方法提供了关键洞见。
---

## Abstract
Model editing enables targeted updates to the knowledge of large language models (LLMs) with minimal retraining. Among existing approaches, locate-then-edit methods constitute a prominent paradigm: they first identify critical layers, then compute residuals at the final critical layer based on the target edit, and finally apply least-squares-based multi-layer updates via $\textbf{residual distribution}$. While empirically effective, we identify a counterintuitive failure mode: residual distribution, a core mechanism in these methods, introduces weight shift errors that undermine editing precision. Through theoretical and empirical analysis, we show that such errors increase with the distribution distance, batch size, and edit sequence length, ultimately leading to inaccurate or suboptimal edits. To address this, we propose the $\textbf{B}$oundary $\textbf{L}$ayer $\textbf{U}$pdat$\textbf{E (BLUE)}$ strategy to enhance locate-then-edit methods. Sequential batch editing experiments on three LLMs and two datasets demonstrate that BLUE not only delivers an average performance improvement of 35.59\%, significantly advancing the state of the art in model editing, but also enhances the preservation of LLMs' general capabilities. Our code is available at https://github.com/xpq-tech/BLUE.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大语言模型（LLM）的参数化知识无法实时更新，重新训练成本极高。模型编辑技术旨在高效地修正或更新LLM中的错误/过时知识，其中“定位-编辑”（locate-then-edit）方法是一类主流范式。
- **核心问题**：该范式中的核心机制——**残差分布（residual distribution）**——被广泛用于将最后一个关键层计算出的残差均匀分配到多个关键层，并通过最小二乘法进行多层权重更新。本文通过理论和实证发现，**残差分布实际上引入了权重偏移误差，反而损害了编辑精度**。误差会随分布距离、编辑批大小和顺序编辑次数增加而加剧，导致编辑不准确或次优。
- **整体含义**：本文揭示了一个反直觉的失败模式，质疑了现有定位-编辑方法的核心设计，并提出了改进策略（BLUE），从而显著提升编辑性能并更好地保留LLM的通用能力。

## 2. 论文提出的方法论

- **核心思想**：放弃残差分布，仅更新关键层的**边界层**（第一层和最后一层），直接为这两个层分别计算残差并进行最小二乘更新。该方法称为**BLUE（Boundary Layer Update）**。
- **关键技术细节**：
  1. 沿用原方法的因果追踪确定关键层集合 L。
  2. 对最后一个关键层（L）计算残差 R_L（通过优化目标函数使新对象概率最大）。
  3. **不再将 R_L 均匀分配到其他层**，而是：
     - 对第一个关键层，直接计算其残差（同样通过优化）；
     - 对最后一个关键层，使用其原始计算的残差；
     - 只更新这两个层的权重（采用最小二乘闭式解）。
  4. 扩展到顺序批量编辑时，类似地使用缓存的历史键矩阵 K_p 参与计算。
- **公式与算法流程**（文字说明）：
  - 原方法：R_l = R_L / (L - l + 1) (均匀分布) → Δ_l = R_l K_l^T (K_0 K_0^T + K_1 K_1^T)^{-1}
  - BLUE：对 l = first_layer 和 l = last_layer，分别计算残差 R_l（不共享），然后各自计算 Δ_l（公式相同，但残差是独立优化的）。
- **理论支撑**：推导了权重偏移误差的上界，证明其随分布距离、批大小和顺序编辑次数增大而增大。实验证明直接计算的残差贡献分数远高于分布残差。

## 3. 实验设计

- **数据集**：
  - **CounterFact**（经典事实编辑基准）
  - **zsRE**（零样本关系抽取数据集）
  - **UnKEBench**（用于长文本编辑评估）
  - **GLUE**子任务（SST、MRPC、MMLU、RTE、CoLA、NLI）用于评估通用能力保留。
- **场景**：
  - 顺序批量编辑（Sequential Batch Editing）：2000 个样本，每批 100 个，依次编辑。
  - 批量编辑（Batch Editing）：10,000 个样本一次性编辑。
  - 长文本编辑（Long-form Editing）：使用 UnKEBench。
- **基准模型与对比方法**：
  - 编辑受测LLM：Llama3-8B-Instruct、GPT-J (6B)、GPT2-XL；额外验证 Llama2-13B。
  - 对比的定位-编辑方法：MEMIT、PRUNE、RECT、AlphaEdit（以及带平方根残差分布的PMET在消融中）。
  - **BLUE增强版本**：对上述每种方法分别实施BLUE，与原始版本对比。
- **评估指标**：Efficacy、Generalization、Specificity、Fluency、Consistency。还使用 t-SNE 可视化隐藏状态偏移。

## 4. 资源与算力

- 文中说明：**所有实验在 A800 GPU 上完成**，但未明确给出具体 GPU 数量、总训练时长或算力消耗细节。
- 在附录 D 中提及：“All our experiments are conducted on A800 GPUs”，并介绍了超参数设置（如 AlphaEdit 的 α 值等），但缺乏资源总量统计。

## 5. 实验数量与充分性

- **实验数量**：
  - 顺序批量编辑：3 个 LLM × 2 个数据集 × 5 种方法（MEMIT, PRUNE, RECT, AlphaEdit 及其 BLUE 版本）= 60 组主要结果；表 2 显示 96 个指标比较（86 个提升）。
  - 批量编辑：类似规模的 10,000 批次实验（表 6）。
  - 消融实验：关于编辑层选择（图 8），验证边界层最优。
  - 通用能力保留实验：6 个 GLUE 任务，每 500 步评估一次，共 3000 次顺序编辑。
  - 隐藏状态偏移可视化：3 个模型（图 7, 10, 11）。
  - 长文本编辑实验：在 UnKEBench 上对比 MEMIT/AlphaEdit（表 3）。
  - 理论验证实验：图 5、13、14 展示误差随规模变化趋势。
- **充分性与公平性**：
  - 实验覆盖了多个主流LLM、两个标准编辑数据集、多个基线方法以及顺序/批量/长文本等多种场景。
  - 报告了误差棒（96% CI 或标准差），确保统计可靠性。
  - 消融实验和理论验证支持主要结论。
  - 所有基线采用原论文最优设置，BLUE 增强时仅改变编辑层选择，其余超参数一致（AlphaEdit 的 α 值调整有说明），实验设计较为公平。

## 6. 论文的主要结论与发现

1. **残差分布并非最优**：分布残差在非末层的贡献分数远低于直接计算的残差，余弦相似度随距离下降，导致编辑成效和泛化能力显著差于直接计算。
2. **理论界定了误差增长规律**：权重偏移误差上界随分布距离、批大小和顺序编辑次数增加而增大。
3. **BLUE 提升显著**：在 12 个顺序批量编辑实验中，平均提升 35.59%；86/96 个指标得到改善；在批量编辑和长文本编辑中同样有效。
4. **通用能力保留更好**：在 GLUE 任务上，BLUE 增强后的方法在多次顺序编辑后仍能保持较高 F1 分数，而原始方法性能严重下降。
5. **缓解隐藏状态偏移**：t-SNE 可视化显示 BLUE 增强方法引起的隐藏状态偏移更小。
6. **效率更优**：大多数情况下，BLUE 降低峰值内存和平均编辑时间。

## 7. 优点

- **发现问题本质**：首次理论并实证揭示残差分布带来的权重误差，挑战了定位-编辑范式的核心假设。
- **方法简洁有效**：BLUE 仅修改编辑层选择（从多层均匀更新改为两层直接计算），无需改变优化目标或网络结构，即可显著提升性能，易于集成到现有方法中。
- **全面评估**：涵盖多样性评估维度（编辑成功、泛化、特异性、流畅性、一致性、通用能力、隐藏状态偏移、效率、长文本），验证充分。
- **开源代码**：提供 GitHub 仓库，促进可复现性。

## 8. 不足与局限

- **适用范围有限**：BLUE 仅适用于采用均匀残差分布的定位-编辑方法（如 MEMIT、RECT、PRUNE、AlphaEdit）。对于使用平方根分布的方法（如 PMET），提升有限或效果不佳（附录 K 显示部分场景提升有限）。
- **编辑逻辑知识未验证**：论文承认 BLUE 在编辑推理知识（如 MQuAKE 数据集）上的效果尚未验证（见附录 L）。
- **特异性可能下降**：在批量编辑实验中，BLUE 增强方法在提升 efficacy 和 generalization 的同时，特异性有时略降（表 6 注释），说明可能对其他知识产生更多干扰。
- **资源算力细节不完整**：未提供 GPU 数量、总耗时等具体算力信息，影响可复现性细节。
- **仅限 FFN 更新**：BLUE 保持原方法的单层 FFN 权重更新机制，未探索结合自注意力等其他模块的编辑，可能限制上限。

（完）
