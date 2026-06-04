---
title: "Conflict-Aware Knowledge Editing in the Wild: Semantic-Augmented Graph Representation for Unstructured Text"
title_zh: 野外冲突感知知识编辑：面向非结构化文本的语义增强图表示
authors: "Zhange Zhang, Zhicheng Geng, Yuqing Ma, Tianbo Wang, Kai Lv, Xianglong Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=wHm5J9uanV"
tags: ["query:model-edit"]
score: 9.0
evidence: 面向非结构化文本的冲突感知知识编辑
tldr: 知识编辑方法通常依赖结构化知识表示，但现实中知识主要存在于非结构化文本中，导致表示模糊和编辑冲突。本文提出CAKE方法，通过语义增强的图表示来捕获非结构化文本中的知识关系，并设计冲突感知机制进行编辑。实验表明该方法在多种非结构化文本编辑任务中显著优于现有方法，有效解决了表示歧义和编辑冲突问题。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-whm5j9uanv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whm5j9uanv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whm5j9uanv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1346, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whm5j9uanv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 586, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whm5j9uanv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 762, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-whm5j9uanv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whm5j9uanv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whm5j9uanv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1071, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whm5j9uanv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1003, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whm5j9uanv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1221, \"height\": 137, \"label\": \"Table\"}]"
motivation: 现有知识编辑依赖结构化表示，无法处理真实世界中复杂的非结构化文本知识，导致编辑冲突和表示歧义。
method: 利用语义增强图表示从非结构化文本中抽取知识关系，并通过冲突感知机制进行编辑与整合。
result: 在多个基准上，CAKE比现有方法在编辑准确性和减少冲突方面提升显著。
conclusion: 冲突感知的图表示是处理非结构化知识编辑的有效途径，推动了知识编辑在真实场景中的应用。
---

## Abstract
Large Language Models (LLMs) have demonstrated broad applications but suffer from issues like hallucinations, erroneous outputs and outdated knowledge. Model editing emerges as an effective solution to refine knowledge in LLMs, yet existing methods typically depend on structured knowledge representations.  
However, real-world knowledge is primarily embedded within complex, unstructured text. Existing structured knowledge editing approaches face significant challenges when handling the entangled and intricate knowledge present in unstructured text, resulting in issues such as representation ambiguity and editing conflicts. 
To address these challenges, we propose a Conflict-Aware Knowledge Editing in the Wild (CAKE) framework, the first framework explicitly designed for editing knowledge extracted from wild unstructured text. 
CAKE comprises two core components: a Semantic-augmented Graph Representation module and a Conflict-aware Knowledge Editing strategy. The Semantic-augmented Graph Representation module enhances knowledge encoding through structural disambiguation, relational enrichment, and semantic diversification. Meanwhile, the Conflict-aware Knowledge Editing strategy utilizes a graph-theoretic coloring algorithm to disentangle conflicted edits by allocating them to orthogonal parameter subspaces, thereby effectively mitigating editing conflicts. Experimental results on the AKEW benchmark demonstrate that CAKE significantly outperforms existing methods, achieving a 15.43\% improvement in accuracy on llama3 editing tasks. Our framework successfully bridges the gap between unstructured textual knowledge and reliable model editing, enabling more robust and scalable updates for practical LLM applications.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：大语言模型（LLMs）存在幻觉、错误输出、知识过时等问题。模型编辑作为一种精确更新特定知识的手段，现有方法通常依赖结构化知识表示（如三元组或问答对）。
- **核心挑战**：真实世界知识主要存在于非结构化文本（如文档、文章）中，缺乏显式的问答对。将非结构化文本转化为结构化表示需要高昂的人工标注成本。现有结构化知识编辑方法在处理非结构化文本时面临两大难题：
  - **表示歧义（Representation Ambiguity）**：非结构化文本中实体通过复杂关系网络交织，同一实体可能关联多个对象，且存在隐式多跳关系，导致知识编码不确定性。
  - **编辑冲突（Editing Conflicts）**：非结构化文本中的知识具有密集语义重叠（如共享实体、相似关系），同时编辑语义相邻但预测目标矛盾的知识会导致梯度方向冲突，破坏模型收敛。
- **研究意义**：提出首个专门针对野外非结构化文本的知识编辑框架CAKE，弥合非结构化文本与可靠模型编辑之间的鸿沟。

## 2. 提出的方法论

