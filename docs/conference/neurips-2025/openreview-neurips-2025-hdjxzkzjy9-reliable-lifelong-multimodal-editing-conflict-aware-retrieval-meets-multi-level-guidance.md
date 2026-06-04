---
title: "Reliable Lifelong Multimodal Editing: Conflict-Aware Retrieval Meets Multi-Level Guidance"
title_zh: 可靠终身多模态编辑：冲突感知检索结合多级指导
authors: "Qiang Zhang, Fanrui Zhang, Jiawei Liu, Ming Hu, Junjun He, Zheng-Jun Zha"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=hdJXzKZjY9"
tags: ["query:model-edit"]
score: 9.0
evidence: 多模态大模型知识编辑，结合冲突感知检索
tldr: 多模态大模型知识编辑面临大规模检索不准确和缺乏多级指导的问题。本文提出CARML，集成冲突感知动态检索与内外隐式/显式多级指导，实现可靠终身编辑。通过模态内不确定性和模态间冲突量化动态融合检索结果，提升编辑准确性和可靠性。实验证明其在多种编辑任务上优于现有方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hdjxzkzjy9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1423, \"height\": 1062, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1455, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 655, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 640, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hdjxzkzjy9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 316, \"label\": \"Table\"}]"
motivation: 现有方法在大规模知识检索中难以精确匹配，且缺乏多级协调指导。
method: 引入模态内不确定性和模态间冲突量化，动态融合多通道检索结果，结合多级显隐式指导。
result: 在多模态知识编辑基准上取得最先进效果，编辑可靠性显著提升。
conclusion: CARML为多模态模型的知识更新提供了高效可靠的编辑框架。
---

## Abstract
The dynamic nature of real-world information demands efficient knowledge editing in multimodal large language models (MLLMs) to ensure continuous knowledge updates. However, existing methods often struggle with precise matching in large-scale knowledge retrieval and lack multi-level guidance for coordinated editing, leading to less reliable outcomes. To tackle these challenges, we propose CARML, a novel retrieval-augmented editing framework that integrates conflict-aware dynamic retrieval with multi-level implicit and explicit guidance for reliable lifelong multimodal editing. Specifically, CARML introduces intra-modal uncertainty and inter-modal conflict quantification to dynamically integrate multi-channel retrieval results, so as to pinpoint the most relevant knowledge to the incoming edit samples. Afterwards, an edit scope classifier discerns whether the edit sample semantically aligns with the edit scope of the retrieved knowledge. If deemed in-scope, CARML refines the retrieved knowledge into information-rich continuous prompt prefixes, serving as the implicit knowledge guide. These prefixes not only include static knowledge prompt that capture key textual semantics but also incorporate token-level, context-aware dynamic prompt to explore fine-grained cross-modal associations between the edit sample and retrieved knowledge. To further enhance reliability, CARML incorporates a "hard correction" mechanism, leveraging explicit label knowledge to adjust the model’s output logits. Extensive experiments across multiple MLLMs and datasets indicate the superior performance of CARML in lifelong multimodal editing scenarios.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

随着多模态大语言模型（MLLMs）的快速发展，其在实际应用中需要不断更新嵌入的知识以适应动态变化的现实世界信息。然而，现有的知识编辑方法存在两大痛点：一是在大规模编辑知识库中难以精确检索到最相关的知识；二是缺乏多级协调指导（包括隐式与显式知识），导致编辑结果的可靠性不足。该论文旨在解决**终身多模态知识编辑**中的检索不精确与编辑不可靠问题，提出一种融合冲突感知动态检索与多级隐式/显式指导的新型框架。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
CARML 框架通过两个核心模块实现可靠编辑：
- **冲突感知动态检索（Conflict-Aware Dynamic Retrieval）**：利用多通道（视觉、文本、多模态）检索并结合模态内不确定性（熵）与模态间冲突度（Jaccard 差异），动态加权融合各通道相似度得分，精确定位最相关历史编辑知识。
- **多级知识指导（Multi-Level Knowledge Guidance）**：包括隐式指导（静态知识提示和上下文感知动态提示）与显式指导（输出 logits 增强），协同引导 MLLM 生成期望输出。

### 关键技术细节
1. **知识库构建**：对每个历史编辑请求，提取视觉、文本及融合多模态嵌入（使用预训练模型 mexma-siglip2）。
2. **多通道检索**：计算查询嵌入与知识库中各模态嵌入的余弦相似度。
3. **冲突感知融合与重排**：对每个模态相似度分布计算信息熵 \(U_i\)，并计算模态间 Top-K 候选集的 Jaccard 冲突度 \(C_{ij}\)。通过动态权重 \(W_i = \text{softmax}(m_i)\) 加权融合相似度，其中 \(m_i\) 结合归一化熵与归一化冲突度。
4. **编辑范围分类器**：使用两个可训练 MLP 将查询嵌入与检索知识映射到新语义空间，计算余弦相似度，若超过阈值 \(\beta\) 则触发编辑。分类器使用 Focal Loss 训练，输入标签由可靠性/泛化性样本（范围内）和局部性样本（范围外）定义。
5. **隐式指导**：
   - 静态知识提示：将检索知识的文本嵌入通过 MLP 映射为固定长度连续提示。
   - 上下文感知动态提示：将检索知识的视觉和多模态嵌入映射为提示，并通过 token 级注意力机制（以编辑样本嵌入为 query，各模态提示 token 为 key/value）融合生成动态提示。
