---
title: "BalancEdit: Dynamically Balancing the Generality-Locality Trade-off in Multi-modal Model Editing"
title_zh: BalancEdit：多模态模型编辑中通用性与局部性的动态平衡
authors: "Dongliang Guo, Mengxuan Hu, Zihan Guan, Thomas Hartvigsen, Sheng Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JWtcAlXkMN"
tags: ["query:model-edit"]
score: 8.0
evidence: 多模态模型编辑中通用性与局部性的权衡
tldr: 现有模型编辑技术忽略不同事实的影响范围，导致通用性和局部性受损。BalancEdit通过动态平衡通用性与局部性，提出新的多模态编辑数据集OKEDIT，有效提升了多模态模型编辑的性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1616, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jwtcalxkmn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 500, \"height\": 416, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 851, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1577, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 850, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jwtcalxkmn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 769, \"height\": 156, \"label\": \"Table\"}]"
motivation: 不同事实在模型编辑中的影响范围不同，需要动态平衡通用性与局部性。
method: 提出BalancEdit方法，动态调节编辑的力度以平衡通用性和局部性，并构建OKEDIT数据集。
result: 在OKEDIT等数据集上，BalancEdit在保持局部性的同时提升了通用性。
conclusion: 该工作首次明确多模态编辑中的通用性-局部性权衡问题，并提供了有效解决方案。
---

## Abstract
Large multi-modal models inevitably decay over time as facts update and previously learned information becomes outdated. Traditional approaches such as fine-tuning are often impractical for updating these models due to their size and complexity. Instead, direct knowledge editing within the models presents a more viable solution. Current model editing techniques, however, typically overlook the unique influence ranges of different facts, leading to compromised model performance in terms of both generality and locality. To address this issue, we introduce the concept of the generality-locality trade-off in multi-modal model editing. We develop a new model editing dataset named OKEDIT, specifically designed to effectively evaluate this trade-off. Building on this foundation, we propose \textbf{BalancEdit}, a novel method for balanced model editing that dynamically achieves an optimal balance between generality and locality. BalancEdit utilizes a unique mechanism that generates both positive and negative samples for each fact to accurately determine its influence scope and incorporates these insights into the model's latent space using a discrete, localized codebook of edits, without modifying the underlying model weights. To our knowledge, this is the first approach explicitly addressing the generality-locality trade-off in multi-modal model editing. Our comprehensive results confirm the effectiveness of BalancEdit, demonstrating minimal trade-offs while maintaining robust editing capabilities. Our code and dataset are available at https://github.com/donglgcn/BalancEdit/tree/MMOKVQA.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大型多模态模型（LVLMs）在部署后因事实更新或知识过时而性能衰退。传统微调方法因模型规模大、成本高而不实用，直接知识编辑是更可行的方案。但现有编辑技术忽略了不同事实的独特影响范围（influence scope），导致通用性（generality，对相关输入输出正确）和局部性（locality，对无关输入输出不变）之间难以平衡，出现“过度泛化”或“过度局部化”的问题。
- **整体含义**：本文首次明确提出多模态模型编辑中的“通用性-局部性权衡”（generality-locality trade-off），并指出每个事实应有动态的影响范围，而非统一或固定范围。通过构建专门数据集OKEDIT和提出方法BalancEdit，旨在实现自动、动态的平衡，提升编辑质量。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
BalancEdit 不修改模型权重，而是在选定Transformer层中插入一个“BalancEdit模块”，该模块包含**离散代码本**（codebook），存储每个编辑的关键信息（key、转换函数、影响半径）。对每个新事实，自动生成正样本（同义改写文本）和负样本（纯黑图像）来确定影响半径，实现动态平衡。

### 关键技术细节
- **代码本结构**：每个条目包含三部分：
  - **Keys** (K)：来自第l-1层的平均嵌入，作为锚点。
  - **Transformations** (V)：微调后的层变换权重，用于输出新知识。
  - **Influence Radius** (E)：动态半径，由正负样本距离加权决定：
    \[
    \epsilon = (1 - \alpha) \cdot d(\text{Pos}, k) + \alpha \cdot d(\text{Neg}, k)
    \]
    其中 \(d\) 为距离函数（默认欧氏距离），\(\alpha\) 为可调超参数。
- **推理过程**：对于新输入，计算其嵌入与所有Key的距离，若最小距离小于对应半径，则应用存储的变换，否则保持原始层变换。
- **正负样本生成**：
  - 正样本：保持图像不变，用模型改写问题文本（rephrase）。
  - 负样本：使用纯黑图像 + 原问题（无语义信息），作为边界的代理。
- **编辑方式**：对变换层进行全微调（full fine-tuning），更新权重以学习新事实，同时保留原有模型权重不变。支持顺序编辑：若新事实与已有Key重叠，则从之前编辑的变换继续微调；若冲突则替换条目。

