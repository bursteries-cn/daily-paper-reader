---
title: "Finding and Reactivating Post-Trained LLMs' Hidden Safety Mechanisms"
title_zh: 发现并重新激活后训练大语言模型的隐藏安全机制
authors: "Mingjie Li, Wai Man Si, Michael Backes, Yang Zhang, Yisen Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=pcG6NRJKu7"
tags: ["query:model-edit"]
score: 6.0
evidence: 发现并重新激活隐藏安全机制属于模型编辑安全范畴
tldr: 针对后训练导致大语言模型安全性下降的问题，本文研究并发现模型中存在隐藏的安全机制，并提出了重新激活这些机制的方法。实验证明，该方法能有效恢复模型的安全对齐水平，避免全量重训练的成本，为模型编辑安全提供了新的思路和实用工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pcg6nrjku7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1225, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pcg6nrjku7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1233, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pcg6nrjku7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 575, \"height\": 333, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1019, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1195, \"height\": 768, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 610, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 589, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 636, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 706, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pcg6nrjku7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 529, \"height\": 163, \"label\": \"Table\"}]"
motivation: 后训练常导致LLM安全性下降，需要低成本的方法恢复安全机制。
method: 定位并重新激活模型中的隐藏安全机制，通过轻量级干预恢复安全对齐。
result: 在多个后训练模型上成功重新激活安全机制，显著降低有害输出率。
conclusion: 揭示了隐藏安全机制的存在，为模型编辑安全提供了可行且高效的解决方案。
---

## Abstract
Despite the impressive performance of general-purpose large language models (LLMs), they often require fine-tuning or post-training to excel at specific tasks. 
    For instance, large reasoning models (LRMs), such as the DeepSeek-R1 series, demonstrate strong reasoning capabilities after post-training different general large language models on diverse chain-of-thought (CoT) datasets. 
    However, this additional training frequently comes at the cost of reduced safety, as the fine-tuned or post-trained models tend to exhibit more harmful behaviors compared with the regular LLMs before post-training or fine-tuning, potentially leading to harmful outcomes due to their enhanced capabilities. 
    Taking LRMs as an example, we first investigate the underlying cause of this safety degradation in this paper. 
    Our analysis reveals that post-training can mask the original safety mechanisms of the base LLM, while over-amplifying representations related to their post-training ability. 
    But luckily, we also find that LRMs' safety mechanisms still exist instead of being removed during their post-training. 
    Based on these findings, we propose a lightweight and cost-effective solution called SafeReAct that restores the suppressed safety behaviors by aligning with LoRA adapters on a few layers. Experiments on four state-of-the-art LRMs show that our method significantly improves safety on harmful prompts without compromising reasoning performance. Besides LRMs, additional results on other domain-specific LLMs, like medical models, further confirm the generality and effectiveness of our approach.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

大规模语言模型（LLMs）通过后训练（post-training）可显著提升特定领域能力，例如，大型推理模型（LRMs）如DeepSeek-R1系列经过长链思维（CoT）数据后训练后展现出强大的推理能力。然而，这种后训练常常以安全性下降为代价：后训练模型比原始基础模型更容易产生有害行为，且其增强的能力可能带来更严重的伦理风险。已有研究（如SafeChain、SaLoRA）尝试通过额外数据集重新对齐或添加安全模块来恢复安全性，但通常需要大量计算资源，且可能损害模型原有的领域能力。

论文以LRMs为主要研究对象，探究安全下降的根本原因，并据此提出一个轻量级、低成本的解决方案。

## 2. 方法论：核心思想、关键技术细节与算法流程

### 核心思想
- **发现**：后训练并未移除原始安全机制，而是**遮蔽（mask）**了它。后训练过程过度激活了与领域能力（如推理）相关的表示，从而抑制了安全机制的激活。
- **思路**：通过将后训练模型在有害提示上的内部表示与“安全版本”模型（通过剪枝移除推理相关神经元得到）的表示对齐，重新激活隐藏的安全机制。

### 关键技术细节
1. **安全机制存在的证据**：
   - 使用基于提示的 alignment 方法（PAT、ICD、Self-Remind）可部分恢复安全行为，说明安全机制仍在。
   - 发现“安全性-推理能力权衡”：提升安全时会损害推理性能。

2. **机制验证**：
   - 采用**Wanda分数**基于集差法识别与推理相关的神经元：
     \[
     S = |W| \cdot |X|_2
     \]
     计算目标域（推理任务）和保留域（安全对齐数据）的神经元重要性，取差集获得推理特异性神经元。
   - 剪枝这些推理神经元后，安全行为显著恢复，验证了“推理机制遮蔽安全机制”的假设。

3. **SafeReAct 方法**：
   - **目标**：让后训练模型在有害提示下模仿其安全剪枝版本的内部表示。
   - **对齐损失**：
     \[
     L_{\text{align}} = \sum_{i \in I} \left\| M_{\text{opt}}^{(i)}(x_{\text{harm}}) - M_{\text{safe}}^{(i)}(x_{\text{harm}} \| s_{\text{safe}}) \right\|_F
     \]
     其中 \(M_{\text{opt}}\) 是待优化模型，\(M_{\text{safe}}\) 是剪枝后的安全模型，\(s_{\text{safe}}\) 是安全后缀（如“Remember you should not generate any harmful or misleading content.”）。
   - **保留损失**（保持领域能力）：
     \[
     L_{\text{retain}} = \sum_{i \in I} \left\| M_{\text{opt}}^{(i)}(x_{\text{retain}}) - M^{(i)}(x_{\text{retain}}) \right\|_F
     \]
   - **总损失**（带时序权重）：
     \[
     L = \alpha \left(1 - \frac{t}{2T}\right) L_{\text{align}} + \alpha \left(\frac{t}{2T}\right) L_{\text{retain}}
     \]
     初期更侧重对齐安全，后期更侧重保留能力。
   - **优化方式**：仅对少数几个层（每5层选一层）的LoRA适配器进行优化（rank=16），不修改全部参数。

