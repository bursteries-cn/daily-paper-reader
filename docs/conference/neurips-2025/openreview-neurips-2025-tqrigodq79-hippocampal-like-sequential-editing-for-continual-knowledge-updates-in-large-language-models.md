---
title: Hippocampal-like Sequential Editing for Continual Knowledge Updates in Large Language Models
title_zh: 类海马体顺序编辑：大语言模型的持续知识更新
authors: "Quntian Fang, Zhen Huang, Zhiliang Tian, Minghao Hu, Dongsheng Li, Yiping Yao, Xinyue Fang, Menglong Lu, Guotong Geng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=tqriGodQ79"
tags: ["query:model-edit"]
score: 9.0
evidence: 受海马体启发的顺序编辑方法用于持续知识更新
tldr: 现有模型编辑方法在顺序编辑场景中因参数漂移导致模型崩溃和能力退化。本文受海马体三突触回路启发，提出类海马体顺序编辑框架，通过模拟记忆与遗忘的神经机制来平衡新知识获取与旧知识保留。在多个基准上，该方法显著优于现有顺序编辑方法，在保持模型通用能力的同时实现了持续知识更新。该工作为模型编辑的终身学习提供了生物启发式解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1364, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1399, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1430, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 926, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1165, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 985, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-tqrigodq79/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1344, \"height\": 367, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1145, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 509, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1377, \"height\": 1228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1356, \"height\": 736, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1399, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-tqrigodq79/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1426, \"height\": 436, \"label\": \"Table\"}]"
motivation: 现有模型编辑方法在连续编辑时因参数漂移引发灾难性遗忘和通用能力下降。
method: 借鉴海马体三突触回路机制，设计包含记忆巩固和遗忘抑制的顺序编辑框架。
result: 在多个顺序编辑任务中，该方法在编辑成功率上超过现有方法，同时保持了模型原有性能。
conclusion: 生物启发的记忆机制有效解决了顺序编辑中的参数漂移问题，为持续知识更新提供了新路径。
---

## Abstract
Large language models (LLMs) are now pivotal in real-world applications. Model editing has emerged as a promising paradigm for efficiently modifying LLMs without full retraining. However, current editing approaches face significant limitations due to parameter drift, which stems from inconsistencies between newly edited knowledge and the model's existing knowledge. In sequential editing scenarios, cumulative drifts progressively lead to model collapse characterized by general capability degradation and balance between acquiring new knowledge and catastrophic forgetting of existing knowledge. Drawing inspiration from the hippocampal trisynaptic circuit for continual memorizing and forgetting, we propose a Hippocampal-like Sequential Editing (HSE) framework that designs the unlearning of obsolete knowledge, domain-specific knowledge update separation and replay for edited knowledge. Specifically, the HSE framework designs three core mechanisms: (1) Machine unlearning selectively erases outdated knowledge to facilitate integration of new information, (2) Fisher Information Matrix-guided parameter updates prevents cross-domain knowledge interference, and (3) Parameter replay consolidates long-term editing memory through lightweight and global replay of editing data in a parametric form. Theoretical analysis demonstrates that HSE achieves smaller generalization error bounds, more stable convergence and higher computational efficiency. Experimental results validate its effective balance between acquiring new knowledge and mitigating catastrophic forgetting, maintaining or even slightly enhancing general capabilities. In practical applications, experiments confirm its effectiveness in multi-domain hallucination mitigation, healthcare knowledge injecting, and societal bias reduction.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有大语言模型（LLM）的模型编辑方法在**顺序编辑**（sequential editing）场景中面临严重的**参数漂移**问题——新编辑的知识与模型已有知识不一致，导致累积性矛盾，最终引发模型通用能力下降和**灾难性遗忘**。这限制了模型编辑在动态、持续更新环境中的实际部署。
- **研究动机**：生物系统中的海马体具有高效的持续记忆与遗忘机制（如三突触回路DG→CA3→CA1），能够通过突触可塑性、模式分离和记忆重放实现终身学习。受此启发，作者希望设计一种类海马体的顺序编辑框架，兼顾新知识获取与旧知识遗忘/保留。
- **整体含义**：提出一种生物启发的参数修改型顺序编辑方法HSE，能够在不损害通用能力的前提下，连续编辑LLM的知识，并有效缓解参数漂移和灾难性遗忘。

