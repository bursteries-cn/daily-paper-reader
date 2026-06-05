---
title: "Representation Shattering in Transformers: A Synthetic Study with Knowledge Editing"
title_zh: Transformer中的表征破碎：基于知识编辑的合成研究
authors: "Kento Nishi, Rahul Ramesh, Maya Okawa, Mikail Khona, Hidenori Tanaka, Ekdeep Singh Lubana"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=BKOeyZal0x"
tags: ["query:model-edit"]
score: 9.0
evidence: 研究知识编辑对模型表征的负面影响
tldr: 该论文通过合成知识图谱任务，发现知识编辑算法会导致Transformer模型出现表征破碎现象，即编辑一个事实关联会使得相关实体在隐藏层的表征中变得混乱，从而破坏模型的整体事实回忆和推理能力。研究揭示了知识编辑的潜在危害机制，为安全编辑提供了理论指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 840, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 637, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1645, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 900, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 859, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1427, \"height\": 1007, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1763, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1690, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 883, \"height\": 880, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1727, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1764, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1769, \"height\": 1327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1722, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1715, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1665, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1709, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1712, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1717, \"height\": 854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bkoeyzal0x/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1667, \"height\": 861, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bkoeyzal0x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 903, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkoeyzal0x/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 663, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkoeyzal0x/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1147, \"height\": 1387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bkoeyzal0x/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 825, \"height\": 579, \"label\": \"Table\"}]"
motivation: 现有知识编辑算法虽能更新事实，但会损害模型整体的回忆和推理能力，其背后原因尚不明确。
method: 设计一个结构化知识图谱的合成任务，训练Transformer从零学习，并施加知识编辑来观察表征变化。
result: 发现编辑会导致相关实体表征在隐藏层中混淆，即表征破碎，从而降低性能。
conclusion: 表征破碎是知识编辑副作用的重要机制，需要设计更安全的编辑方法。
---

