---
title: "Mechanistic Unlearning: Robust Knowledge Unlearning and Editing via Mechanistic Localization"
title_zh: 机械遗忘：通过机械定位实现鲁棒的知识遗忘与编辑
authors: "Phillip Huang Guo, Aaquib Syed, Abhay Sheshadri, Aidan Ewart, Gintare Karolina Dziugaite"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=92oBV5HAGl"
tags: ["query:model-edit"]
score: 9.0
evidence: 通过机械定位进行知识编辑和遗忘
tldr: 知识编辑和遗忘方法旨在修改或移除大模型中的不良知识，但鲁棒性不足。本文利用机械可解释性，定位与特定机制相关的模型组件（电路），从而更精确地进行编辑和遗忘。实验表明，通过不同定位方法训练的模型在编辑鲁棒性上存在显著差异，基于机制定位的方法效果更优。该工作为知识编辑提供了一种更稳健的框架，对提升模型安全具有直接价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1652, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 788, \"height\": 1168, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1559, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 839, \"height\": 1060, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 840, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1242, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 845, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 720, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 717, \"height\": 572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 721, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 541, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 527, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 533, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1616, \"height\": 1238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 931, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 931, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 933, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 930, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 932, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 931, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1598, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1415, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1607, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1584, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1604, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 713, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 710, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 711, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 709, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1742, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1741, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1739, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1738, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1734, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1733, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1744, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1744, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1740, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1737, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1739, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1739, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1737, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1733, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1731, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-047.webp\", \"caption\": \"\", \"page\": 0, \"index\": 47, \"width\": 1729, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-048.webp\", \"caption\": \"\", \"page\": 0, \"index\": 48, \"width\": 1731, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-049.webp\", \"caption\": \"\", \"page\": 0, \"index\": 49, \"width\": 1738, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-050.webp\", \"caption\": \"\", \"page\": 0, \"index\": 50, \"width\": 1739, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-051.webp\", \"caption\": \"\", \"page\": 0, \"index\": 51, \"width\": 1740, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-92obv5hagl/fig-052.webp\", \"caption\": \"\", \"page\": 0, \"index\": 52, \"width\": 1739, \"height\": 557, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1188, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1159, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1310, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1272, \"height\": 779, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1371, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-92obv5hagl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1372, \"height\": 524, \"label\": \"Table\"}]"
motivation: 现有知识编辑和遗忘方法精度不足，容易影响模型通用性能。
method: 利用机械可解释性定位特定能力对应的神经电路，仅编辑相关组件。
result: 基于机制定位的编辑方法在鲁棒性上显著优于其他定位方法。
conclusion: 机械定位为知识编辑提供了更精确且鲁棒的实现途径。
---

## Abstract
Methods for knowledge editing and unlearning in large language models seek to edit or remove undesirable knowledge or capabilities without compromising general language modeling performance. This work investigates how mechanistic interpretability---which, in part, aims to identify model components (circuits) associated to specific interpretable mechanisms that make up a model capability---can improve the precision and effectiveness of editing and unlearning. We find a stark difference in unlearning and edit robustness when training components localized by different methods. We highlight an important distinction between methods that localize components based primarily on preserving outputs, and those finding high level mechanisms with predictable intermediate states. In particular, localizing edits/unlearning to components associated with the *lookup-table mechanism* for factual recall 1) leads to more robust edits/unlearning across different input/output formats, and 2) resists attempts to relearn the unwanted information, while also reducing unintended side effects compared to baselines, on both a sports facts dataset and the CounterFact dataset across multiple models.
We also find that certain localized edits disrupt the latent knowledge in the model more than any other baselines, making unlearning more robust to various attacks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：大型语言模型（LLMs）在训练中会学习到不良知识，如何选择性编辑或遗忘这些知识（事实编辑/机器遗忘）是确保模型准确性、公平性和可控性的关键挑战。现有方法常常影响模型其他通用能力，且编辑的鲁棒性不足——例如，轻微改变提示词仍可触发原答案，或者白盒访问下仍能提取原始信息。
- **研究动机**：最近有工作利用机械可解释性（mechanistic interpretability）来定位存储特定事实的组件（如Meng等人的因果追踪），但这些基于输出追踪（Output-Tracing, OT）的定位方法受到质疑（Hase等人2023认为定位对编辑无帮助）。本文旨在深入探索哪种定位方式能带来更鲁棒的编辑/遗忘，并提出**机械遗忘（Mechanistic Unlearning）**概念。
- **整体含义**：发现不同定位方法导致编辑鲁棒性差异显著。基于事实查找机制（Fact Lookup, FLU）的定位——关注具有可预测中间状态的高级机制——比仅基于输出影响的OT定位方法在编辑鲁棒性、抗重学习能力和副作用控制上均更优。核心洞察是：OT方法倾向于修改属性提取机制（attribute extraction），而FLU方法修改知识源头（事实查找机制），从而更彻底地移除潜在知识。

