---
title: Reinforced Lifelong Editing for Language Models
title_zh: 语言模型的强化终身编辑
authors: "Zherui Li, Houcheng Jiang, Hao Chen, Baolong Bi, Zhenhong Zhou, Fei Sun, Junfeng Fang, Xiang Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1jUXprrfcb"
tags: ["query:model-edit"]
score: 9.0
evidence: 基于超网络和强化学习的终身模型编辑
tldr: 针对现有超网络方法在终身编辑中与动态参数不兼容的问题，本文提出RLEdit，将编辑损失视为奖励，利用强化学习优化超网络参数，使其适应知识序列变化。实验表明，RLEdit在多次编辑后仍能保持模型性能，有效支持大规模知识更新，为模型编辑的实用化提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 884, \"height\": 858, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1704, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1745, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1juxprrfcb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1785, \"height\": 742, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1juxprrfcb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 777, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1juxprrfcb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1776, \"height\": 1135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1juxprrfcb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1224, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1juxprrfcb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1775, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1juxprrfcb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1764, \"height\": 1850, \"label\": \"Table\"}]"
motivation: 现有超网络在终身编辑中因参数动态变化而失效，需要一种能适应知识序列的方法。
method: 将超网络终身编辑建模为强化学习，用编辑损失作为奖励，优化超网络参数。
result: RLEdit在多个数据集上优于基线，支持数百次编辑，保持模型性能。
conclusion: 强化学习框架有效解决了超网络不适应动态参数的问题，提升了终身编辑的稳定性。
---

## Abstract
Large language models (LLMs) acquire information from pre-training corpora, but their stored knowledge can become inaccurate or outdated over time. Model editing addresses this challenge by modifying model parameters without retraining, and prevalent approaches leverage hypernetworks to generate these parameter updates. However, they face significant challenges in lifelong editing due to their incompatibility with LLM parameters that dynamically change during the editing process. To address this, we observed that hypernetwork-based lifelong editing aligns with reinforcement learning modeling and proposed **RLEdit**, an RL-based editing method. By treating editing losses as rewards and optimizing hypernetwork parameters at the full knowledge sequence level, we enable it to precisely capture LLM changes and generate appropriate parameter updates. Our extensive empirical evaluation across several LLMs demonstrates that RLEdit outperforms existing methods in lifelong editing with superior effectiveness and efficiency, achieving a **59.24%** improvement while requiring only **2.11%** of the time compared to most approaches.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **背景**：大语言模型（LLMs）在预训练中获取的知识可能过时或不准确，需要通过模型编辑来更新参数而不重新训练。超网络（hypernetwork）方法能够高效生成参数更新，但在**终身编辑**（lifelong editing，即连续多次编辑）场景中，由于LLM参数在编辑过程中动态变化，超网络与当前LLM参数不兼容，导致编辑效果急剧下降（通常只能支持约100次编辑）。
- **问题**：如何让超网络持续适应动态变化的LLM，在数千乃至数万次编辑后仍保持有效性和模型原有能力。
- **整体含义**：提出**RLEdit**，首次将超网络终身编辑建模为**强化学习（RL）**问题，通过将编辑损失视为奖励、用RL优化超网络参数，使其能够感知LLM状态并自适应生成更新，从而大幅提升终身编辑的规模和稳定性。

### 2. 论文提出的方法论
- **核心思想**：将超网络在终身编辑中的训练过程建模为**马尔可夫决策过程（MDP）**：
  - **智能体（agent）**：超网络 \(H\)（参数 \(\theta\)）
  - **环境（environment）**：LLM \(f_W\)
  - **状态（state）**：当前LLM参数 \(W_{t-1}\) 及待编辑知识 \((x_t, y_t)\)，具体表示为梯度 \(\nabla W_{t-1}\)
  - **动作（action）**：超网络生成的参数更新 \(\tilde{\nabla}W_t\)
  - **奖励（reward）**：基于编辑损失设计的函数 \(r_t\)
- **关键技术细节**：
  - **MDP建模**：每个时间步 \(t\)，LLM状态仅依赖前一时刻，满足马尔可夫性；超网络根据当前状态产生动作，环境转移后给出奖励。
  - **奖励函数设计**：
    - **基本组件**：目标知识编辑损失 \(L_e\) + 无关知识保持损失 \(L_{loc}\)（KL散度）
    - **记忆回溯组件**：为保持已编辑知识，回顾前 \(k\) 个知识样本的损失，用指数衰减因子 \(\mu\) 加权
    - **正则化组件**：对 \(\|\tilde{\nabla}W\|_2\) 加惩罚，限制更新幅度，保护模型通用能力
    - 最终奖励 \(r_t = -(L_{base}^t + L_{back}^t + \eta \|\tilde{\nabla}W_t\|_2)\)
  - **训练策略**：采用**离线策略更新**——遍历整个训练序列后，用累积总奖励 \(J = \sum_i \gamma^i r_i\) 一次性优化超网络参数，避免在线更新带来的过拟合和低效。