6. **显式指导（输出 logits 增强）**：若模型预测分布与期望输出 token 的负对数相似度低于阈值 \(\eta\)，则直接添加 one-hot 向量提升目标 token 概率。
7. **训练目标**：联合优化编辑损失（可靠性+泛化性+局部性）与分类器损失，权重系数 \(\lambda=0.04\)，保持 MLLM 核心参数冻结。

## 3. 实验设计

### 数据集与场景
- **E-VQA**（从 VQAv2 构建，视觉问答编辑）
- **E-IC**（从 COCO Caption 构建，图像描述编辑）
- **VLKEB**（真实图像，基于知识图谱的结构化编辑，更大规模）
- **跨任务编辑**：同时处理 E-VQA 和 E-IC 样本的连续编辑序列。

### Benchmark 与评估指标
- 指标：可靠性（Reliability）、T-泛化性（T-Generality）、M-泛化性（M-Generality）、T-局部性（T-Locality）、M-局部性（M-Locality）。
- 编辑数量 T 分别设为 1、100、1000，模拟终身编辑场景。

### 对比方法
- **FT-L**：微调语言模型最后一层。
- **TP**、**MEND**：内在知识编辑方法。
- **SERAC**、**LEMoE**、**RECIPE**、**LiveEdit**：外部知识辅助方法，其中 LiveEdit 为专为 MLLM 设计的最先进终身编辑方法。

### 基线实现
所有方法均在两个 MLLM 上测试：BLIP-2 OPT（2.7B）和 LLaVA-V1.5（7B）。

## 4. 资源与算力
论文明确说明：“All experiments were conducted on a single NVIDIA H100 GPU。”但未给出具体训练时长或总 GPU 小时数。训练周期设为 120 个 epoch，batch size 为 8，学习率 1e-5。由于代码未公开，更详细的资源消耗难以复现。

## 5. 实验数量与充分性
- **主实验**：在三个数据集（E-VQA、E-IC、VLKEB）、两个 MLLM、三种编辑数量（T=1,100,1000）下进行，共约 3×2×3=18 组表格结果。
- **跨任务编辑**：一项附加实验（表4）。
- **消融实验**：基于 RECIPE 逐步替换组件（+冲突感知检索、+分类器、+动态提示、+logits 增强），共 5 组对比（表5）。
- **分析实验**：t-SNE 可视化编辑范围分类器的语义空间（图3a）；编辑时间与准确率权衡（图3b）；可视化编辑案例（图3c、图4）。
- **平均性能汇总**：附录表6。

整体实验设计较为充分，对比了多种类型基线（内在编辑、外部记忆、终身编辑），覆盖了不同模态任务和数据集规模，消融验证了各组件贡献。公平性方面，所有实验遵循相同评估协议，但未报告误差棒或多次运行统计，可能受随机性影响。

## 6. 主要结论与发现
1. **CARML 在终身多模态编辑中显著优于所有基线**，尤其在 T=1000 时仍保持近 100% 的可靠性和泛化性，而基线方法性能大幅下降。
2. **冲突感知动态检索**是性能关键：相比传统单模态检索，多通道融合与量化冲突可大幅提升检索准确率（Recall@1 接近 100%）。
3. **多级指导**（隐式+显式）协同作用：消融实验显示每一步改进（+检索、+分类器、+动态提示、+logits）均有效提升性能，最终达到最优。
4. **编辑范围分类器**成功区分范围内/外样本，保护模型局部性。
5. **高效性**：CARML 在准确率与编辑时间权衡上优于 LiveEdit 等方法，具有实际部署潜力。

## 7. 优点
- **创新性**：首次在终身多模态编辑中引入冲突感知动态检索，结合模态内不确定性和模态间冲突度进行自适应融合。
- **完备性**：同时提供隐式（连续提示）和显式（logits 增强）指导，形成多级协作编辑框架。
- **鲁棒性**：在大量编辑（1000 次）后性能几乎不衰减，克服了参数扰动和灾难性遗忘。
- **通用性**：在 VQA、图像描述、跨任务场景以及两种不同架构 MLLM 上均表现优越。
- **分析透彻**：通过消融、可视化、时间权衡等实验深入解释机制。

## 8. 不足与局限
1. **复杂抽象编辑**：论文承认对高级常识推理等复杂编辑的泛化能力需进一步验证。
2. **模型规模限制**：实验仅在 2.7B 和 7B 规模的 MLLM 上进行，未测试更大模型（如 InternVL2.5-78B），缩放性能未知。
3. **计算资源报告不全**：未提供单次训练/推理的具体时间或 GPU 小时数，复现难度增加。
4. **未报告统计误差**：实验结果未给出多次运行的标准差或置信区间，可能存在偶然性。
5. **代码未开源**：仅声明“will release upon acceptance”，目前不可复现。
6. **阈值依赖**：编辑范围分类器阈值 β 和 logits 增强阈值 η 需要针对不同数据集手动调参（附录 A 显示 β 在 E-IC 为 0.4，其他为 0.7），缺乏自适应机制。
7. **潜在负效应**：论文在 Broader Impacts 中承认知识编辑可能被恶意利用植入错误信息，但未给出具体防护措施。

（完）
