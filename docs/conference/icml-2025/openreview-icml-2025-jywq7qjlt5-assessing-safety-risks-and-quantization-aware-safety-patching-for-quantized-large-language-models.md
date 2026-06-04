---
title: Assessing Safety Risks and Quantization-aware Safety Patching for Quantized Large Language Models
title_zh: 量化大型语言模型的安全风险评估与量化感知安全补丁
authors: "Kejia Chen, Jiawen Zhang, Jiacong Hu, Yu Wang, Jian Lou, Zunlei Feng, Mingli Song"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=jywq7qJLt5"
tags: ["query:model-edit"]
score: 5.0
evidence: 量化模型的安全风险与量化感知安全补丁
tldr: 量化部署可能削弱大模型的安全能力。本文系统评估了多种量化技术下的安全风险，并提出Q-resafe框架，通过量化感知的安全补丁高效恢复模型安全性。实验表明该方法在保持量化效率的同时有效修复了安全漏洞。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jywq7qjlt5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1538, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jywq7qjlt5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1592, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jywq7qjlt5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1594, \"height\": 529, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 799, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1568, \"height\": 887, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 866, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1608, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 672, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 749, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 690, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1708, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1118, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 788, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1416, \"height\": 998, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1476, \"height\": 997, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jywq7qjlt5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1245, \"height\": 1013, \"label\": \"Table\"}]"
motivation: 量化可能降低LLM安全性，缺乏系统性评估与缓解方案。
method: 提出量化感知的安全补丁框架Q-resafe，修复模型安全漏洞。
result: 在不牺牲量化效率的前提下显著提升安全性。
conclusion: 量化感知补丁为量化模型的安全部署提供了有效方案。
---

## Abstract
Quantized large language models (LLMs) have gained increasing attention and significance for enabling deployment in resource-constrained environments. However, emerging studies on a few calibration dataset-free quantization methods suggest that quantization may compromise the safety capabilities of LLMs, underscoring the urgent need for systematic safety evaluations and effective mitigation strategies. In this paper, we present comprehensive safety evaluations across various mainstream quantization techniques and diverse calibration datasets, utilizing widely accepted safety benchmarks. To address the identified safety vulnerabilities, we propose a quantization-aware safety patching framework, Q-resafe, to efficiently restore the safety capabilities of quantized LLMs while minimizing any adverse impact on utility.  Extensive experiment results demonstrate that Q-resafe successfully re-aligns the safety of quantized LLMs with their pre-quantization counterparts, even under challenging evaluation scenarios. Project page: https://github.com/Thecommonirin/Qresafe.

---

## 论文详细总结（自动生成）

# 中文详细总结

## 1. 核心问题与整体含义
- **研究动机**：量化技术使大型语言模型（LLM）能够在资源受限环境中部署，但已有研究表明，部分无需校准数据集的量化方法可能削弱模型的安全能力（如生成有害内容、更容易被越狱攻击）。目前缺乏对主流量化技术及不同校准数据集下安全风险的系统性评估，也缺少有效的缓解策略。
- **整体含义**：论文旨在系统评估量化LLM的安全退化程度，并提出一种量化感知的安全补丁框架（Q‑resafe），在不明显牺牲模型实用性的前提下高效恢复量化模型的安全性，推动量化LLM的可靠部署。

## 2. 方法论
- **核心思想**：利用预量化LLM（全精度）的强安全能力引导量化模型修复安全缺陷。保留大部分量化权重以维持效用，仅选择性更新“安全关键权重”。
- **关键技术细节**：
  - **安全补丁数据集构建**：对校准数据集中的每个提示 `x`，分别从预量化LLM `π_W` 和量化模型 `π_{Q0}` 生成响应，将前者标记为优胜响应 `y_w`、后者为劣响应 `y_l`，构成偏好三元组 `(x, y_w, y_l)`。此方式无需人工标注，利用知识蒸馏传递安全能力。
  - **DPO优化目标**：使用直接偏好优化（DPO）损失函数，约束量化模型输出偏好于优胜响应，同时通过KL正则化避免与原始量化模型偏差过大。
  - **安全关键权重识别**：采用SNIP分数计算每个权重的安全重要性：`I(W_{ij}, x) = |W_{ij}·∇_{W_{ij}} L(x)|`，其中`L(x)`为条件负对数似然。取校准数据集上的平均分数，选择分数最高的 `τ` 百分位权重作为安全关键权重，通过二进制掩码 `M_Q` 标记。
  - **LoRA结构更新**：量化模型的更新限制为低秩适应（LoRA）形式 `Q = Q0 + Quant(M_Q ⊙ AB)`，仅对掩码对应的LoRA矩阵 `A, B` 进行梯度更新，其余权重保持不变。每隔 `K` 步重新识别安全关键权重。
- **算法流程（Algorithm 1）**：
  1. 从校准数据集 `D_calib` 生成偏好三元组，构建 `D_patch`。
  2. 初始化LoRA矩阵 `A, B`。
  3. 循环迭代 `T` 步：
     - 每 `K` 步重新计算安全关键权重掩码 `M_Q`，并映射为 `M_A, M_B`。
     - 计算DPO损失关于 `A, B` 的梯度，仅更新掩码位置：`A_{t+1} = M_A ⊙ (A_t - η∇A L) + (1-M_A)⊙A_t`，类似更新 `B`。
     - 更新量化权重 `Q_{t+1} = Q0 + Quant(A_{t+1}B_{t+1})`。
  4. 输出补丁后的量化权重 `Q_T`。

