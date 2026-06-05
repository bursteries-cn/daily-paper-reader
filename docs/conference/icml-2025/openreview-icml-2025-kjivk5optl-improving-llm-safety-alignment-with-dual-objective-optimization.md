---
title: Improving LLM Safety Alignment with Dual-Objective Optimization
title_zh: 通过双目标优化改善大语言模型安全对齐
authors: "Xuandong Zhao, Will Cai, Tianneng Shi, David Huang, Licong Lin, Song Mei, Dawn Song"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Kjivk5OPtL"
tags: ["query:model-edit"]
score: 8.0
evidence: 双目标优化分离拒绝训练和知识遗忘，类似于安全模型编辑
tldr: 现有安全对齐方法易受越狱攻击。本文分析DPO在拒绝学习上的不足，提出双目标优化：鲁棒拒绝训练鼓励即使部分有害输出也拒绝，以及针对性遗忘有害知识。该方法显著提升对多种越狱攻击（如前缀、后缀、提示注入）的鲁棒性，是一种有效利用知识编辑的安全对齐方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1410, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1699, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 851, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 852, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 848, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 842, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1683, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1249, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1244, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kjivk5optl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1596, \"height\": 486, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kjivk5optl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 349, \"label\": \"Table\"}]"
motivation: DPO在拒绝学习上存在不足，导致易受越狱攻击。
method: 将DPO目标分离为鲁棒拒绝训练和针对性有害知识遗忘。
result: 在多种越狱攻击下显著提升LLM鲁棒性。
conclusion: 双目标优化是一种有效的安全对齐改进，其中有害知识遗忘部分类似模型编辑。
---

## Abstract
Existing training-time safety alignment techniques for large language models (LLMs) remain vulnerable to jailbreak attacks. Direct preference optimization (DPO), a widely deployed alignment method, exhibits limitations in both experimental and theoretical contexts as its loss function proves suboptimal for refusal learning. Through gradient-based analysis, we identify these shortcomings and propose an improved safety alignment that disentangles DPO objectives into two components: (1) robust refusal training, which encourages refusal even when partial unsafe generations are produced, and (2) targeted unlearning of harmful knowledge. This approach significantly increases LLM robustness against a wide range of jailbreak attacks, including prefilling, suffix, and multi-turn attacks across both in-distribution and out-of-distribution scenarios. Furthermore, we introduce a method to emphasize critical refusal tokens by incorporating a reward-based token-level weighting mechanism for refusal learning, which further improves the robustness against adversarial exploits. Our research also suggests that robustness to jailbreak attacks is correlated with token distribution shifts in the training process and internal representations of refusal and harmful tokens, offering valuable directions for future research in LLM safety alignment. The code is available at https://github.com/wicai24/DOOR-Alignment.

---

## 论文详细总结（自动生成）

