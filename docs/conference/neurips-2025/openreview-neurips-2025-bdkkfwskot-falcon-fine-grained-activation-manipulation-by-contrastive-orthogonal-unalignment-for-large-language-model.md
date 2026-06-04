---
title: "FALCON: Fine-grained Activation Manipulation by Contrastive Orthogonal Unalignment for Large Language Model"
title_zh: FALCON：面向大语言模型的对比正交去对齐细粒度激活操纵
authors: "Jinwei Hu, Zhenglin Huang, Xiangyu Yin, Wenjie Ruan, Guangliang Cheng, Yi Dong, Xiaowei Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BDKkFwskot"
tags: ["query:model-edit"]
score: 9.0
evidence: 细粒度激活操作实现大模型有害知识遗忘
tldr: 现有机器遗忘方法依赖粗粒度损失组合，难以精确分离知识与平衡效果。本文提出FALCON，通过对比正交去对齐实现细粒度激活操纵，利用信息论指导高效参数选择。实验表明，FALCON在移除有害信息的同时保持模型实用性，显著优于基线。该方法为模型编辑提供了新的表示级操控手段，有助于提升LLM安全性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdkkfwskot/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdkkfwskot/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdkkfwskot/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 761, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bdkkfwskot/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 373, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdkkfwskot/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 779, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdkkfwskot/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdkkfwskot/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 906, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bdkkfwskot/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1015, \"height\": 157, \"label\": \"Table\"}]"
motivation: 现有训练时遗忘方法无法精确分离知识，且在移除效果与模型效用间难以平衡。
method: 提出FALCON方法，利用信息论指导高效参数选择，通过对比正交去对齐进行细粒度激活操纵。
result: 在有害信息移除任务上，FALCON在保持模型实用性的前提下实现了更精确的遗忘效果。
conclusion: 细粒度激活操纵为模型编辑提供了一种有效且可扩展的安全治理方案。
---

## Abstract
Large language models have been widely applied, but can inadvertently encode sensitive or harmful information, raising significant safety concerns. Machine unlearning has emerged to alleviate this concern; however, existing training-time unlearning approaches, relying on coarse-grained loss combinations, have limitations in precisely separating knowledge and balancing removal effectiveness with model utility.  In contrast, we propose $\textbf{F}$ine-grained $\textbf{A}$ctivation manipu$\textbf{L}$ation by $\textbf{C}$ontrastive $\textbf{O}$rthogonal u$\textbf{N}$alignment (FALCON), a novel representation-guided unlearning approach that leverages information-theoretic guidance for efficient parameter selection, employs contrastive mechanisms to enhance representation separation, and projects conflict gradients onto orthogonal subspaces to resolve conflicts between forgetting and retention objectives. Extensive experiments demonstrate that FALCON achieves superior unlearning effectiveness while maintaining model utility, exhibiting robust resistance against knowledge recovery attempts.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
大型语言模型（LLM）在训练过程中可能无意中编码有害、偏见或敏感信息，引发严重的安全和合规问题（如GDPR“被遗忘权”）。现有的**训练时机器遗忘方法**大多依赖粗粒度的损失组合（如简单的梯度上升或混合损失），难以精确分离需要遗忘的知识与需要保留的知识，导致遗忘效果与模型通用能力之间难以平衡。此外，现有方法缺乏对模型内部表示层的可解释指导，且容易受到知识恢复攻击（如越狱攻击）。**FALCON**旨在通过细粒度的表示级操纵，实现精准、高效且鲁棒的知识移除。

## 2. 论文提出的方法论
### 核心思想
FALCON 是一个表示引导的遗忘框架，通过**信息论度量**指导参数选择，利用**对比学习**强制遗忘表示与保留表示分离，并通过**梯度正交投影**解决遗忘与保留目标之间的优化冲突。

### 关键技术细节
- **互信息（MI）引导的参数选择**：计算模型各层上遗忘数据集与保留数据集激活之间的互信息 I(F; R)（用KDE估计连续熵，PCA降维保持95%方差），选择互信息最小的层作为干预目标。低MI表示知识纠缠最小，适合遗忘操作。
- **对比表示遗忘**：构建**主偏移向量（POV）**，通过SVD提取激活的主方向，构造一个随机初始化但偏离主方向的向量作为“正样本”。对遗忘数据，用InfoNCE损失**LF**迫使更新模型的激活靠近POV而远离冻结模型的激活；对保留数据，用余弦相似度损失**LR**使更新模型激活与冻结模型激活对齐。
- **梯度正交投影**：当遗忘梯度与保留梯度方向冲突（余弦相似度<0）时，将遗忘梯度投影到保留梯度的正交补空间，消除干扰，然后加权组合得到最终更新方向。结合Sophia二阶优化器提升稳定性。

