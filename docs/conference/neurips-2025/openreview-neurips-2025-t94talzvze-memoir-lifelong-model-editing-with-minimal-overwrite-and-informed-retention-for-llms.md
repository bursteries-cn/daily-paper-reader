---
title: "MEMOIR: Lifelong Model Editing with Minimal Overwrite and Informed Retention for LLMs"
title_zh: MEMOIR：具有最小覆盖和知情保留的大语言模型终身模型编辑
authors: "Ke Wang, Yiming QIN, Nikolaos Dimitriadis, Alessandro Favero, Pascal Frossard"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=t94tALZvZE"
tags: ["query:model-edit"]
score: 9.0
evidence: 提出针对大语言模型的终身模型编辑框架MEMOIR
tldr: 针对大语言模型终身编辑中泛化性差、干扰历史编辑、难以扩展到长序列的问题，提出MEMOIR框架。该框架通过残差记忆模块和依赖于数据的稀疏掩码，将每个编辑限制在参数子集上，实现最小覆盖和知情保留。实验表明，MEMOIR在长编辑序列中保持了高精度和低遗忘，显著优于现有方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 788, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 671, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 644, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 732, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t94talzvze/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 680, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 874, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 826, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 591, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1428, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1435, \"height\": 1310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1288, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 654, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 730, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1459, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t94talzvze/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 801, \"height\": 269, \"label\": \"Table\"}]"
motivation: 现有终身模型编辑方法存在泛化性差、干扰历史编辑或无法扩展到长序列的问题。
method: 提出MEMOIR框架，利用残差记忆模块和数据依赖稀疏掩码，将每个编辑注入参数子集中。
result: 在长编辑序列上保持高编辑精度和低遗忘率，优于现有方法。
conclusion: MEMOIR实现了可扩展且高效的终身模型编辑，兼具精度和参数效率。
---

## Abstract
Language models deployed in real-world systems often require post-hoc updates to incorporate new or corrected knowledge. However, editing such models efficiently and reliably—without retraining or forgetting previous information—remains a major challenge. Existing methods for lifelong model editing either compromise generalization, interfere with past edits, or fail to scale to long editing sequences. We propose MEMOIR, a novel scalable framework that injects knowledge through a residual memory, i.e., a dedicated parameter module, while preserving the core capabilities of the pre-trained model. By sparsifying input activations through data-dependent masks, MEMOIR confines each edit to a distinct subset of the memory parameters, minimizing interference among edits. At inference, it identifies relevant edits by comparing the sparse activation patterns of new queries to those stored during editing. This enables generalization to rephrased queries by activating only the relevant knowledge while suppressing unnecessary memory activation for unrelated prompts. Experiments on question answering, hallucination correction, and out-of-distribution generalization benchmarks  across LLaMA-3 and Mistral demonstrate that MEMOIR achieves state-of-the-art performance across reliability, generalization, and locality metrics, scaling to thousands of sequential edits with minimal forgetting.

---

## 论文详细总结（自动生成）

# 论文《MEMOIR: Lifelong Model Editing with Minimal Overwrite and Informed Retention for LLMs》中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：大语言模型（LLMs）在实际部署中需要持续更新知识（如纠正错误、补充新信息），但重新训练代价高昂且易发生灾难性遗忘（catastrophic forgetting）。现有终身模型编辑方法存在三方面不足：
  - **泛化性差**：非参数方法（如GRACE）严格记忆编辑样本，但对语义相似的改写查询失效。
  - **干扰历史编辑**：参数方法（如ROME、MEMIT、WISE）在连续编辑中会覆盖先前知识，导致遗忘。
  - **难以扩展**：多数方法在编辑序列超过几百次时性能急剧下降。
- **目标**：设计一种同时满足**可靠性**（正确回答编辑样本）、**泛化性**（适应改写查询）和**局部性**（不影响无关样本）的终身编辑框架，并能扩展到数千次编辑。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：在预训练模型中插入一个**残差记忆模块**（residual memory layer，即与原始投影层同尺寸的零初始化全连接层），所有编辑都只修改该模块的权重，保留原始模型参数不变。通过在输入激活上施加**数据依赖的稀疏掩码**，将每次编辑限制在记忆模块的一个子集参数上，减少编辑间的覆盖。推理时，通过比较输入与已编辑样本的掩码模式（汉明距离），动态激活相关编辑知识或完全停用记忆模块。

- **关键技术细节**：
  1. **稀疏掩码生成（TopHash）**：
     - 对输入激活（取所有token平均）进行**Top-k选择**（保留幅值最大的k个特征）。
     - 对Top-k索引施加**固定随机排列**（permutation），将原本集中的更新分散到不同列，增加多样性而不破坏语义一致性（因为语义相似的输入会产生相似的Top-k结果，经相同排列后仍高度重叠）。
     - 最终得到二值掩码 $M(a) \in \{0,1\}^D$，其中只有k个位置为1。
  2. **编辑过程**：
     - 残差记忆的最终输出为 $FFN_{\text{edited}}(a) = W_0 a + W_m (M(a) \odot a)$。
     - 由于掩码 $M(a)$ 将输入大部分维度置零，梯度只更新 $W_m$ 中对应的k列，其他列保持不变，从而保护先前编辑的知识。
     - 每次编辑时，将当前样本的掩码存入数据库。
  3. **推理时条件知识激活**：
     - 计算当前输入x的掩码 $M(a(x))$，与数据库所有掩码计算**最优重叠率** $R_{\text{match}}(x)$（即与最相似编辑样本的掩码交并比）。
     - 设置阈值 $\tau$：若 $R_{\text{match}}(x) \ge \tau$，则激活残差记忆，并使用匹配到的编辑样本的掩码（而非当前输入的掩码）来路由相应知识；若 $R_{\text{match}}(x) < \tau$，则完全停用记忆模块，仅使用原始模型输出，从而保证局部性。