### 核心思想
CAKE由两个核心模块组成：
- **语义增强图表示模块（SGR）**：通过结构消歧、关系丰富、语义多样化三个协同机制增强知识编码。
- **冲突感知知识编辑策略（CKE）**：利用图论着色算法将冲突的编辑分配到正交参数子空间，消除编辑冲突。

### 关键技术细节

#### 2.1 预备知识：野外非结构化知识编辑（WUKE）
- 传统方法：结构化知识实例 `K = {(s_i, r_i, o_i)}`，输入为 `x_i = s_i ⊕ r_i`，目标为 `o_i`。
- WUKE任务：仅用非结构化文本更新模型，通过三元组提取构造伪查询 `x_{ij} = e_i ⊕ r_{ij}`，但要求单次编辑注入文本中所有相连的三元组。
- 参数保持方法（如LoRA）：在原始参数`W`上增加额外参数`ΔW`，使用交叉熵损失更新。

#### 2.2 语义增强图表示（SGR）

**① 基于图的结构消歧**
- 设计结构感知提示模板，引导LLM从输入文本中动态构建知识图 `G = {E, R_s}`，其中`E`为实体集，`R_s`为直接关系集。
- 确保图结构与文本语义同构，保持段落级知识连贯性。

**② 多跳关系丰富**
- 引导LLM推断距离为2到p跳的实体对之间的隐式关系：`r_{ij} = M([I_h, G, T, (e_i, e_j)])`，其中`d_G(e_i, e_j) ∈ [2, p]`。
- 将新增关系并入`R_s`，稠密化知识图的关系流形。

**③ 释义驱动的语义多样化**
- 对每个关系事实`(e_i, r_{ij}, e_j)`，引导LLM生成释义变体`R_d`：`{r'_{ij}} = M([I_d, G, T, (e_i, r_{ij}, e_j)])`。
- 将原始图转化为多重有向图`G' = (E, R_s ∪ R_d)`，增加边多样性，提升对真实查询分布偏移的鲁棒性。

#### 2.3 冲突感知知识编辑（CKE）

**① 冲突图构建**
- 构造知识冲突图`G_c^* = (K, Φ)`，每个节点`k_{ij}`为一个知识三元组`(e_i, r_{ij}, e_j)`。
- 边函数`φ(k_{ij}, k_{pq})`定义为：
  ```
  φ = 1 如果 α·I(e_i, e_p) + β·(a_{ij}^T a_{pq})/(||a_{ij}||·||a_{pq}||) ≥ γ
  ```
  其中`a_{ij}`为查询`x_{ij}=e_i⊕r_{ij}`在编辑层的隐藏表示，`I(·)`为克罗内克指示函数，`α,β`为权重，`γ`为冲突阈值。
- 关键：冲突检测关注具有不同目标实体但共享主语或关系相似的三元组；并行边（相同主语-宾语）被显式标记为无冲突。

**② 图着色隔离编辑**
- 采用Welsh-Powell算法计算顶点着色方案`f`和最小色数`L`，将知识实例分配到`L`个LoRA参数子空间`ΔW_1, ..., ΔW_L`。
- 每个子空间独立更新：`ΔW_l ← ΔW_l - η·∇Σ_{f(k_{ij})=c_l} L(M(x_{ij}), e_j)`。
- 推理时通过激活相似度路由机制判断输入是否属于编辑范围：若激活相似度超过阈值（设为0.7），则融合所有LoRA子空间输出；否则仅用原始模型。

## 3. 实验设计

### 数据集与场景
- 标准WUKE基准：**CounterFact**（大量反事实知识，高度冲突）、**WikiUpdate**（丰富多样的知识实体）、**MQuAKE-CF**（多跳关系，编辑难度高）。
- 评估指标：**可靠性（Reliability）**：模型对编辑后问题的回答准确率；**局部性（Locality）**：模型对未编辑内容的准确率（使用ZsRE数据集中的语义无关问答对）。

### 对比方法
- 基线方法：ROME、MELO、MEMIT、WISE、ELDER（五种代表性知识编辑方法）。
- 遵循AKEW设置：所有基线方法先将非结构化文本中的每个句子提取为三元组再编辑。

### 实现细节
- 模型：GPT2-XL、LLaMA3.2-3B、LLaMA3-8B。
- 默认超参数：α=0.8，β=0.8，γ=0.8。
- 优化器：SGD；学习率0.001；最大迭代次数50；LoRA秩为8。
- 编辑层选择：
  - GPT2-XL：`transformer.h.36.mlp.c_fc`和`transformer.h.37.mlp.c_fc`
  - LLaMA3.2-3B和LLaMA3-8B：`model.layers.13.mlp.down_proj`