## 3. 实验设计
- **数据集**：
  - **校准数据集（用于评估和补丁）**：根据风险等级分为三类：Risk‑I（良性，来自UltraChat）、Risk‑II（间接有害，基于AdvBench构造的身份转换示例）、Risk‑III（直接有害，AdvBench中的有害指令-响应对）。
  - **安全评估**：使用AdvBench计算攻击成功率（ASR）；效用评估使用MT‑Bench和AlpacaEval。
- **基准方法**：对比四种主流量化方法——AWQ（PTQ，无微调）、AQLM（PTQ，需微调）、LLM‑QAT（QAT，全参数微调）、QLoRA（QAT，参数高效微调）。同时比较了基线（预量化FP16模型）。
- **模型**：Llama‑2‑7B‑Chat 和 Gemma‑7B‑Instruct。
- **位宽**：INT4和INT8（部分实验含2‑bit、3‑bit）。
- **评估指标**：ASR（越低越好）、MT‑Bench分数、AlpacaEval胜率。

## 4. 资源与算力
- 论文明确说明：实验基于 **4 块 NVIDIA A100 40GB GPU**，使用 PyTorch 和 Hugging Face Transformers 框架。
- 训练时长：附录A.1中给出了超参数（LoRA r=128, α=256, DPO β=0.01, 学习率5e-6），但 **未统一报告各实验的具体训练时长**。消融实验中提及Q‑resafe仅需1.2 GPU小时（相比于SFT的3.4小时、DPO的3.8小时），但仅为特定设置下的对比。

## 5. 实验数量与充分性
- **实验数量**：涵盖了多种量化方法、两种模型（Llama‑2和Gemma）、两种位宽（INT4/INT8）、三种风险级别的校准数据集、多种解码策略（温度、top‑p、top‑k）下的ASR评估。此外进行了多组消融实验：安全关键权重比例τ的影响、不同微调方法（SFT/DPO/Q‑resafe）的对比、混合精度及更多位宽（2‑bit/3‑bit）的测试、以及多种bitsandbytes库中的量化方法（LLM.int8(), NF4, FP4）。
- **充分性与客观性**：实验覆盖主流量化类别和常见模型，风险评估与全精度LLM评估标准一致，对比公平。消融实验验证了各组件必要性。但仅针对两个7B规模模型，未涵盖更大模型或其他架构，存在一定覆盖偏差。

## 6. 主要结论与发现
- 所有量化技术均导致安全能力下降，其中PTQ方法（如AWQ）下降更严重；QAT方法在良性校准数据集下稍好。
- 校准数据集中的有害样本（Risk‑II、Risk‑III）会显著加剧安全退化，间接有害数据集（身份转换）的危害甚至超过直接有害数据。
- 低位宽（INT4）比高位宽（INT8）安全风险更高。
- 提出的 **Q‑resafe 能够将量化模型的安全性恢复到接近预量化水平**，在几乎所有测试场景下ASR仅增加1–14个百分点（对比基线方法可增加超80个百分点），同时保持MT‑Bench和AlpacaEval分数几乎不变。
- 安全关键权重识别（SNIP分数）对效率和安全恢复至关重要：若不使用（τ=0），ASR从1.6%飙升至42.2%；更新20%权重即可取得较好效果。

## 7. 优点
- **系统性**：首次覆盖多种量化类型（PTQ/QAT）、多种校准数据集（三个风险等级）和多种位宽的全面安全评估。
- **方法高效**：Q‑resafe通过知识蒸馏构建偏好数据，避免人工标注；仅更新安全关键权重，训练速度快（1.2 GPU小时），且不牺牲量化模型的效用。
- **泛化性好**：对多种量化方法（AWQ, AQLM, LLM‑QAT, QLoRA等）均有效，且可推广到其他低比特格式。
- **消融完整**：对τ、不同微调方法、位宽等进行了深入分析，验证设计合理性。

## 8. 不足与局限
- **模型与规模覆盖不足**：仅评估了Llama‑2‑7B‑Chat和Gemma‑7B‑Instruct两个7B模型，未验证更大模型（如13B/70B）或其他架构（如Mistral、Falcon）。
- **位宽有限**：主要评估INT4/INT8，对更低比特（如2‑bit）仅做了初步消融，未深入分析。
- **依赖性**：Q‑resafe需要预量化LLM（或同等强安全模型）作为教师，若教师模型不可用，则无法直接应用。
- **未考虑其他安全威胁**：仅针对有害指令生成（越狱）的安全风险，未评估其他维度（如歧视、隐私泄露、对抗鲁棒性等）。
- **实验客观性讨论**：ASR测量可能受解码策略影响，论文采用了多种解码设置并取最高ASR，但评价方式仍可能受GPT‑4作为judge的偏差影响。另外，未报告实验结果的标准差或置信区间。

（完）