### 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：模拟海马体三突触回路的三种机制：主动遗忘（对应LTD）、知识更新分离（对应DG模式分离）和长期记忆巩固（对应CA3→CA1锐波涟漪重放）。

**关键技术细节**（公式部分用文字说明）：
1. **记忆导向主动遗忘（Memory-directed Active Forgetting）**：  
   针对编辑数据与旧知识冲突的问题，使用**机器遗忘（unlearning）** 来降低模型对过时知识的预测概率。具体通过**非似然损失（Unlikelihood Loss）** 与常规交叉熵损失结合，构成**MAF损失**（公式6）：  
   \( L_{MAF} = -\alpha \sum \log p(y|x) - (1-\alpha) \sum \log[1-p(\tilde{y}|x)] \)  
   其中α平衡记忆与遗忘。理论上证明MAF损失的泛化误差上界比交叉熵损失更紧。

2. **记忆稳定性保持（Memory Stability Preservation via Fisher Information Matrix）**：  
   为解决不同领域编辑数据间的干扰，使用**Fisher信息矩阵（FIM）** 来约束参数更新的幅度。在贝叶斯框架下，通过拉普拉斯近似得到后验的高斯分布，从而在损失中添加FIM正则项（公式16）：  
   \( L_\delta = L_{MAF} + \frac{1}{2}\delta^T \sum_{i=1}^{n-1}(\lambda_i F_{e_i}) \delta \)  
   高Fisher值的参数更新幅度小，保护已有知识。

3. **渐进式记忆巩固（Progressive Memory Consolidation via Parameter Replay）**：  
   通过**参数重放（parametric replay）** 避免灾难性遗忘。推导闭式解（定理2），增量更新矩阵Δ_i = δ_i K_i^T (C_0 + α_i Cov_sum_{i-1} + K_i K_i^T)^{-1}，其中Cov_sum累积历史编辑的协方差作为长期记忆，α_i为收敛因子（例如α_i = n/(i-1)），保证Frobenius范数收敛（引理2）。

**算法流程**（文字说明）：  
- 定位编辑层（早期FFN的第二线性层）；  
- 从Wikipedia采样通用知识对(K0, V0)；  
- 对每个编辑样本，生成键k_i和值v_i（通过可学习增量δ_i）；  
- 使用MAF损失+FIM正则更新δ_i；  
- 计算累加协方差Cov_sum；  
- 通过闭式解更新权重矩阵W_i = W_{i-1} + Δ_i。

### 3. 实验设计：数据集、benchmark、对比方法

- **主要数据集**：  
  - **CounterFact**（反事实填空）  
  - **ZsRE**（问答数据集）  
  - **GLUE benchmark**（6个任务：SST、MRPC、MMLU、RTE、COLA、NLI）评估通用能力  
  - **HalluEdit**（9个领域幻觉缓解）  
  - **SafeEdit**（社会偏见减少）  
  - **MQUAKE-CF**（多跳问答）

- **对比基线（baselines）**：  
  - 参数保持型：GRACE  
  - 参数修改型：FT-L、MEND、ROME、MEMIT、PRUNE、RECT、**AlphaEdit**（作为HSE的特例）  
  - 额外对比：F-learning（类似“先遗忘后学习”方法）

- **评估指标**：Efficacy（编辑成功率）、Generalization（改写泛化）、Specificity（邻域特异性）、Fluency（流畅性）、Consistency（一致性），以及GLUE的F1分数等。