## 4. 资源与算力

- 文中说明：所有实验在装备八块NVIDIA A800（80GB显存）GPU的服务器上完成。
- 未明确给出单次实验的精确时长，但附录中比较了每样本编辑时间：CAKE为49.31秒，优于其他方法（例如ELDER 54.17秒，MELO 52.76秒，WISE 143.91秒），表明其训练效率较高。

## 5. 实验数量与充分性

### 实验组别
1. **主实验结果（Table 1）**：在3个数据集×3个模型×6种方法（含CAKE）上对比可靠性、局部性及均值，共9组（每个模型/数据集组合）。
2. **消融实验（Table 2）**：在3个模型上分别去掉SGR、去掉CKE、替换为Router Expert（即ELDER的分配方式）与完整模型对比，共4×3=12组结果。
3. **冲突感知超参数分析（Figure 3）**：在LLaMA3.2上调整α/γ和β/γ，观察编辑可靠性变化。
4. **知识冲突与编辑可靠性分析（Figure 4）**：量化冲突比与可靠性关系。
5. **激活相似度路由阈值分析（Figure 5）**：在CounterFact/Llama3.2上调整阈值，观察可靠性与局部性变化。
6. **SGR内部消融（Table 5）**：在CounterFact/Llama3.2上去掉多跳丰富、去掉释义多样化，与完整SGR对比。
7. **初始知识图质量评估（Table 4）**：人工评估三个数据集上的提取准确率与知识完整性。
8. **编辑效率对比（Table 3）**：在MQuAKE-CF/Llama3-8B上对比每样本编辑时间。

### 实验充分性与公平性
- 实验覆盖了3种不同规模和架构的LLM、3个风格迥异的非结构化数据集、5种主流基线方法，消融全面，参数分析细致。对照组设置合理（如去掉模块、替换为其他分配策略），符合学术规范。
- 但在部分实验中未报告多次运行的标准差或统计显著性检验，可能影响结果稳健性的量化评估。

## 6. 主要结论与发现

- CAKE在所有三个数据集和三个LLM上均显著优于现有方法，在可靠性上最高提升15.43%（Llama3-8B在CounterFact上）。
- SGR模块中三个增强机制对性能均有正向贡献，其中释义多样化对提高编辑可靠性最为关键（表5）。
- CKE的图着色策略有效缓解了知识冲突：当冲突程度高时，单专家LoRA可靠性急剧下降，而CAKE保持稳定（图4）。
- 激活相似度路由的阈值选择对可靠性/局部性有平衡作用（图5）。
- CAKE在编辑效率上也具有竞争力，每样本编辑时间最低（49.31秒）。

## 7. 优点

- **首次针对性解决野外非结构化文本知识编辑问题**，填补了结构化方法无法直接处理真实文本的空白。
- **多维度语义增强**：通过结构消歧、多跳关系丰富、释义多样化系统性地缓解表示歧义，思路清晰且有效。
- **创新冲突隔离机制**：将冲突检测形式化为图着色问题，利用经典算法实现参数子空间隔离，避免了复杂的路由训练，简洁高效。
- **泛化能力强**：在三个不同特征的数据集（反事实冲突、多实体、多跳）上均表现优异，说明框架具有良好适应性。
- **实验设计较全面**：消融、超参数分析、效率对比、知识图质量评估等齐全，验证了各组件的必要性。

## 8. 不足与局限

- **模型架构限制**：仅适用于自回归（next-token prediction）LLM，无法直接适配编码器-解码器等架构。
- **领域专业性依赖**：在特定领域知识编辑时，SGR模块的图构建需要利用对应领域LLM来保证准确性，否则可能导致知识图质量下降。
- **缺乏真实性校验**：框架未考虑非结构化文本本身的真实性与可靠性，可能被用于恶意编辑模型、传播虚假信息（如歧视、偏见）。
- **缺乏统计显著性检验**：实验结果以均值形式报告，未给出误差棒或置信区间，难以判断多次实验的稳定性和差异的统计意义。
- **路由机制较为简单**：激活相似度阈值仅设为固定值0.7，未探讨自适应阈值或更复杂的路由策略，可能在某些场景下不最优。
- **未探讨大规模持续编辑场景**：实验限于单次编辑（每个文本独立编辑），未验证在长期、连续编辑下的冲突累积和性能退化情况。

（完）
