---
title: "Just Enough Shifts: Mitigating Over-Refusal in Aligned Language Models with Targeted Representation Fine-Tuning"
title_zh: 恰到好处的偏移：通过针对性表征微调缓解对齐大模型的过度拒绝
authors: "Mahavir Dabas, Si Chen, Charles Fleming, Ming Jin, Ruoxi Jia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TiYOHdK35L"
tags: ["query:model-edit"]
score: 4.0
evidence: 针对性的表征微调以减少过度拒绝
tldr: 安全对齐的大模型常常过度拒绝良性请求，损害用户体验。本文提出ACTOR框架，通过分析内部激活模式，精确识别触发拒绝的组件，并仅微调单个模型层来减少过度拒绝。该方法计算高效且数据效率高，在多个基准上有效降低错误拒绝率。ACTOR展示了通过精细控制激活实现安全对齐编辑的可行性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tiyohdk35l/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1759, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tiyohdk35l/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tiyohdk35l/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1685, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tiyohdk35l/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1760, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tiyohdk35l/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1719, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tiyohdk35l/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1738, \"height\": 991, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 380, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1782, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 756, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1777, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1778, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tiyohdk35l/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1786, \"height\": 144, \"label\": \"Table\"}]"
motivation: 安全对齐导致模型过度拒绝良性请求，影响可用性。
method: 基于内部激活模式识别拒绝触发组件，仅微调单个模型层以降低过度拒绝。
result: 在多个基准测试上有效减少过度拒绝，且保持安全性。
conclusion: 通过精确控制激活可以实现安全对齐的精准编辑。
---

## Abstract
Safety alignment is crucial for Large Language Models (LLMs) to resist malicious instructions but often results in over-refusals, where benign prompts are unnecessarily rejected, impairing user experience and model utility. To this end, we introduce **ACTOR** (Activation-Based Training for Over-Refusal Reduction), a robust and compute- and-data efficient training framework that mini- mizes over-refusals by utilizing internal activation patterns from diverse queries. ACTOR precisely identifies and adjusts the activation components that trigger refusals, providing stronger control over the refusal mechanism. By fine-tuning only a single model layer, ACTOR effectively reduces over-refusals across multiple benchmarks while maintaining the model’s ability to handle harmful queries and preserving overall utility.

---

## 论文详细总结（自动生成）

# 论文总结：Just Enough Shifts: Mitigating Over-Refusal in Aligned Language Models with Targeted Representation Fine-Tuning

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：安全对齐的大语言模型（LLM）在拒绝恶意指令的同时，常常过度拒绝（over‑refusal）良性但表面“伪有害”的查询，损害用户体验和模型实用性。
- **挑战**：伪有害提示与真正有害提示在语义和语言特征上高度重叠，使得区分极为困难。
- **目标**：在保持对有害查询的拒绝能力的同时，减少对良性查询的误拒，平衡安全性与可用性。

## 2. 方法论
- **核心思想**：利用模型内部激活模式识别触发拒绝的组件，通过仅微调单个Transformer层来精确调整这些激活，实现“恰到好处”的干预。
- **关键技术细节**：
  - **拒绝向量提取**：使用锚定数据（有害/良性查询）识别安全关键层（通过t‑SNE和轮廓分数确定中间层），然后计算该层上两类查询激活的均值差作为拒绝向量 **R**。
  - **对齐目标设定**：并非对所有查询施加统一偏移，而是根据每个查询在嵌入空间中的位置进行个性化调整。通过投影校准：对于伪有害和良性查询，目标激活为 \( \mathbf{a}_q - \alpha \text{Proj}_{\mathbf{R}}(\mathbf{a}_q) \)；对于有害查询则为 \( \mathbf{a}_q + \alpha \text{Proj}_{\mathbf{R}}(\mathbf{a}_q) \)。其中 \(\alpha\) 是超参数，投影大小与所需偏移量呈线性关系（实验验证）。
  - **损失函数**：Projection‑Calibrated Refusal Direction Loss（\( \mathcal{L}_{\text{PRD}} \)）= 1 − cosine_similarity(当前激活, 目标激活)。
