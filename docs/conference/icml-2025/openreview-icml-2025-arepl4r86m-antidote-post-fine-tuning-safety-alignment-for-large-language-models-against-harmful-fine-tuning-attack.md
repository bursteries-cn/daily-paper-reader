---
title: "Antidote: Post-fine-tuning Safety Alignment for Large Language Models against Harmful Fine-tuning Attack"
title_zh: Antidote：针对有害微调攻击的大语言模型微调后安全对齐
authors: "Tiansheng Huang, Gautam Bhattacharya, Pratik Joshi, Joshua Kimball, Ling Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Arepl4R86m"
tags: ["query:model-edit"]
score: 9.0
evidence: 微调后的安全对齐，对抗有害微调攻击
tldr: 现有防御在特定超参数下失效，Antidote提出微调后阶段的安全对齐方法，通过移除有害参数恢复模型安全性，且不受微调阶段超参数影响。实验表明该方法在各种攻击下均有效。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-arepl4r86m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 837, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arepl4r86m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 833, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arepl4r86m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arepl4r86m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1235, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arepl4r86m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 837, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-arepl4r86m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 498, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1589, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1588, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1586, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1588, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 695, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 849, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 856, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 682, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 871, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 853, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 856, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 858, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-arepl4r86m/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 852, \"height\": 255, \"label\": \"Table\"}]"
motivation: 现有防御在特定超参数下失效，需要一种鲁棒的微调后安全对齐方法。
method: 提出Antidote，在微调后通过检测和移除有害参数来恢复模型安全性，无需依赖微调阶段超参数。
result: 实验证明Antidote在不同超参数设置下均能有效恢复模型安全性。
conclusion: Antidote提供了一种与超参数无关的微调后安全对齐方案，增强了LLM对抗有害微调的鲁棒性。
---

## Abstract
Safety aligned Large Language Models (LLMs) are vulnerable to harmful fine-tuning attacks -- a few harmful data mixed in the fine-tuning dataset can break the LLMs's safety alignment. While several defenses have been proposed, our evaluation shows that existing defenses fail \textit{when some specific training hyper-parameters are chosen} -- a large learning rate or a large number of training epochs in the fine-tuning stage can easily invalidate the defense. To this end,  we propose Antidote, a post-fine-tuning stage solution, which remains \textbf{\textit{agnostic to the training hyper-parameters in the fine-tuning stage}}. Antidote relies on the philosophy that by removing the harmful parameters, the harmful model can be recovered from the harmful behaviors, regardless of how those harmful parameters are formed in the fine-tuning stage. With this philosophy, we introduce a one-shot pruning stage after harmful fine-tuning to remove the harmful weights that are responsible for the generation of harmful content. Despite its embarrassing simplicity, empirical results show that Antidote can reduce harmful score while maintaining accuracy on downstream tasks.

---

## 论文详细总结（自动生成）

# 论文总结：Antidote: 针对有害微调攻击的LLM微调后安全对齐

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：安全对齐的大型语言模型（LLM）在微调服务中易遭受“有害微调攻击”——用户上传的微调数据中混入少量有害样本即可破坏模型的安全对齐，使其拒绝有害指令的能力丧失。
- **现有防御局限**：已有对齐阶段防御（如Vaccine, RepNoise）和微调阶段防御（如Lisa, LDIFS）均对微调超参数高度敏感：当学习率大或训练轮数多时，防御效果显著下降，甚至完全失效。然而，大学习率和大轮数往往是保证下游任务精度的必要条件。
- **研究目标**：提出一种与微调超参数无关的防御方法，能够在微调完成后安全地恢复模型的安全性，不依赖微调阶段的具体设置。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：通过在微调后移除与有害内容生成最相关的“有害参数”，即可从有害行为中恢复模型，无论这些有害参数在微调阶段如何形成。
- **关键技术细节**：
  - **有害参数识别**：利用Wanda score评估每个参数对重新对齐数据集（有害提示-有害回答对）的重要性。Wanda score定义为权重绝对值与其输入激活范数的乘积的平均值（公式1）。
  - **有害掩码生成**：选取Wanda score最高的α比例参数，生成二值掩码m（公式2）。
  - **参数移除**：通过逐元素乘法将掩码对应的参数置零（即剪枝），得到恢复后的模型（公式3）。
- **算法流程（Algorithm 1）**：
  1. 输入：剪枝比例α、重新对齐数据集D_realign、有害微调后的模型权重w。
  2. 根据公式(1)计算重要性分数h(w, D_realign)。
  3. 用公式(2)生成top-α掩码m。
  4. 用公式(3)执行剪枝：˜w = (1 - m) ⊙ w。
  5. 输出恢复后的模型˜w。