### 4. 资源与算力

- **GPU**：A100 80GB  
- **训练时间**：每个模型进行1,000次顺序编辑约**5小时**  
- **模型规模**：Llama3-8B-Instruct、Mistral-7B-Instruct-v0.3、GPT-J-6B、GPT2-XL-1.5B（最大8B参数）  
- 文中并未明确说明使用的GPU数量，仅提及单卡A100 80GB。

### 5. 实验数量与充分性

- **实验组数**：非常丰富，包括：  
  - 4种LLM × 2个主要数据集（CounterFact、ZsRE）的主实验（图2）；  
  - 通用能力GLUE评测（图3）；  
  - 3个实际应用场景（幻觉、医疗知识注入、偏见减少）（图4-6）；  
  - 完整的消融实验（表2）：分别去掉主动遗忘、FIM、长期记忆模块，并用经验重放对比；  
  - 超参数敏感测试（表7、表8）：α、λ_i、α_i；  
  - 与MEMIT_full的批量编辑对比（表4）；  
  - 多跳问答MQUAKE（表6）；  
  - 时间复杂度分析（表3）；  
  - 案例展示（附录F）。  

- **充分性评估**：实验设计全面，覆盖了标准基准、通用能力、实际应用、消融、超参数、可扩展性等方面，对比方法包括主流baseline，结果均报告误差条，实验客观公平。但未在更大规模模型（>8B）上验证，算力限制是明显不足。

### 6. 论文的主要结论与发现

- HSE在所有benchmark上显著优于现有方法：相比最优baseline，在CounterFact/ZsRE上平均提升Generalization 20.6%、Specificity 21.9%、Efficacy 17.3%。  
- 在顺序编辑后，HSE几乎完全保持甚至略微提升LLM的通用能力（GLUE任务上平均提升1.67%当编辑正确知识），而其他方法性能在几百步后骤降为零。  
- 理论分析证明MAF损失泛化误差上界更紧（推论1），参数重放保证Frobenius范数收敛（推论2），Fisher矩阵有效分离不同领域知识。  
- 实际应用中，HSE在幻觉缓解、医疗知识更新、偏见减少方面均优于基线，验证了其实用价值。

### 7. 优点

- **生物启发的创新方法论**：首次将海马体三突触回路机制（主动遗忘、模式分离、记忆重放）统一引入顺序模型编辑，每个模块都有明确的神经科学对应和理论支撑。  
- **理论扎实**：提供了泛化误差、收敛性的详细数学证明，强化了方法的可靠性。  
- **实验全面且结果亮眼**：在多个模型、数据集、实际场景中验证，且能同时保持通用能力，这是现有方法做不到的。  
- **轻量高效**：参数重放仅需累加协方差矩阵，无需存储大量数据，时间复杂度O(n)（顺序编辑），远低于批量编辑MEMIT_full的O(n²)。  
- **开源代码**：提供了可复现的代码库。

### 8. 不足与局限

- **模型规模受限**：实验仅进行到8B参数模型，未在更大规模（如70B）上验证，泛化性有待确认。  
- **未深入长文本/推理场景**：虽然测试了多跳问答，但论文承认未广泛探索长文本生成或复杂推理（如思维链编辑）场景。  
- **Fisher矩阵计算开销**：虽然理论若O(n)，但实际对每个编辑都需要计算一次FIM，在极大规模顺序编辑（如百万级）时可能成为瓶颈。  
- **收敛因子α_i需人工设定**：文中采用n/(i-1)并做了消融，但最优选择可能依赖数据分布，缺乏自适应机制。  
- **实际应用偏差风险**：虽然缓解了偏见，但若编辑恶意知识也可能被滥用（作者在伦理部分提及）。  
- **未与所有最新方法对比**：例如AnyEdit仅在多跳数据中对比，未在主实验中对比，且缺乏与更多参数保持型方法（如WISE）的直接比较。

（完）