## 3. 实验设计

- **数据集与场景**：
  - **QA任务**：ZsRE数据集（上下无关的问答），评估编辑后的可靠性、泛化性（改写问题）、局部性（无关问题）。
  - **幻觉纠正**：SelfCheckGPT数据集（GPT-3生成的维基百科风格传记，含事实幻觉），评估可靠性（以困惑度PPL衡量）和局部性。
  - **OOD泛化**：Temporal数据集（新兴实体知识，含distributionally shifted的测试对），评估对结构化变体的泛化能力。
  - **多跳推理**：RippleEdits benchmark（POPULAR数据集），评估递推逻辑泛化和关系特异性。
- **对比方法**：
  - 非参数：GRACE
  - 参数：FT（微调）、ROME、MEMIT、DEFER、WISE、AlphaEdit
- **模型**：LLaMA-3-8B-Instruct、Mistral-7B、LLaMA-2-7B、GPT-J-6B
- **编辑规模**：1, 10, 100, 1000, 3000, 7000, 15000 次顺序编辑
- **评估指标**：可靠性（Rel.）、泛化性（Gen.）、局部性（Loc.），平均性能（Avg.）；幻觉任务用PPL（越低越好）和Loc.

## 4. 资源与算力

- 所有实验在**单张NVIDIA A100 GPU**上完成。
- 编辑耗时示例：
  - 对于LLaMA-3，编辑1000个QA样本约需**3小时**；Mistral约需**4小时**。
  - 对于幻觉纠正，编辑600个样本在LLaMA-3上约需**4小时**，Mistral约需**6小时**。
- 使用SGD优化器，学习率1.0，梯度裁剪1.0，每编辑步数30-70。
- 论文未报告总计算开销或能源消耗。

## 5. 实验数量与充分性

- **实验数量**：涵盖了四种模型架构、四个相关数据集、多种编辑长度（1到15000）、多个对比方法（7种以上），以及消融实验（TopHash变体、条件激活、k值影响、激活中心化等）。**总计实验组数十组**，数据量充分。
- **充分性**：
  - 在QA、幻觉纠正、OOD、多跳等不同难度任务上均进行了测试，覆盖了编辑的三个核心指标。
  - 对关键超参数（k值、阈值$\tau$、激活中心化样本数）进行了系统消融，验证了设计选择的合理性。
  - 对比方法的参数按官方或最佳实践设置，并注明来源（如EasyEdit库、原文参数），保证了公平性。
- **客观性**：论文如实报告了基线的性能衰退（尤其在长序列下），并展示了MEMOIR的稳定性；对随机性（如小编辑数）采用多次实验平均以减少方差。

## 6. 主要结论与发现

- MEMOIR在所有数据集和模型上取得了**最平衡的性能**，在可靠性、泛化性、局部性之间达到最优平均分。
- 在长编辑序列（最高15000）中，MEMOIR仅出现轻微性能下降（Rel.=0.87），而基线方法（如AlphaEdit降至0.02，WISE降至0.43）严重遗忘。
- 消融实验表明，TopHash（Top-k + 排列）和条件知识激活是关键组件：缺少排列会导致泛化性下降；缺少条件激活会严重破坏局部性。
- MEMOIR不需要大量无关样本进行正则化，而基线方法（如MEMIT、WISE）通常需要100,000个无关样本。

## 7. 优点

- **创新性**：将稀疏激活思想引入终身模型编辑，通过数据依赖掩码实现编辑的自然隔离和检索，避免显式任务边界或身份标签。
- **高效性**：仅修改一个线性层的部分参数，计算开销低，且推理时路由计算简单（汉明距离比较）。
- **可扩展性**：实验证明可支持上万次编辑，远超先前工作（通常难以超过1000次）。
- **鲁棒性**：对超参数（k、阈值）不敏感，且激活中心化只需少量无关样本即可稳定性能。
- **无需额外正则化数据**：相比WISE、MEMIT等需要大量无关数据，MEMOIR仅利用编辑样本本身，降低了数据准备成本。

## 8. 不足与局限

- **架构限制**：当前方法只修改单个线性层（FFN投影层），可能无法处理需要更大幅度模型变化的知识（如长文本依赖或多层因果关系）。扩展到多层或分层编辑是未来方向。
- **模型类型**：实验仅覆盖decoder-only Transformer；未测试encoder-decoder或多模态模型。
- **多跳推理能力有限**：虽然MEMOIR在多跳任务上优于基线，但绝对分数仍然不高（Rel.=0.98, Gen.=0.20, Spec.=0.59），复杂推理场景下的泛化仍是挑战。
- **计算与存储开销**：需要存储每个编辑样本的稀疏掩码（4096维二值向量），在极小数据集上可能不是问题，但在百万级编辑上仍需考虑索引效率。
- **潜在偏差风险**：实验基于英文数据集，未验证多语言或领域迁移能力；且纠正的知识可能引入新的事实错误，未讨论对模型公平性、偏见的影响。
- **局限性中的开放性**：作者提到编辑一个线性层的局限性，但未量化分析性能瓶颈的根源（如参数量不足、无法影响更浅层表示等）。

（完）