### 算法流程简示
1. **Step 1**：计算各层MI，选择最优层 \( l^* \)。
2. **Step 2**：在选定层上交替进行：
   - **2.1** 对比表示遗忘：对遗忘数据计算LF，对保留数据计算LR。
   - **2.2** 检查梯度冲突，若冲突则投影遗忘梯度使其与保留梯度正交。
3. **Step 3**：用调整后的梯度更新模型参数。

## 3. 实验设计
### 数据集与场景
| 任务 | 数据集 | 评估指标 |
|------|--------|----------|
| 有害知识遗忘 | WMDP（生物、网络子域） | WMDP分数（越低越好），MMLU（通用知识），PPL（困惑度） |
| 版权内容遗忘 | MUSE News（新闻文章） | forget_knowmem_ROUGE、forget_verbmem_ROUGE（越低越好），retain_knowmem_ROUGE（保留） |
| 实体遗忘 | TOFU（虚构实体，1%/5%/10%遗忘大小） | Forget Quality（FQ，越高越好），Model Utility（MU，保留能力） |
| 抗知识恢复 | 增强GCG攻击、Logit Lens探测 | 恢复后的WMDP分数 |

### 对比方法
- 有害遗忘：LLMU, SCRUB, SSD, RMU（来自WMDP基准）；还比较了Fine-tuned, Retain, GradAscent, GradDiff, NPO, SimNPO等。
- 版权/实体：GradAscent, GradDiff, IdkDPO, NPO, RMU等（来自OpenUnlearning框架）。

### 模型
Zephyr-7B-Beta, Yi-6B-Chat, Mistral-7B-Instruct-v0.3, Llama-2-7b-hf（版权）, Llama-3.2-1B-Instruct（实体）。

## 4. 资源与算力
论文**未明确说明**所使用的GPU型号、数量、训练时长等具体硬件资源。仅在附录提到实验在有限计算条件下进行，且使用了相对较小的模型（≤7B参数）。这限制了结果的直接可复现性。

## 5. 实验数量与充分性
- **实验数量**：涵盖三类主要遗忘任务（有害、版权、实体），每个任务均在多个模型上对比多种基线方法，并进行了对抗恢复评估（GCG攻击和Logit Lens探测）。此外附录包含消融研究（如不同层选择、梯度投影有效性等）。
- **充分性与公平性**：实验设计较全面，所有基线均使用官方实现或公开基准的默认设置。对比指标统一（WMDP、MMLU、PPL等）。作者声明由于LLM固有非确定性，未报告误差棒或统计显著性检验，但实验结果的趋势一致且明显。
- **潜在不足**：未在更大规模模型（如70B）上验证；未进行跨任务泛化的系统消融（如同时遗忘多个领域时的相互影响）。

## 6. 论文的主要结论与发现
- FALCON在所有遗忘任务上均取得了**最优或接近最优的遗忘效果**，同时保持了与基线相当的模型通用能力（MMLU和PPL）。
- **MI指导的参数选择**有效定位了知识纠缠最少的层，显著降低了梯度冲突并提高了遗忘效率。
- **对比正交去对齐机制**实现了比粗粒度损失组合更彻底的表示分离，且对知识恢复攻击（GCG、Logit Lens）具有鲁棒性。
- 在实体遗忘（TOFU）中，即使在仅10%遗忘数据下，FALCON也能平衡遗忘质量与模型效用，优于其他方法。

## 7. 优点
- **可解释性**：使用互信息量化知识纠缠，提供了参数选择的理论依据，避免了网格搜索。
- **细粒度操纵**：通过POV和对比学习直接操控表示方向，比传统损失组合更精准。
- **冲突解决**：梯度正交投影有效调和遗忘与保留目标的冲突，训练更稳定。
- **鲁棒性**：实验证明对多种知识恢复攻击有效，说明实现了真正的知识移除而非表面屏蔽。
- **跨域泛化**：在有害内容、版权、实体三种不同遗忘场景下均表现优异。

## 8. 不足与局限
- **实验规模有限**：仅在≤7B参数的文本LLM上验证，未在多模态或更大模型（如70B）上测试，泛化性存疑。
- **资源信息缺失**：未报告GPU型号、时耗等硬件细节，影响可复现性评估。
- **近似误差**：MI估计依赖KDE和PCA，在高维表示空间中可能存在偏差；POV构造中随机向量和扰动参数的选择未完全理论分析。
- **安全维度覆盖不全**：未讨论对模型公平性、偏见等其他安全属性的影响；抗恢复攻击仅测试了典型的GCG和Logit Lens，未覆盖更广泛的对抗手段。
- **无统计显著性报告**：未提供多次运行的变异性，尽管作者解释为LLM非确定性所致，但仍削弱了结论的统计稳健性。

（完）