## 3. 实验设计

### 使用的模型
- **推理模型（LRMs）**：DeepSeek-R1-distilled LLaMA-8B、DeepSeek-R1-distilled Qwen-7B、DeepSeek-R1-distilled Qwen-14B、OpenThinker-7B。
- **其他领域模型**：Llama-3-8B-UltraMedical（医学）、Finance-llama3.1-8B-instruct（金融）。

### 数据集
- **安全对齐**：HarmBench（有害提示），用于对齐损失。
- **保留能力**：LIMO（推理模型保留数据集，约1000个长CoT样本）；UltraMedical（医学模型保留数据，前20000个样本）；金融模型未明确给出保留数据集（可能沿用类似方式）。
- **安全评估**：AdvBench、JailbreakBench（JBB）、XsTest（过度拒绝测试）。
- **推理能力评估**：GSM8K、MATH-500。
- **医学能力评估**：MedQA。

### 对比方法
- **Circuit-Breaker**：基于表示工程，在有害提示上扭曲生成能力。
- **SafeChain**：使用Long CoT风格的安全响应数据集（50K样本）进行完整微调，同时加入推理数据保持能力。

### 评估指标
- **安全性**：有害率（由Llama-3-Guard作为评判）。
- **推理性能**：准确率（GSM8K、MATH-500）。

## 4. 资源与算力

- **硬件**：单个 NVIDIA A100 80GB GPU。
- **训练配置**：LoRA rank=16，学习率2e-5，batch size=16，总迭代步数300步。
- **对比方法资源**：SafeChain的完整微调需要10倍以上的算力开销。

## 5. 实验数量与充分性

### 实验组数
- **主要安全性对比**：4个推理模型 ×（原始+3种方法）= 12组实验，涵盖JBB、AdvBench、XsTest三个安全基准。
- **推理能力对比**：同模型在GSM8K和MATH-500上的准确率。
- **消融实验**：
  - α参数影响（α=2,5,10,20）在R1-7B和R1-8B上测试。
  - 特征探索：通过余弦相似度跟踪训练过程中表示与安全机制表示的靠近程度及ASR变化。
- **跨领域验证**：
  - 医学模型：Llama-3-UltraMedical的JBB和MedQA评估。
  - 金融模型：Finance-Llama3.1-8B-Instruct的JBB和AdvBench评估。
- **过度拒绝测试**：在XsTest良性提示上计算拒绝率（原始模型与SafeReAct后对比）。
- **更大模型**：QwQ-32B和R1-distilled-32B上的JBB测试。

### 充分性与客观性
- 实验覆盖多个模型（7B/8B/14B/32B）、多个领域（推理、医学、金融），对比了两个主流基线方法。
- 消融实验验证了关键参数和机制。
- 使用了标准安全基准和评判模型，确保公平性。
- 但未提供多次运行的误差棒（受限于计算资源），统计显著性未明确。

## 6. 主要结论与发现

1. **安全机制未被移除，而是被遮蔽**：后训练过程中领域能力（如推理）的过度激活掩盖了已有的安全机制，导致有害提示下无法触发安全响应。
2. **剪除推理相关神经元可恢复安全**：实验表明去除推理机制后安全行为显著改善，支持假设。
3. **SafeReAct有效且泛化**：
   - 在四个LRM上，SafeReAct将有害率降至接近0%（JBB和AdvBench），优于Circuit-Breaker和SafeChain。
   - 推理性能几乎无损（GSM8K和MATH-500下降<3%），而基线方法下降明显（SafeChain下降约20%）。
   - 在医学和金融模型上也成功恢复安全，同时保持领域性能。
4. **不会导致过度拒绝**：在XsTest良性提示上拒绝率与原始模型相当（约2-4%）。
5. **可扩展至更大模型**：在32B模型上也有效（JBB有害率从23-27%降至2-3%）。

## 7. 优点

- **轻量级**：仅需训练少量LoRA适配器（每5层一层），总迭代300步，计算成本极低。
- **无需安全响应数据**：只利用模型自身的剪枝安全版本表示，避免了收集和生成安全响应的困难，避免分布偏移。
- **泛化性强**：在推理、医学、金融多个领域均验证有效。
- **机制洞察深刻**：揭示了安全下降的根本原因是遮蔽而非移除，为后训练模型安全维护提供了新视角。
- **实用性好**：可直接应用于已发布的不安全后训练模型，快速恢复安全，无需重新全量训练。

## 8. 不足与局限

- **模型规模限制**：最大只评估到32B参数模型，超过32B的效果未验证。
- **领域覆盖有限**：仅测试了推理、医学、金融三个领域，其他领域（如代码、法律等）未涉及。
- **未提供统计误差**：由于计算资源限制，未报告多次运行的误差棒，实验结果可能对随机种子敏感。
- **对α参数敏感**：虽然安全性能稳定，但推理性能随α变化，实际应用时需要基于验证集调参。
- **依赖剪枝获得安全模型**：需要先识别并剪除领域能力相关神经元，这个步骤本身需要设计目标域和保留域数据集，存在一定主观性。
- **未考虑后训练后的模型结构变化**：方法假设基础安全机制在原始和后训练模型中共享相同的表示空间，对于结构改动较大的后训练（如添加新模块）可能不适用。

（完）