- **算法流程**：交替进行拒绝向量识别与微调，每次更新后重新计算拒绝向量。只更新目标层的参数，其余层冻结。

## 3. 实验设计
- **数据集**：
  - **训练**：HexPhi（有害）、UltraChat（良性）、XSTest/SCOPE/OR‑Bench‑Hard‑1K/PHTest（伪有害）。
  - **评估**：XSTest、SCOPE、OR‑Bench‑Hard‑1K、PHTest（过拒绝）；OKTest（OOD）；AdvBench（安全性）；MMLU、MT‑Bench、WikiText2（通用能力）。
- **基准方法**：默认模型、SFT、Safe‑Decoding、DRO、Self‑CD、SCANS、Surgical。
- **指标**：合规率（C.R.）、安全分数（S.S.）、权衡分数（T.S. = (C.R. + S.S.)/2）、MMLU准确率、MT‑Bench评分、困惑度。

## 4. 资源与算力
- 论文在表3中报告了在**H100 GPU**上训练Llama‑2‑7b‑chat 3个epoch的用时：ACTOR仅需**4分钟**，而SFT需**15分钟**。
- 未明确说明使用的GPU数量、显存等其他细节。

## 5. 实验数量与充分性
- **多模型验证**：在Llama‑2‑7b‑chat、Llama‑2‑13b‑chat、Gemma‑7b‑it三个模型上进行实验。
- **全面消融**：
  - 目标层选择（\(l^*\)）的影响；
  - 投影乘子 \(\alpha\) 的敏感性；
  - 良性样本数量（15、50）和过拒绝样本数量（10、50）的预算消融；
  - 单个过拒绝数据集训练后的跨数据集泛化测试（表9）；
  - 分布鲁棒性实验：改变用于计算拒绝向量的有害数据集（HexPhi, BeaverTails, MaliciousQA）。
- **公平性**：与多种基线方法在相同基准和评估协议下比较，使用GPT‑4o作为裁判进行评估（见附录E），且公开了实验设置和超参数。实验设计较为充分、客观。

## 6. 主要结论与发现
- ACTOR在**显著提高合规率**的同时，几乎不影响有害查询的拒绝能力。在Llama‑2‑7b‑chat上平均合规率提升47.47%（从61.53%到90.74%）。
- ACTOR优于所有基线方法（包括SFT、SCANS、Surgical等），在权衡分数上最高。
- ACTOR**计算高效**（单层微调，训练比SFT快约3.75倍），**数据高效**（即使仅用25个伪有害查询也优于SFT）。
- ACTOR对拒绝向量的数据分布变化**鲁棒性强**，而SCANS等静态向量方法易出现剧烈波动。
- 对通用能力（MMLU、MT‑Bench、困惑度）影响极小（变化在1.5%以内）。

## 7. 优点
- **方法论创新**：基于激活空间而非输出响应的微调，提供更直接的干预。
- **个性化偏移**：通过投影校准实现“恰到好处”的调整，避免均匀偏移导致的模型崩溃。
- **计算与数据双高效**：仅需微调单层，无需生成响应，降低资源门槛。
- **分布鲁棒**：动态更新拒绝向量，适应数据分布变化。
- **广泛验证**：多模型、多基准、多消融实验证明了方法的有效性和稳定性。

## 8. 不足与局限
- **白盒依赖**：需要访问模型内部激活，无法用于黑盒API。
- **标签不一致**：不同基准对“伪有害”的界定存在分歧，实验结果反映的是折中而非普适标准。
- **评估局限**：仅针对单轮查询，未覆盖多轮对话场景（缺乏多轮过拒绝基准）。
- **理论假设**：线性决策边界的简化分析仅用于启发，未严格证明。
- **对照不足**：部分基线（如Safe‑Decoding、DRO）性能较低可能因其原始实现未针对本设置优化，但已尽最大努力复现。
- **实际部署风险**：虽然保持了安全性，但在对抗性攻击下的鲁棒性需要额外评估。

（完）
