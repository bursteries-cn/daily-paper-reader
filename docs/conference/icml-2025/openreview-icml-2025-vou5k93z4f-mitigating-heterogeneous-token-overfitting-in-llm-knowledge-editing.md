---
title: Mitigating Heterogeneous Token Overfitting in LLM Knowledge Editing
title_zh: 缓解大语言模型知识编辑中的异质性标记过拟合
authors: "Tianci Liu, Ruirui Li, Zihan Dong, Hui Liu, Xianfeng Tang, Qingyu Yin, Linjun Zhang, Haoyu Wang, Jing Gao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vOu5K93z4f"
tags: ["query:model-edit"]
score: 9.0
evidence: 解决大语言模型知识编辑中的异质性标记过拟合问题
tldr: 知识编辑后大语言模型对新知识推理能力下降，本文发现异质性标记过拟合（HTO）是关键原因。提出缓解HTO的方法，通过调整编辑策略使模型更好地泛化到新知识。实验证明该方法显著提升了编辑后模型的推理性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vou5k93z4f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vou5k93z4f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vou5k93z4f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 804, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vou5k93z4f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1684, \"height\": 1064, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vou5k93z4f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vou5k93z4f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 695, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vou5k93z4f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1684, \"height\": 1554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vou5k93z4f/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1686, \"height\": 1549, \"label\": \"Table\"}]"
motivation: 知识编辑后LLM对新知识的推理能力下降，原因是异质性标记过拟合。
method: 识别HTO问题并提出针对性的缓解方法，通过调整编辑参数避免过拟合特定标记。
result: 所提方法在多个知识编辑基准上提升了编辑后模型的推理能力。
conclusion: 缓解HTO是提升知识编辑效果的重要方向。
---

## Abstract
Large language models (LLMs) have achieved remarkable performance on various natural language tasks. However, they are trained on static corpora and their knowledge can become outdated quickly in the fast-changing world. 
This motivates the development of knowledge editing (KE) to update specific knowledge in LLMs without changing unrelated others or compromising their pre-trained capabilities. 
Previous efforts sought to update a small amount of parameters of a LLM and proved effective for making selective updates.  
Nonetheless, the edited LLM often exhibits degraded ability to reason about the new knowledge. 
In this work, we identify a key issue: \textit{heterogeneous token overfitting} (HTO), where the LLM overfits different tokens in the provided knowledge at varying rates.
To tackle this, we propose {OVERTONE}, a token-level smoothing method that mitigates HTO by adaptively refining the target distribution. 
Theoretically, OVERTONE offers better parameter updates with negligible computation overhead. 
It also induces an implicit DPO but does not require preference data pairs. 
Extensive experiments across four editing methods, two LLMs, and diverse scenarios demonstrate the effectiveness and versatility of our method.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：大语言模型（LLM）基于静态语料训练，知识容易过时。知识编辑（KE）旨在更新特定知识，同时保持无关知识及预训练能力。现有方法通过更新少量参数实现选择性更新，但编辑后的LLM往往对新知识的推理能力下降。
- **问题发现**：论文首次识别并定义了**异构令牌过拟合（HTO）**现象，即LLM在拟合编辑知识时，不同令牌的学习速率不一致，导致模型过度关注易于拟合的令牌而忽略困难令牌，最终损害推理能力（如多跳推理）。具体表现为：编辑后，模型对同类查询的泛化性（Generality）尚可，但推理性（Portability）显著退化。
- **整体意义**：揭示KE过拟合的根源在令牌级别，为设计更鲁棒的编辑策略提供了新视角。

## 2. 论文提出的方法论
- **核心思想**：针对HTO，提出 **OVERTONE**——一种令牌级别的自适应平滑方法。通过为每个令牌动态构建平滑的目标分布，控制不同令牌的拟合程度，从而缓解过拟合。
- **关键技术细节**：
    - 使用模型**当前预测分布 πθ** 经 **Top-nσ 过滤**（去除尾噪声）后得到 πflt。
    - 将 πflt 与标签独热分布 δ(yi) 按参数 λ 混合，形成候选目标分布 πtar_can。若该分布正确分配最大概率给标签 yi，则采用；否则回退到 δ(yi)，避免新旧知识冲突。
    - 损失函数采用**剪枝的前向KL散度**：ℓ = Σ max( DKL[πtar || πθ], ε )，其中 ε 实现令牌级的早期停止，防止过度拟合。
