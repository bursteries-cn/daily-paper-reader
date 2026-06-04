---
title: Learning Safety Constraints for Large Language Models
title_zh: 学习大型语言模型的安全约束
authors: "Xin Chen, Yarden As, Andreas Krause"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Ffpc7vx6qq"
tags: ["query:model-edit"]
score: 7.0
evidence: 表示空间中的几何安全约束用于大模型安全
tldr: 本文提出SaP方法，在语言模型表示空间中学习安全多面体，通过几何导向检测和修正不安全输出，无需修改权重即可实现安全约束。实验证明，SaP能有效检测不道德输入，同时保持模型原有能力。该方法为安全对齐编辑提供了一种无需重新训练的新途径，可应用于防止攻击等场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1722, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 779, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1637, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1770, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1584, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ffpc7vx6qq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1729, \"height\": 686, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1536, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 892, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1563, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 925, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1606, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 929, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 888, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 925, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1586, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 638, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 634, \"height\": 770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 639, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1551, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1659, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1602, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ffpc7vx6qq/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1748, \"height\": 711, \"label\": \"Table\"}]"
motivation: 现有安全方法常需修改权重或影响模型能力，需一种后置的安全约束方法。
method: 学习表示空间中的安全与不安全区域的多面体，通过几何导向修正输出。
result: 在多个LLM上有效检测不道德输入，安全性与能力保持均优。
conclusion: 几何安全约束方法可在不损害模型性能的前提下增强安全性，适用于安全对齐编辑。
---

## Abstract
Large language models (LLMs) have emerged as powerful tools but pose significant safety risks through harmful outputs and vulnerability to adversarial attacks. We propose SaP–short for Safety Polytope–a geometric approach to LLM safety, that learns and enforces multiple safety constraints directly in the model's representation space. We develop a framework that identifies safe and unsafe regions via the polytope's facets, enabling both detection and correction of unsafe outputs through geometric steering. Unlike existing approaches that modify model weights, SaP operates post-hoc in the representation space, preserving model capabilities while enforcing safety constraints. Experiments across multiple LLMs demonstrate that our method can effectively detect unethical inputs, reduce adversarial attack success rates while maintaining performance on standard tasks, thus highlighting the importance of having an explicit geometric model for safety. Analysis of the learned polytope facets reveals emergence of specialization in detecting different semantic notions of safety, providing interpretable insights into how safety is captured in LLMs' representation space.

---

## 论文详细总结（自动生成）

## 学习大型语言模型的安全约束（Learning Safety Constraints for Large Language Models）

### 1. 论文的核心问题与整体含义

- **研究动机**：大语言模型（LLM）在广泛部署中面临严重的安全风险，包括生成有害内容、易受对抗性攻击等。现有安全方法（如RLHF、提示工程、训练时约束）存在局限性：模型可能“玩弄”奖励函数而非真正变安全，人类偏好标注的噪声导致意外行为，且多数方法需要重新训练模型、缺乏后置控制机制和可解释性。
- **核心问题**：如何在**不修改模型权重**的前提下，在LLM的**表示空间**中显式学习和强制安全约束，同时保持模型原有能力，并提供可解释的安全决策依据。
- **整体含义**：本文提出将LLM安全问题建模为几何约束学习问题，通过在多面体（polytope）中刻画安全/不安全区域，实现后置的、无需微调的安全控制，为LLM安全提供了一种新的几何范式。

### 2. 论文提出的方法论

- **核心思想**：受约束马尔可夫决策过程（CMDP）中约束学习理论启发，将LLM的安全需求视为表示空间中的线性约束。这些约束构成一个凸多面体（polytope）——即安全集，每个面（facet）对应一个独立的安全语义概念。通过从标注数据（安全/不安全二元标签）中学习多面体的参数，可以实现安全输出的检测和修正。
- **关键技术细节**：
  1. **特征提取**：从预训练LLM的中间层提取隐藏状态 \( h \in \mathbb{R}^{d_h} \)（通常取句子最后一个token的表示）。
  2. **概念编码器（Concept Encoder, CE）**：在隐藏状态上添加一个线性层+ReLU非线性变换，得到稀疏特征 \( \tilde{f} = E_C(\bar{\pi}_l(x)) \in \mathbb{R}^d \)，并引入L1稀疏正则化以缓解多语义性（polysemanticity）。
  3. **多面体学习**：采用凸多面体机（Convex Polytope Machine, CPM）方法，将多面体学习转化为分类问题。损失函数包含：
     - 安全示例的间隔惩罚（鼓励特征在安全侧）
     - 不安全示例的间隔惩罚（鼓励违反某个面的约束）
     - 稀疏正则项和权重范数正则项
     通过梯度下降优化得到面参数 \( \phi \in \mathbb{R}^{d \times K} \) 和阈值 \( \tilde{\xi} \in \mathbb{R}^K \)。
  4. **表示导向（Steering）**：在生成过程中，当模型当前表示 \( \bar{\pi}_l(x) \) 违反约束时，通过求解优化问题：
     \[
     \min_h \| \bar{\pi}_l(x) - h \|_1 \quad \text{s.t.} \quad \phi^\top \tilde{f}(h) \leq \tilde{\xi}
     \]
     得到修正后的表示 \( h \)，并用其覆盖原表示，然后继续生成。该优化可采用拉格朗日松弛法快速求解（文中用100步梯度下降）。
  5. **Alg. 1 (SafeFlow)**：在解码循环中，每步先检查表示是否安全，若不安全则修正，再预测下一个token，直到生成结束。