## 2. 方法论：核心思想、关键技术细节、公式/算法流程

- **核心思想**：将模型视为有向无环图，识别出负责事实查找（fact lookup）的MLP层（通过探针实验或路径修补（path patching）定位），然后仅对这些组件进行参数更新。这与OT方法（如因果追踪、归因修补）形成对比，后者只关注组件对最终输出的直接影响。
- **关键技术细节**：
  - **定位方法**：
    - **FLU定位**：对于运动事实数据集，参考Nanda等人（2023）的方法：训练逻辑回归探针（probe）预测每层的隐藏状态对应的运动类别，选择探针准确率快速上升的层作为FLU层（即事实查找阶段MLP）。注意，仅包含MLP而不包含注意力头（尽管注意力头也有贡献，但为简单只选MLP）。
    - 对于CounterFact数据集，先用路径修补找出“属性提取机制”（直接作用于最终logits的注意力头和MLP），再通过修补MLP到这些提取机制的路径，找出对提取机制贡献最大的MLP作为FLU层。
    - **OT定位**：因果追踪（Causal Tracing）和归因修补（Attribution Patching），使用标准实现。
  - **参数更新方法**：局部微调（Localized Fine-Tuning）。仅更新定位到的组件参数。损失函数：
    \[
    L = \lambda_1 L_{\text{injection}} + \lambda_2 L_{\text{retain}} + \lambda_3 L_{\text{SFT}}
    \]
   其中 \(L_{\text{injection}}\) 是交叉熵损失（最大化新编辑答案的概率），\(L_{\text{retain}}\) 是保留事实的交叉熵，\(L_{\text{SFT}}\) 是Pile数据集的交叉熵（保持语言建模能力）。所有定位方法都使用相同的参数更新方法，仅改变定位的组件。
  - **另外使用权重掩码（weight masking）**：训练可微分二进制掩码，控制编辑大小，用于分析不同定位修改的机制比例。
- **算法流程**：对于每个编辑任务，首先根据定位方法得到组件集合 \(C_\tau\)，然后在该集合上运行梯度下降优化上述损失函数，更新参数（或掩码）。所有方法标准化了可训练参数数量。

## 3. 实验设计

- **数据集与场景**：
  - **Sports Facts**（Nanda等人2023）：1567名运动员与三种运动（篮球、棒球、足球）关系。包括三个任务：
    - **Sports-Athlete-Editing**：编辑16或64个随机运动员的关联，改为错误运动。
    - **Full-Sports-Editing**：遗忘某一个运动的所有运动员（如所有篮球运动员），改为高尔夫。
    - **Sports-Unlearning**：类似遗忘任务，但使用 \(L_{\text{forget}} = \log(1-p)\) 作为遗忘损失。
  - **CounterFact**（Meng等人2023）：过滤后得到模型正确概率高于50%的事实。编辑16或64个事实，替换为假目标。还设计了**Sequential-CounterFact-Editing**（顺序编辑64个事实，每次16个）。
- **评估指标**：
  - **标准提示评估**：遗忘准确性（forget accuracy）、编辑准确性（edit accuracy）、保持准确性（maintain accuracy）。
  - **鲁棒性评估**：多选题格式（MCQ，4选1）；对CounterFact还有同义改写（Paraphrase）和邻域事实（Neighborhood）评估；以及MMLU通用能力指标。
  - **对抗重学习评估**：将遗忘集分为两半，用一半重新训练（LoRA rank-512），评估另一半的准确性，检验是否可恢复知识。
  - **潜在知识分析**：训练探针分类器，从中间层激活预测正确运动，观察遗忘集上的预测变化。
  - **参数效率分析**：权重掩码控制编辑大小，比较不同定位的效果。
- **对比方法**：FLU、因果追踪（CT）、因果追踪仅MLP（CT MLPs）、归因修补（AP）、归因修补仅MLP（AP MLPs）、随机MLP、随机组件、所有MLP、无定位（全模型）。主要文本聚焦FLU、CT、无定位。
- **模型**：Gemma-7B、Gemma-2-9B、Llama-3-8B。所有实验重复多次并取平均（如平均三个模型、平均不同忘记集大小和不同运动类别）。

## 4. 资源与算力

论文中**未明确说明**训练使用的GPU型号、数量及总训练时长。仅提及：
- 使用AdamW优化器，8位优化器（对Gemma-2-9B因内存限制）。
- 部分实验（如超参数搜索）在多个学习率和损失系数上进行。
- 未提供具体计算量估计。因此无法量化算力消耗。