## 3. 实验设计

### 数据集
- **MMEDIT**：基于VQA-v2，2093个测试样本，图像由扩散模型生成，存在图像内容偏差问题。
- **OKEDIT**（新构建）：基于OKVQA，5046个测试样本，涵盖20+类别，每个编辑提供10个通用性样本和复杂语义的局部性样本，更严格评估权衡。

### 场景与benchmark
- 任务：视觉问答（VQA）中的知识编辑（如改变品牌名、物种名等）。

### 对比方法
- **FT**（微调）：仅微调同一层，固定其他层。
- **IKE**：基于上下文学习的检索增强编辑（适配多模态）。
- **MEND**：元学习预测权重更新，需大量训练数据。
- **GRACE**：内存增强的终身编辑，使用离散键值代码本。

### 评估指标
- **Acc**：编辑成功率（可靠性）
- **T-Gen**：文本通用性（改写问题）
- **I-Gen**：图像通用性（语义相似图像）
- **Loc**：局部性（无关图像/问题）
- **HM**：T-Gen、I-Gen、Loc的调和平均，度量权衡性能。

## 4. 资源与算力

论文明确说明：
- **GPU**：使用24GB NVIDIA RTX A5000、40GB A100、80GB A100等多种型号。
- **训练时长报告**：
  - FT：0小时预训练，单次编辑3.91秒。
  - IKE：12小时预训练索引，编辑0.38秒。
  - MEND：22小时预训练，编辑1.48秒。
  - GRACE：0小时预训练，编辑32.67秒。
  - **BalancEdit**：0小时预训练，编辑8.04秒，无需额外训练数据。
- 无明确说明总计算量（如卡时），但已体现出高效性。

## 5. 实验数量与充分性

- **主要实验**：在2个数据集×2个骨干模型（MiniGPT-4、BLIP-2 OPT）上对比4个基线，报告了Acc、T-Gen、I-Gen、Loc、HM指标（表3）。
- **顺序编辑实验**：50次顺序编辑（表4），评估记忆和冲突处理。
- **效率实验**：时间和数据成本对比（表5）。
- **消融实验**：
  - 超参数α的影响（图5，α从0.1到0.3）。
  - 不同距离函数（欧氏 vs 余弦，表6）。
  - 不同负锚点（黑 vs 白，表7）。
  - 随机负采样对比（表8）。
  - 不同编辑层（第30层与第31层，表9）。
  - 极端α值（0和1，表10）。
- **可解释性展示**：给出成功/失败案例的代码本解释（图4）。
- 实验覆盖了可靠性、通用性、局部性、多编辑、效率、可解释性，较为充分；消融实验较全面。但缺乏大规模多跳编辑、跨任务泛化等测试。总体客观公平。

## 6. 论文的主要结论与发现

- BalancEdit在所有数据集和骨干模型上实现100%编辑成功率，同时HM指标显著优于基线（如OKEDIT上比MEND高10%-20%）。
- 动态半径机制有效平衡通用性与局部性，α可调节权衡倾向。
- 无需额外训练数据，仅依赖单次编辑数据即可完成高效编辑。
- 顺序编辑能力良好，性能略有下降但优于无顺序编辑的基线。
- 可解释代码本提供编辑追溯和输出解释能力。

## 7. 优点

- **首次明确定义并解决**多模态模型编辑中的通用性-局部性权衡问题。
- **构建了更高质数据集**OKEDIT，克服MMEDIT图像偏差、样本量少、难度低等问题。
- **方法高效且无需预训练**，正负样本自动生成，适用于流式编辑。
- **动态半径机制**创新，利用语义相似性自然确定影响范围，无需外部知识。
- **与模型无关**，可即插即用，支持多种骨干模型（MiniGPT-4, BLIP-2）。
- **可解释性强**：代码本可检查、可回溯，推理时可输出影响来源。
- 实验设计全面，消融深入，对比公平。

## 8. 不足与局限

- **推理速度减慢**：因需相似性搜索，比原始模型慢。虽减少训练时间，但推理开销未优化，论文也承认是未来改进方向。
- **无法处理多跳编辑**：基于Key的相似性搜索难以捕获依赖新知识的复合查询（如“由SpaceX领导、前称Twitter的社交应用”），因新知识不在原嵌入空间。
- **数据集覆盖有限**：仅评估VQA任务中的知识编辑，未测试其他多模态任务（如图文生成、指代理解）。
- **局部性评估可能偏弱**：负样本仅用纯黑图像，可能无法覆盖所有无关变体（如类似但不同对象的图像），但作者通过白色图像实验显示鲁棒性。
- **α选择需调参**：不同模型、不同任务可能需要重新选择α，增加应用成本。
- **顺序编辑中代码本冲突处理**：虽设计丢弃策略，但未详细分析冲突导致的性能损失边界。

（完）