## Abstract
Knowledge Editing (KE) algorithms alter models' weights to perform targeted updates to incorrect, outdated, or otherwise unwanted factual associations. However, recent work has shown that applying KE can adversely affect models' broader factual recall accuracy and diminish their reasoning abilities. Although these studies give insights into the potential harms of KE algorithms, e.g., performance evaluations on benchmarks, little is understood about why such destructive failures occur. Motivated by this, we define a novel synthetic task in which a Transformer is trained from scratch to internalize a "structured" knowledge graph. The structure enforces relationships between entities of the graph, such that editing a factual association has "trickling effects" on other entities (e.g., altering X's parent is Y to Z affects who X's siblings' parent is). Through evaluations of edited models on this task, we show that KE inadvertently affects representations of entities beyond the targeted one, distorting relevant structures that allow a model to infer unseen knowledge about an entity. We call this phenomenon representation shattering and demonstrate that it degrades models' factual recall and reasoning performance. We further corroborate our findings in naturalistic settings with pre-trained Llama and Mamba models as well. Overall, our work yields a precise mechanistic hypothesis to explain why KE has adverse effects on model abilities.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：知识编辑（Knowledge Editing, KE）旨在精准修改大语言模型中的错误或过时事实。然而，近期研究发现KE会意外损害模型的整体事实回忆准确率和推理能力。
- **问题**：虽然已有工作通过基准评测揭示了KE的负面影响，但对其**内部机制**缺乏理解——编辑为何以及如何导致广泛的能力退化？
- **目标**：本文通过构建可控的**合成知识图**任务，从表示层面提出“**表示碎片化**”（Representation Shattering）假说：KE扭曲了实体在模型内部表示空间中的几何结构，从而破坏模型基于该结构进行推理的能力。

## 2. 方法论

### 核心思想
- 设计一个具有**全局结构**（循环排列）的知识图，实体之间通过关系（如“顺时针1跳”）相互连接。Transformer从该图上学习序列（随机游走），从而在内部表示中编码出与图结构同构的**流形**。
- 应用KE（如ROME）修改一个事实后，观测表示流形的变化，并定义量化指标衡量结构扭曲程度。

### 关键技术细节
- **知识图定义**：2048个实体，3个独立的循环顺序（I, II, III），每个顺序下有8个关系（1~4跳的顺时针与逆时针），共24个关系。
- **数据生成**：从图中随机采样路径（交替实体和关系），作为训练文本序列。序列长度16，最大组合长度2。
- **模型**：2层nanoGPT Transformer（GPT风格），词嵌入维度24，12头注意力，上下文长度16。训练150k步。
- **编辑方法**：主要使用ROME（在MLP层做秩一更新），也测试MEMIT、AlphaEdit、PMET。对合成模型，编辑在layer 1的MLP投影矩阵上执行。
- **表示碎片化度量**：定义指标 \( R(D^*) = \frac{\|D^* - D_\emptyset\|_F}{\|D_\emptyset\|_F} \)，其中 \( D \) 是实体表示间的欧氏距离矩阵。\( R \) 越大表示结构扭曲越严重。

### 评价任务
- **直接回忆**：预测已学到的事实。
- **逻辑推理**：推断逆关系（如从顺时针1跳推断逆时针1跳）。
- **组合推理**：组合两个关系预测目标实体。

## 3. 实验设计

### 合成实验
- **数据集**：基于2048实体的循环知识图生成10^8个序列（训练集）。保留一些事实不直接出现，用于测试逻辑/组合推理。
- **基准**：无编辑的原始模型性能（直接回忆准确率>98%，组合推理>88%）。
- **对比方法**：对ROME、MEMIT、AlphaEdit、PMET均进行了测试。编辑类型包括**纠正编辑**（修正模型错误）和**反事实编辑**（故意引入不一致）。
- **关键变量**：反事实编辑的“距离”（d=1~4，表示新事实在循环顺序上与原事实相距几步）。

### 自然语言实验（LLM验证）
- **模型**：Llama 3 8B Instruct、Mamba 2.8B。
- **数据**：12个月份的循环顺序（结构化先验），编辑如“January is followed 8 months later by ...”改为错误月份。编辑距离d=1,2,3。
- **基准**：MMLU-Redux推理基准，ZeroEval框架。
- **额外实验**：树形结构（城市-国家关系）的初步验证，使用GPT-2 XL。

### 消融/补充实验（见附录）
- 因果追踪验证KE假设（MLP层存储事实）。
- MLP作为键值存储的可视化。
- 不同表示提取点的流形图。
- 所有24个关系的流形图。
- 反事实编辑的分布图。
- 多方法（MEMIT, AlphaEdit, PMET）的对比表。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。仅提到合成模型训练150k步，使用nanoGPT参数（批量大小256）。自然语言实验使用了Llama 3 8B和Mamba 2.8B，但未提及硬件配置。因此，无法评估资源开销。

## 5. 实验数量与充分性

- **实验数量**：非常充分。主要实验包括：
  - 合成模型上对3种评价任务、3个子图（编辑/保留/测试）、4种编辑距离、4种不同KE方法的对比（主表1、表3）。
  - 表示可视化：多个编辑实例、多个层提取点（附录图12）。
  - 因果追踪和键-值验证。
  - 自然语言实验：2个模型、2种架构（Transformer和状态空间模型）、不同编辑距离。
  - 树形结构初步验证。
- **充分性**：实验设计较为系统，控制了关键变量（编辑距离、子图角色），并使用多个KE方法确保结论的通用性。消融和补充实验覆盖了表示分析的各个方面。
- **客观性与公平性**：评估指标（准确率、R(D*)）定义清晰，对比方法采用公开实现，编辑设置一致。但自然语言实验仅在月份循环上验证，树形结构实验仅初步，且无其他基准对比（如未编辑模型性能）。

## 6. 主要结论与发现

1. **表示碎片化假说成立**：KE编辑会破坏实体在Transformer内部的表示流形，几何结构扭曲程度与编辑的反事实距离正相关。
2. **性能退化与碎片化强相关**：表示碎片化指标R(D*)与准确率下降高度相关（合成实验r²=0.905）。
3. **编辑距离越大，损害越严重**：反事实编辑距离从1增加到4，准确率下降幅度和R(D*)均单调增加。
4. **现象泛化到真实LLM**：在Llama 3 8B Instruct和Mamba 2.8B上，对月份循环的编辑同样引起表示碎片化和推理性能下降。
5. **方法普适性**：ROME、MEMIT、AlphaEdit、PMET均表现出类似碎片化模式，只是程度不同（更晚的方法损害略小）。

## 7. 优点

- **机制层面的解释**：提供了直观且可量化的“表示碎片化”机制，而非仅停留于基准评测。
- **可控的合成框架**：通过结构化知识图，精确控制实体关系和编辑影响，便于因果推断。
- **可视化支持**：利用Isomap降维展示流形变化，直观揭示编辑如何“破碎”几何结构。
- **多方法验证**：覆盖主流KE方法，增强了结论的稳健性。
- **向真实世界的推广**：在强大生产级模型（Llama 3, Mamba）上得到初步验证，提升了假说可信度。

## 8. 不足与局限

- **合成任务简化**：仅使用循环结构，真实知识图更为复杂（如层次、多关系、稀疏）。树形验证仅初步。
- **编辑方法覆盖有限**：虽测试了4种，但未包括基于元学习或微调的方法，且仅测试了一次编辑，未研究顺序或批量编辑的累积效应（但MEMIT实验采用批量编辑）。
- **自然语言验证范围窄**：仅测试了月份循环和少量城市-国家关系，未在其他结构化概念（如数字顺序、知识图谱问答）上验证。
- **未提出解决方案**：论文揭示了问题机制，但未提供改进KE算法以减轻碎片化的具体策略。
- **资源信息缺失**：未报告算力开销，可能影响复现和可扩展性评估。
- **表示碎片化度量R(D*)的局限性**：Frobenius范数对排列敏感，等价于要求实体保持绝对位置；但实际中只要保持相对结构即可（如整体旋转），该指标可能放大无害变化。但作者指出其对排列敏感正是为了检测结构扭曲。

（完）