- **算法流程（文字描述）**：
    1. 给定编辑样本 (x, y) 及初始参数 θ₀。
    2. 对每个令牌 yi，构建上下文 ci = x ⊕ y<ᵢ。
    3. 通过模型获取 logits，经 softmax 得 πθ。
    4. 对 logits 进行 Top-nσ 过滤（保留大于 max- nσ 的 logit），重新 softmax 得 πflt。
    5. 按式 (3) 混合得到 πtar。
    6. 计算该令牌的损失 ℓ = max(DKL, ε)。
    7. 对所有令牌求和得总体损失，更新参数。
- **理论优势**：
    - 通用性：OVERTONE 可退化为标准交叉熵（λ=1, ε=0）。
    - 计算高效：额外复杂度仅为 O(|V|)，远小于 LLM 前向。
    - 更优更新方向：通过影响函数分析，OVERTONE 的梯度方向更接近理想重训练梯度，且对无关知识扰动更小。
    - 与DPO的联系：可看作隐式 DPO，无需偏好数据对。

## 3. 实验设计
- **数据集/场景**：
    - **单次编辑**：ZsRE、WikiData recent、WikiData counterfact、WikiBio。
    - **持续编辑**：同上四个数据集，序列长度 T=1,10,100。
    - **复杂推理**：MQuAKE-2002（含单跳和多跳推理）。
- **评估指标**：可靠性（Rel.）、通用性（Gen.）、可移植性（Por.）、局部性（Loc.），以及平均分。
- **对比方法**：
    - **内部存储**：FT-M（细调特定层）、LoRA（低秩适配）、MELO（动态LoRA+门控）、WISE（权重副本+门控）。
    - **外部存储基线**：ROME（因果溯源+解析更新）、MEMIT（批量编辑）。
- **实现工具**：EasyEdit。

## 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量、训练时长等硬件资源。仅提到基于LLaMA2-7B和LLaMA3-8B进行实验，但未披露训练配置。

## 5. 实验数量与充分性
- **实验数量**：非常充分。
    - 单次编辑：4种方法 × 2个LLM × 5个数据集 ≈ 40组主实验，每组报告4个指标。
    - 持续编辑：4种方法（以及ROME/MEMIT） × 2个LLM × 3个序列长度 × 5数据集，数据量巨大。
    - 消融实验：1组（LoRA on ZsRE）详细分析了4个组件的影响。
    - 额外复杂推理实验：FT-M和LoRA在MQuAKE上的结果。
- **充分性与公平性**：
    - 实验覆盖了主流编辑方法家族（内部存储、外部存储），且均在统一框架下实现。
    - 对比基线包括ROME、MEMIT等强基线，且报告了默认或调优超参数（附录B）。
    - 消融实验系统验证了每个设计模块的必要性。
    - 不足：未对超参数进行大规模扫描（论文声明未过度调优），可能产生次优结果；未报告多次运行的统计方差。

## 6. 论文的主要结论与发现
- OVERTONE **显著提升了所有编辑方法的性能**，尤其改善了可移植性（Portability）和局部性（Locality），且不牺牲可靠性。
- 在持续编辑场景下，OVERTONE帮助原本不适合持续编辑的方法（如LoRA）取得了与专门方法（MELO、WISE）竞争的表现。
- 消融实验确认了**每个组件**（修剪、动态过滤、检查机制）的贡献，缺失任一都会导致性能下降。
- 理论分析表明OVERTONE提供更优的更新方向且对无关知识影响更小。

## 7. 优点
- **方法通用性强**：可即插即用于多种现有KE方法，不依赖特定参数更新策略。
- **计算开销极低**：仅增加O(|V|)复杂度，实用性强。
- **理论支撑扎实**：从影响函数、DPO连接等多个角度论证有效性。
- **实验设计全面**：覆盖单次/持续编辑、复杂推理、多个LLM和数据集，消融实验充分。
- **与现有技术互补**：可直接与参数约束、低秩更新等方法结合。

## 8. 不足与局限
- **硬件资源未报告**：无法判断实验的可复现成本。
- **未与ROME/MEMIT直接结合**：ROME/MEMIT使用特殊损失（如MSE），OVERTONE未验证对其效果，论文承认需进一步扩展。
- **潜在知识冲突风险**：OVERTONE使用模型自身预测，当模型存在严重偏见或过时知识时，混合目标可能引入冲突（尽管通过检查机制缓解，但非完全消除）。
- **长文本或自由形式编辑未充分测试**：HTO问题可能在长序列中加剧，但论文实验中编辑知识多为短句；自由形式编辑场景未涉及。
- **超参数敏感**：λ、ε、n等需要针对不同方法调优，且论文未进行敏感性分析。
- **缺乏多次运行统计**：未报告多次实验的标准差或置信区间，结果稳定性存疑。

（完）