- **算法流程**（伪代码已在论文Algorithm 1给出）：
  1. 随机采样知识序列
  2. 对每个知识，计算前向损失并回传得到梯度
  3. 超网络根据梯度生成更新 \(\tilde{\nabla}W_t\)，并更新LLM参数
  4. 在当前LLM上计算奖励（包含记忆回溯）
  5. 遍历完整序列后，计算总奖励 \(J\)，反向传播优化超网络参数
  6. 重复多轮直至收敛

### 3. 实验设计
- **数据集**：三个标准编辑数据集：
  - **ZsRE**（零样本关系抽取）
  - **FEVER**（事实验证）
  - **CounterFact**（矛盾事实）
- **评测指标**：Efficacy（编辑成功率）、Generalization（对同义表达泛化能力）、Specificity（无关知识保持能力），以及**通用能力**（6个GLUE任务：SST、MMLU、MRPC、CoLA、RTE、NLI的F1分数）和**时间效率**。
- **baseline方法**：
  - 传统单步编辑：FT、ROME、MEMIT
  - 超网络方法：MEND、MALMEN、DAFNet；以及MEND*、MALMEN*（每次编辑前重训超网络）
  - 顺序编辑方法：PRUNE、RECT、AlphaEdit
- **实验配置**：在Llama-3-8B、Gemma-2-9B、Mistral-7B-v0.3三个8B级LLM上进行；编辑规模从20×100到200×100（即2000到20000次编辑不等）。

### 4. 资源与算力
- 论文明确说明：“大多数实验在单个NVIDIA A100 (80GB) GPU上运行”。
- 未提供具体训练时长，但给出了每样本平均编辑时间（RLEdit为0.22秒左右）及总时间对比（初始设置+编辑时间，RLEdit仅需0.145秒/样本，比其他方法快数十倍）。

### 5. 实验数量与充分性
- **数量丰富**：包含：
  - 三个数据集、三个LLM的完整对比（Table 2）
  - 四种不同编辑规模（20×100、50×100、100×100、150×100）的扩展实验（Table 5, Figure 3）
  - 消融研究（B.1节，Table 4）：去除RL框架、记忆回溯、正则化
  - 通用能力测试（Figure 5）
  - 与其他超网络方法集成实验（Figure 6）
  - 不同批次大小和编辑频率的影响实验（Figure 8）
- **充分性与公平性**：
  - 同类方法均采用相同超参数配置（按原论文设置），并报告多次实验的均值和标准差。
  - 时间测量考虑初始设置成本（协方差矩阵计算或超网络训练），保证对比公平。
  - 但仅在8B级模型上实验，未在更大模型（如70B）上验证，存在一定局限。

### 6. 主要结论与发现
- RLEdit在**所有评测指标**上显著优于现有方法，平均提升Efficacy 66%、Generalization 65%、Specificity 40%。
- 效率极高：仅需2.11%的对比方法时间（0.22秒/样本 vs 6~8秒/样本）。
- 能在超过**20000次编辑**后仍保持良好性能，而基线在几百次编辑后崩溃。
- 通用能力几乎不受影响（GLUE F1分数保持与预训练模型一致）。
- 可作为**即插即用模块**提升MEND、MALMEN等超网络方法的终身编辑能力。

### 7. 优点
- **创新性**：首次将终身编辑建模为RL问题，巧妙利用MDP自然契合编辑过程。
- **设计合理**：记忆回溯组件有效缓解知识遗忘；正则化保护通用能力；离线更新避免过拟合。
- **高效可扩展**：极短的每样本编辑时间，支持大规模编辑序列。
- **通用性**：可集成到多种超网络架构，不依赖特定网络结构。

### 8. 不足与局限
- **实验覆盖有限**：仅评估事实知识编辑（单跳），未涉及多跳推理、关系知识、领域知识（如医学、法律）等更复杂场景。
- **模型规模局限**：仅在8B级模型上测试，未验证在更大模型（如70B、130B）上的扩展性。
- **潜在安全风险**：直接修改参数可能被用于注入虚假或有害信息，论文虽提及需严格监管，但未提供防护机制。
- **超参数敏感性**：编辑层数（Layer）对性能影响较大，需手动调优（论文在附录A.5指出）。
- **资源开销**：虽然单次编辑时间短，但超网络训练仍需一定计算成本（尤其在很大批次时GPU内存消耗高）。

（完）