## 5. 实验数量与充分性

- **实验数量**：包含多个数据集（2个）、多个任务（近5个变种）、3个模型、多种定位方法（5种以上）、多种评估（标准提示、MCQ、重学习、探针分析、参数掩码）。并且进行了超参数扫描（学习率和注入损失系数）。附录中还包含软提示攻击和其他消融。
- **充分性与公平性**：
  - 充分：覆盖了多种鲁棒性评估（提示变化、重学习、探针）和计算效率分析（权重掩码）。在不同模型和数据集上一致地支持结论。
  - 公平：控制参数数量（使各定位方法可训练参数数一致）；使用相同微调超参数（仅对不同定位单独优化学习率和损失系数，且优化标准避免使用鲁棒性指标，防止数据泄漏）；多次平均减少随机性。
  - 但不足：重学习实验仅在Sports-Athlete-Editing上有效（其他任务太容易/太难重学），因此结论的一般性受限。此外，仅使用白盒设置（全参数微调/掩码），未与其他知识编辑方法（如Meng等人的ROME、MEMIT）直接比较（而是将定位作为变量，微调作为统一更新方法）。这削弱了与现有编辑方法直接竞争的说服力。

## 6. 主要结论与发现

- **FLU定位显著优于OT定位和基线**：在多个任务和模型上，FLU定位的编辑在多选题和同义改写格式下更鲁棒，遗忘准确性更低，编辑准确性更高。
- **FLU更抗重学习**：在Sports-Athlete-Editing中，FLU编辑后重学习仅恢复约20%的遗忘准确性，而OT方法恢复约63%。
- **FLU修改了潜在知识**：探针分析显示，FLU编辑后模型内部表示中原始知识消失，编辑答案出现；而OT方法仍保留大量原始知识在早期层。
- **FLU更参数高效**：在权重掩码实验中，FLU用更少参数实现更好鲁棒性。
- **OT方法倾向于修改属性提取机制而非事实查找机制**：机制权重分析（附录A.5）证明OT定位主要修改提取头/MLP，而FLU仅修改事实查找MLP。
- **FLU可扩展**：在Gemma-7B上编辑1000个CounterFact事实，FLU仍保持高MCQ编辑准确性，而基线降低至随机。

## 7. 优点

- **清晰的机械可解释性驱动**：利用对事实回忆机制的深入理解（Nanda等人+Geva等人）来设计定位，而非仅依赖输出相关性。这提供了更稳健的编辑理由。
- **全面的鲁棒性评估**：不仅检查标准提示，还包括多选题、同义改写、邻域事实、对抗重学习、潜在知识探针、权重掩码分析，评估维度丰富。
- **跨模型、跨数据集的验证**：在3个不同规模/架构的模型和2个不同性质数据集上系统验证，结论具有一般性。
- **控制参数数量**：公平比较不同定位方法的编辑容量。
- **可操作性**：提供了自动化FLU定位的方法（对CounterFact用标准差阈值），并展示了扩展到1000个事实的可行性。

## 8. 不足与局限

- **重学习评估有限**：对抗重学习仅在Sports-Athlete-Editing上有效，其他任务（Full-Sports-Editing、CounterFact）或太容易或太难重学，削弱了鲁棒性结论的普适性。
- **缺乏与现有编辑方法的直接比较**：本文使用局部微调作为统一编辑方法，没有与ROME、MEMIT等先进知识编辑方法对比。因此无法评估FLU定位结合其他更新方式的效果，也无法判断FLU是否优于现有全模型编辑方法。
- **手工定位依赖人工分析**：FLU定位基于手动发现的事实查找机制（早期MLP层），对于其他类型知识可能不适用；需要对新任务重新进行机械分析。虽然提供了自动化方法，但精确度可能不如手工。
- **仅考虑MLP**：文章明确排除了注意力头，尽管分析显示注意力头也参与事实查找。这可能导致未充分利用模型结构。
- **计算开销**：FLU定位需要探针训练或路径修补（对CounterFact），这比OT方法（单次前向传播）更耗时。扩展性论文虽提供自动化，但未比较定位的计算成本。
- **指标片面性**：主要依赖准确性指标，未检查生成质量（如困惑度、多样性）；MMLU仅作为粗略的通用能力代理。
- **未讨论安全场景**：虽然动机提及安全，但实验限于体育事实和一般事实，未涉及有害/敏感知识的遗忘。应用推广需谨慎。
- **未考虑后门或对抗提取**：仅考虑重学习、提示变化、软提示，未测试白盒对抗提取（如梯度攻击、提示注入等），鲁棒性评估仍有局限。

（完）