## 3. 实验设计
- **数据集**：
  - 安全对齐数据：从BeaverTails中采样安全回答（is_safe=True）。
  - 微调数据：包含部分有害数据（is_safe=False）和下游任务数据（SST2, AGNEWS, GSM8K, AlpacaEval）。
  - 重新对齐数据：所有数据均为有害数据（与微调中的有害数据不同）。
- **模型 backbone**：Llama2-7B（默认），Mistral-7B, Gemma-7B, Llama3-8B。
- **对比方法**：
  - SFT（基线无防御）
  - 对齐阶段：Vaccine, RepNoise
  - 微调阶段：Lisa, LDIFS
- **评估指标**：
  - **有害分数（HS）**：使用BeaverTails的审核模型对1000个未见有害指令的输出进行标记，计算不安全输出的比例。
  - **微调精度（FA）**：在各任务测试集上的Top-1准确率（或AlpacaEval的胜率）。
- **默认设置**：n=5000样本，有害比例p=0.2，学习率lr=1e-4，epoch ep=20，LoRA rank=256。

## 4. 资源与算力
- **GPU**：所有实验使用NVIDIA H100 GPU。论文未明确说明使用数量（推测单卡）。
- **时间开销**（Table 10）：
  - Antidote总时间1.78小时（对齐0.92h + 微调0.78h + 后处理0.04h），仅为SFT的1.02倍。
  - 相比其他防御（Vaccine 2.63h, RepNoise 2.75h, Lisa 1.72h, LDIFS 2.11h），Antidote额外开销最小。
- **显存**：Antidote峰值显存35.45 GB，与SFT持平，远低于其他方法（如RepNoise 75.26 GB）。

## 5. 实验数量与充分性
- **实验组数量**：超过10组主要实验，涵盖：
  - 有害比例变化（p=0,0.05,0.1,0.2,0.5）
  - 微调样本数变化（n=100~5000）
  - 学习率变化（1e-7~1e-3）
  - 微调轮数变化（ep=1~40）
  - 良性微调攻击
  - 不同数据集（4种下游任务）
  - 不同模型（4种7B/8B模型）
  - 不同对齐数据集
  - 消融实验：mask ratio、重新对齐数据集必要性、重新对齐数据集大小
  - 扩展实验（组合Vaccine/Lisa）
  - 机制分析（有害嵌入漂移HED、输出logit漂移）
  - 系统性能评估
- **充分性评价**：实验覆盖了多种超参数、数据集、模型和攻击设置，设计较为全面。但缺少多次重复实验的标准差，可能随机性影响未充分展示。所有实验基于BeaverTails单一安全数据集，结论的泛化性有待更多安全数据集验证。

## 6. 主要结论与发现
- **有效性**：Antidote能显著降低有害分数（平均降低11~17%），同时保持下游任务精度（损失<2%）。
- **超参数鲁棒性**：在不同学习率、训练轮数、有害比例下，Antidote的有害分数保持稳定，而其他防御方法随超参数增大而严重退化。
- **机制理解**：Antidote通过剪枝有害参数，有效减小了模型在安全数据上的有害嵌入漂移（HED），并能在不严重干扰下游任务logit的情况下改变有害样本的logit。
- **组合优势**：将Antidote与对齐阶段防御Vaccine结合（V-S-A）可获得最佳效果。
- **系统高效**：仅增加少量后处理时间（0.04h），内存开销与SFT相同。

## 7. 优点（方法或实验设计亮点）
- **方法简洁且有效**：仅需一次前向传播计算Wanda score然后剪枝，无需复杂训练或额外优化，易于部署。
- **超参数无关性**：创新性地将防御从微调阶段移到微调后阶段，从根本上回避了超参数敏感问题。
- **实验设计全面**：系统评估了现有防御的超参数敏感性，并提供了丰富的对比和消融实验，论证充分。
- **机制分析深入**：通过HED和logit漂移可视化解释了剪枝为何有效。
- **系统性能优秀**：相比其他防御，Antidote几乎不增加时间和内存开销，实用性强。

## 8. 不足与局限
- **对重新对齐数据集的依赖**：需要收集有害提示-有害回答对，可能在某些场景下难以获得（但论文指出该假设在之前工作中已被接受）。
- **mask ratio需要手动调节**：不同任务可能需调整α以获得最优trade-off（实验显示α=0.05~0.2较合适）。
- **模型规模限制**：仅在7B/8B模型上实验，未验证更大规模（如70B）的效果。
- **缺乏统计显著性**：未报告多次运行的标准差，结果稳定性未知。
- **攻击类型覆盖不足**：仅考虑显式有害数据混合，未测试更隐蔽的攻击（如良性数据中隐含有害行为、对抗性提示等）。
- **安全数据集单一**：仅使用BeaverTails，可能无法代表真实世界的多样安全偏好。
- **未考虑模型能力退化**：剪枝可能影响模型在未测试任务上的通用能力，论文未做全面评估。

（完）