- **算法流程（文字说明）**：  
  (1) 用安全/不安全数据集训练概念编码器和多面体参数；  
  (2) 部署时，每次前向传播至层l获取隐藏状态，若违反多面体约束则进行表示修正（最小化与原始表示的L1距离并强制满足约束）；  
  (3) 使用修正后的表示完成后续解码，输出最终文本。

### 3. 实验设计

- **数据集/场景**：
  - **安全检测与防御**：使用**HarmBench**（Mazeika et al., 2024）作为对抗性攻击基准，包含9种攻击方法（GCG, GBDA, AutoPrompt, PEZ, UAT, AutoDAN, Human Jailbreak, Direct Request, Adaptive Attack）。
  - **能力保持评估**：使用**MMLU**（57个学科的多选题）衡量模型通用能力。
  - **可解释性分析**：使用**BeaverTails**数据集（330k条标注句子，14个安全类别）分析多面体各面对应语义概念。

- **对比方法**：
  - 提示型防御：Self Reminder, Response Check, SmoothLLM
  - 训练型/分类器型：Rejection Sampling（基于多面体决策直接拒绝）、MLP（相同参数量的二分类器，用于导向）、MLP+5（再增加5层）
  - 原始模型（无防御）作为基线

- **模型**：Llama2-7B, Ministral-8B, Qwen2-1.5B

### 4. 资源与算力

论文**未明确说明**训练SaP所需的GPU型号、数量及具体训练时长。仅提到模型使用16位精度（float16/bfloat16）以减少内存占用。训练过程使用Adam优化器、batch size=128，训练轮数等细节在附录中提供（如HarmBench训练epoch数未明确，BeaverTails训练20 epochs）。由于SaP仅在推理时进行少量梯度步骤（100步），整体算力开销相对可控，但作者未给出详细资源报告。

### 5. 实验数量与充分性

- **实验数量**：
  - 在3个LLM上、每个模型对比7种防御方法、9种攻击方法，每种配置重复5个种子，共计算大量ASR和MMLU指标。
  - 消融实验：对比有无概念编码器（CE）的影响（图3）；改变多面体面数量从1到50或60的影响（图6，分防御和分类两个维度）。
  - 可解释性分析：计算互信息热力图（图4）、KL散度分析（图5）展示各面对语义概念的特化。
  - 与MLP分类器的分类准确率对比（表1，4个模型比较）。
- **充分性与公平性**：
  - 实验覆盖多种攻击类型（梯度、基于搜索、人工设计）和多种模型规模（1.5B/7B/8B），具有较强的泛化性。
  - 对比方法选择全面，包括提示型、推理时、训练后方法，且MLP对比控制参数量接近，公平合理。
  - 重复5次种子报告均值±标准差，统计可靠性较好。
  - 不足：Adaptive Attack仅在Llama上测试（文中脚注说明），未在Ministral和Qwen上充分评估；且ST的MT-Bench评估仅做简要提及（附录表9），未详细讨论生成质量。

### 6. 论文的主要结论与发现

- **防御有效性**：SaP在保持MMLU准确率几乎不变的情况下，显著降低攻击成功率（以Llama2-7B为例，ASR从12.92%降至0.26%），优于所有基线方法。
- **可解释性**：概念编码器+稀疏正则化使多面体各面自然对应不同安全类别（如暴力、儿童虐待、虚假信息等），互信息热力图显示解缠表示。
- **几何建模优于纯分类**：即使MLP分类准确率与SaP相当，MLP导向的效果远差于SaP（图2），证明结构化几何约束比黑箱分类器更适合表示空间安全控制。
- **面数量影响**：防御性能随面数增加先快速提升后趋于稳定（约20-30面最佳），分类准确率类似但有些类别在面多时下降，提示存在过拟合或面浪费现象。

### 7. 优点

- **创新性**：首次将LLM安全明确建模为表示空间中的多面体约束，将CMDP理论与LLM内部表征结合。
- **后置部署**：无需修改模型权重或重新训练，对已部署模型可无缝集成。
- **可解释性**：每个面可关联到具体安全语义，提供人类可理解的决策依据。
- **高效性**：推理时仅需少量梯度步骤（100步），可使用向量化计算，与“测试时计算”趋势一致。
- **广泛验证**：在多个模型、多种攻击类型、不同数据集上进行了充分比较和消融。

### 8. 不足与局限

- **理论保证不足**：仅引用PAC学习下多面体的样本复杂度上界，但假设较强（完美可分、已知边际等），未提供针对LLM实际分布的泛化保证。
- **语义不连贯风险**：在Ministral-8B模型上，SaP的导向可能导致输出语义不连贯（作者承认）。
- **面分配策略启发式**：当前使用基于熵的启发式分配不安全样本到面（附录A），可能限制表示能力和训练稳定性。
- **实验覆盖缺失**：未在更大模型（如70B）上验证；对抗攻击排除Adaptive Attack在部分模型上的评估；未系统评估对良性输入的误触发率（可能影响有用性）。
- **计算开销细节缺失**：未报告具体训练时长、GPU型号和数量，影响可复现性和资源评估。
- **限于单层约束**：仅修改单个层（layer 20）的表示，可能不足以应对复杂安全需求。

（完）