# 论文总结：Improving LLM Safety Alignment with Dual-Objective Optimization

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：现有大语言模型（LLM）的安全对齐方法（如直接偏好优化，DPO）在对抗越狱攻击时仍然脆弱。DPO在拒绝学习任务中存在系统性缺陷：其损失函数导致安全响应的学习率过早饱和，且对分布外（OOD）输入泛化能力差，容易被前缀填充、后缀攻击、多轮对话等越狱手段绕过。
- **整体含义**：本文旨在通过理论分析DPO的梯度动态，提出一种双目标优化框架（DOOR），以鲁棒拒绝训练和有害知识定向遗忘为核心，从根本上提升LLM对多种越狱攻击的鲁棒性，同时保持通用能力。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将DPO的单一目标解耦为两个互补目标：①**鲁棒拒绝训练**——通过数据增强让模型学会在生成部分有害内容后“悬崖勒马”，强制输出拒绝；②**有害知识定向遗忘**——利用负偏好优化（NPO）削弱模型生成有害内容的能力。此外，**W-DOOR** 进一步引入基于奖励的token级权重，强化关键拒绝token（如“Sorry”“cannot”）的学习。
- **关键技术细节**：
  - **鲁棒拒绝训练**：对每个有害提示 \(x\)，在其后拼接有害响应 \(y_h\) 的前 \(k\) 个token（\(k\) 从1到\(C\)均匀采样），形成增强输入 \(x' = x \oplus y_{h,<k}\)，然后训练模型输出安全拒绝响应 \(y_s\)（使用标准交叉熵损失）。
  - **定向遗忘（NPO）**：对有害响应 \(y_h\) 使用NPO损失：`L_NPO = - (2/β) E[log σ(-β log (π_θ(y_h|x) / π_ref(y_h|x)))]`，该损失比梯度上升更稳定。
  - **DOOR总损失**：`L_DOOR = E[ -log π_θ(y_s | x⊕y_{h,<k}) - (2/β) log σ(-β log (π_θ(y_h|x) / π_ref(y_h|x))) ]`。
  - **W-DOOR**：将鲁棒拒绝训练中的交叉熵替换为token级加权版本，权重 \(\beta_t = (π^*(y_t|x,y_{<t}) / π_ref(y_t|x,y_{<t}))^{1/τ}\)，其中 \(π^*\) 由DPO对齐模型近似，\(\tau\) 为温度参数。权重高的token（如“Sorry”）获得更大梯度更新。
  - **保留损失**：为保持通用能力，加入标准SFT损失 `L_Retain = E[-log π_θ(y|x)]`，总损失为 `L_Total = α L_Align + (1-α) L_Retain`（实验中α=0.2）。
- **算法流程**（文字描述）：
  1. 使用部分HEx-PHI数据微调一个“越狱”模型以生成有害响应。
  2. 构建安全数据集：原始提示+安全响应（来自已对齐模型）和有害响应（来自越狱模型）。
  3. 对每个有害提示，随机选择其有害响应的前k个token作为前缀，与提示拼接。
  4. 使用DOOR或W-DOOR损失（含保留损失）训练模型10个epoch。

## 3. 实验设计：数据集、Benchmark、对比方法
- **训练数据**：
  - 安全相关数据：SORRY-Bench（450条有害指令，取子集）和HEx-PHI（330条，取子集220条）。
  - 有害响应：由微调的越狱模型生成，并人工验证。
  - 通用能力数据：来自Alpaca（400条）。
- **评估数据**：
  - **安全性**：
    - SORRY-Bench（held-out子集）：单轮拒绝鲁棒性。
    - Multi-Turn SORRY-Bench（使用Crescendo生成多轮对话）。
    - HarmBench（含GCG和AutoDAN后缀攻击）。
  - **过拒绝**：XSTest（350条安全查询）。
  - **通用能力**：MMLU、HellaSwag。
- **对比方法**：
  - 基础方法：原始模型、SFT、DPO、NPO（均含/不含数据增强）。
  - 先进方法：Representation Rerouting (RR)、Tampering Attack Resistance (TAR)。
  - 消融：梯度上升（GA）用于对比。
- **模型**：Gemma-2-2B、Llama-3-8B（均为Instruct版本）。

## 4. 资源与算力
- **明确信息**：所有模型均在 **NVIDIA H100 GPU** 上训练，共 **10个epoch**，batch size=2，梯度累积=1，学习率1×10⁻⁵，采用AdamW优化器，bfloat16混合精度，最大序列长度512。
- **未明确说明**：文中未提及使用的GPU数量、总训练时长或能耗。仅提到“NVIDIA H100 GPUs”（复数），但未给出确切数量。

## 5. 实验数量与充分性
- **实验数量**：覆盖多组评估（前缀攻击ASR vs. 不同长度、多轮ASR vs. 轮次、GCG/AutoDAN ASR、HellaSwag/MMLU精度、XSTest过拒绝率）。消融实验包括：有无数据增强、不同token权重函数（指数/对数、不同τ、使用越狱模型作为参考）、帕累托分析（10个epoch每个检查点）。
- **充分性与公平性**：
  - 实验设计较为全面：同时在两个不同规模模型上验证，涵盖多种典型越狱攻击（前缀、后缀、多轮）。
  - 对比方法包括近年代表性防御（RR、TAR），且使用相同攻击生成策略（攻击数据对基线模型不可见）。
  - 帕累托分析揭示了鲁棒性与能力之间的权衡，并比较了不同方法在训练过程中的表现。
  - 但未测试更大规模模型（如70B）或更复杂的攻击（如基于角色的越狱）；多轮攻击下的鲁棒性提升幅度有限，可能提示训练数据未覆盖长上下文场景。

## 6. 论文的主要结论与发现
1. **DPO的梯度缺陷**：DPO在安全对齐中学习率饱和且OOD泛化差，导致对前缀攻击等防御薄弱。
2. **DOOR有效**：双目标优化（鲁棒拒绝+定向遗忘）显著降低各种攻击的成功率（ASR），且优于DPO和单纯SFT。
3. **W-DOOR进一步提升**：token级权重机制（尤其强调拒绝关键token）进一步增强鲁棒性，同时保持HellaSwag精度。
4. **鲁棒性泛化**：前缀攻击ASR可作为整体鲁棒性的可靠指标，其提升可泛化到后缀攻击、多轮攻击，甚至OOD数据集HarmBench。
5. **模型行为分析**：鲁棒性与KL散度（与基模型相比）正相关；W-DOOR在隐空间上实现更清晰的安全/有害表示分离。
6. **过拒绝与能力保留**：W-DOOR在降低ASR的同时，过拒绝率并未显著上升，且HellaSwag精度接近原始模型。

## 7. 优点：方法或实验设计上的亮点
- **理论驱动**：从DPO梯度的数学分析出发，识别其不足，进而设计新的损失函数，而非完全经验试错。
- **双目标解耦**：将拒绝学习与有害知识遗忘分离，避免DPO中“安全-有害”边缘竞争导致的梯度饱和。
- **token级权重**：首次在安全对齐中引入基于奖励的token级加权，强调关键拒绝token（如“Sorry”），思路新颖且有效。
- **数据增强策略**：通过拼接有害前缀迫使模型学会“途中拒绝”，直接针对前缀攻击这一常见越狱方式。
- **广泛的对比与消融**：包含多种基线（RR、TAR）和大量消融实验（参数、有无增强、不同权重函数），实验设计全面。
- **行为分析**：通过KL散度、token概率分布、t-SNE可视化等深入解释鲁棒性来源，增加可信度。

## 8. 不足与局限
- **多轮攻击鲁棒性有限**：所有方法（包括W-DOOR）在多轮攻击下ASR仍较高（约0.35-0.5），说明训练数据缺乏多轮或长上下文样本。
- **数据增强可能引入过拒绝**：随机选择前缀长度可能导致模型对非有害前缀也产生拒绝，增加过拒绝风险（XSTest上W-DOOR拒答率0.44，高于部分基线）。
- **token权重可能不稳定**：权重基于参考策略 \(\pi_{\text{ref}}\) 与理想策略 \(\pi^*\) 的比值，但 \(\pi^*\) 由DPO模型近似，可能存在噪声。
- **实验覆盖有限**：仅测试了两个中等规模模型（2B和8B），未在更大模型（如70B）或不同架构上验证。攻击类型未覆盖所有已知越狱（如重编码、低资源语言）。
- **未报告训练时间**：缺乏训练效率对比，可能影响实际部署可行性。
- **保留损失比例固定**：α=0.2可能不是最优，且未对每个方法单独调参，公平性虽好但可能未发挥各方法最大潜力。

（完）
