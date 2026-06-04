---
title: "Shape it Up! Restoring LLM Safety during Finetuning"
title_zh: 重塑形状！在微调中恢复大语言模型的安全性
authors: "ShengYun Peng, Pin-Yu Chen, Jianfeng Chi, Seongmin Lee, Duen Horng Chau"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PAIVwOaAnq"
tags: ["query:model-edit"]
score: 8.0
evidence: 微调中的动态安全整形
tldr: 本文针对微调中安全上下文在单样本内变化的问题，提出动态安全整形框架DSS。利用细粒度安全信号，在更新模型时分段强化安全内容、抑制不安全内容。实验表明DSS有效提升微调后模型的安全性，同时减少有害内容学习。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 716, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 521, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1371, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 596, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 594, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-paivwoaanq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1353, \"height\": 1215, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 811, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 934, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1375, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1244, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 752, \"height\": 525, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 930, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1075, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 640, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1407, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1032, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 854, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 993, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 885, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 884, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 594, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 541, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 612, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-paivwoaanq/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 911, \"height\": 293, \"label\": \"Table\"}]"
motivation: 现有安全微调方法对样本内安全与不安全部分同等更新，效果次优。
method: 提出动态安全整形DSS，基于细粒度安全信号调整每段损失的权重。
result: 在多个安全基准上，DSS微调后的模型有害响应率显著降低。
conclusion: 细粒度安全整形为安全微调提供了更精确的控制手段。
---

## Abstract
Finetuning large language models (LLMs) enables user-specific customization but introduces important safety risks: even a few harmful examples can compromise safety alignment. A common mitigation strategy is to update the model more strongly on examples deemed safe, while downweighting or excluding those flagged as unsafe. However, because safety context can shift within a single example, updating the model equally on both harmful and harmless parts of a response is suboptimal — an atomic treatment we term static safety shaping. In contrast, we propose dynamic safety shaping (DSS), a dynamic shaping framework that uses fine-grained safety signals to reinforce learning from safe segments of a response while suppressing unsafe content. To enable such fine-grained control during finetuning, we introduce a key insight: guardrail models, traditionally used for filtering, can be repurposed to evaluate partial responses, tracking how safety risk evolves throughout the response, segment by segment. This leads to the Safety Trajectory Assessment of Response (STAR), a token-level signal that enables shaping to operate dynamically over the training sequence. Building on this, we present ★DSS, a DSS method guided by STAR scores that robustly mitigates finetuning risks and delivers substantial safety improvements across diverse threats, datasets, and model families, all without compromising capability on intended tasks. We encourage future safety research to build on dynamic shaping principles for stronger mitigation against evolving finetuning risks. Our code is publicly available at https://github.com/poloclub/star-dss

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机与背景）

大语言模型（LLM）的微调服务允许用户上传自定义数据集以定制模型行为，但这带来了严重的安全风险：即使少量有害数据也会破坏模型的安全对齐。现有缓解方法通常采用**静态安全整形（static safety shaping）**，即对每个训练样本做二元判断（保留或丢弃），并对整个样本施加相同的更新权重。然而，**单个样本内部的安全上下文可能发生变化**（例如，响应前半段安全、后半段有害），静态整形无法区分，导致对有害部分与安全部分学习效果不佳。为此，论文提出**动态安全整形（Dynamic Safety Shaping, DSS）**，利用细粒度安全信号动态调整每个token的更新权重，在强化安全内容学习的同时抑制不安全内容。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 将护栏模型（guardrail model）从“全响应分类”重新用于**评估部分响应的安全性**，从而获得逐token的安全信号。
- 定义**STAR分数（Safety Trajectory Assessment of Response）**：对每个前缀 $(x, y_{1:t})$，利用护栏模型logits计算安全概率 $V_{\text{safe}}(x, y_{1:t})$，反映“给定已生成内容，继续生成安全的可能性”。

### 关键技术细节
- **STAR分数计算**：  
  $V_{\text{safe}}(x, y_{1:t}) = \sigma(\text{logit}_{\text{safe}}^{(t)} - \text{logit}_{\text{unsafe}}^{(t)})$，其中 $\sigma$ 为sigmoid函数。
- **★DSS损失函数**：  
  将响应分为 $K$ 个chunk（每个chunk含 $M$ 个token），对第 $k$ 个chunk使用STAR分数 $V_{\text{safe}}(x, y_{1:kM})$ 作为权重：
  $$
  \mathcal{L} = \sum_{k=1}^{K} \sum_{t=(k-1)M+1}^{\min(kM,T)} \left[ V_{\text{safe}} \cdot \mathcal{L}_{\text{CE}}(y_t) + (1 - V_{\text{safe}}) \cdot \lambda_{\text{KL}} \cdot \text{KL}(\pi_\theta \| \pi_{\text{ref}}) \right]
  $$
  - 当 $V_{\text{safe}} \approx 1$ 时，退化为标准SFT（交叉熵主导）；
  - 当 $V_{\text{safe}} \approx 0$ 时，KL散度项主导，使模型向原始安全参考模型靠拢；
  - 混合安全内容时，自动调整每token的权重。
- **理论保证**（定理1）：★DSS微调后的模型有害性受限于原参考模型有害性加上KL项和护栏模型最坏情况漏检率。

## 3. 实验设计

### 数据集与场景
- **安全评估**：HEx-PHI、AdvBench（使用GPT-4o判断响应是否安全）。
- **能力评估**：MMLU、ARC-Challenge（ARC-C）、GSM8K。
- **微调数据**：
  - 有害数据：PureBad、BeaverTails、Anthropic HH-RLHF。
  - 安全数据：Safe Instruct、GSM8K（良性）。
- **场景**：恶意用户 vs 良性用户；有无可信安全数据集 $D_{\text{safe}}$，组合成四种现实场景。

### 基准方法
- **无安全数据**：Vanilla SFT、Vaccine、SafeLoRA、Rejection Sampling (RS)、Deep Token、★DSS。
- **有安全数据**：额外对比 Safe Instruct、SEAL、LISA。

### 模型与护栏
- **LLM**：Llama-3.2-1B-Instruct（主要）、Llama-3.1-8B-Instruct、Llama-2-7B-Chat、Gemma-3-1B-IT、Granite-3.3-2B-Instruct、Qwen-2.5-3B-Instruct。
- **护栏模型**：Granite Guardian-3.1-2B/8B、Llama Guard-3-1B/8B。

## 4. 资源与算力

- 论文明确说明：**计算STAR分数的实验在单节点8张A40 GPU上进行**（表3给出不同chunk大小M下的平均时间）。
- 对于Llama-3.2-1B等模型微调，未给出具体GPU型号和训练时长；但提及STAR分数可预计算并缓存，并且可通过流水线与训练并行以降低开销。
- 总体而言，资源需求适中，且可通过并行优化。

## 5. 实验数量与充分性

- **实验覆盖广泛**：
  - 在主场景（恶意/良性用户 × 有无安全数据）四种组合下均进行了评估。
  - 跨6种不同LLM、4种护栏模型、5种有害比例（0%~100%）、3种有害数据集（PureBad, BeaverTails, HH-RLHF）。
  - 扩展攻击场景：响应适配攻击（前缀/后缀）、提示中毒攻击、有害预填充攻击。
- **消融实验**：对chunk大小M和KL缩放因子 $\lambda_{\text{KL}}$ 进行了灵敏度分析。
- **公平性**：所有基线使用其官方超参数，且同时报告安全与能力指标（避免以牺牲能力换安全）。
- **结论**：实验设计全面、客观，对比充分，结论可信。

## 6. 主要结论与发现

- ★DSS在所有场景下**显著提升安全性**，且**不降低模型在目标任务上的能力**。
- 在最坏场景（恶意用户、无安全数据）下，★DSS比最强基线RS提升**20.41%** 安全分数（HEx-PHI: 72.12% vs 56.36%；AdvBench: 89.42% vs 79.23%）。
- ★DSS对护栏模型错误具有**鲁棒性**（相比RS，在高FN率下性能下降更小）。
- 在响应适配攻击（误导性后缀）中，★DSS仍保持高安全性（AdvBench 84.62%），而RS因全响应过滤被欺骗几乎完全失效（14.81%）。
- 理论分析表明★DSS模型的有害性存在可解释的上界。

## 7. 优点

1. **细粒度动态整形**：首个利用护栏模型在部分响应上的演化信号实现token级安全调整的方法，突破了静态整形的局限性。
2. **无需额外安全数据**：在无安全数据集场景下仍能有效恢复安全性（如最坏场景）。
3. **理论有界保证**：安全性能上界明确，与KL散度和护栏错误率相关。
4. **强鲁棒性**：对多种对抗性攻击（后缀/前缀/提示中毒）均表现出较好防御效果。
5. **通用性**：在多个模型族、护栏模型、有害数据比例上均有一致改进。
6. **实现简洁**：STAR分数预计算后可高效集成训练，开销可控。

## 8. 不足与局限

1. **计算开销**：STAR分数计算需要额外预处理时间（尤其小chunk M时），论文虽提出流水线并行缓解，但未在超大规模训练中验证。
2. **依赖护栏模型质量**：尽管★DSS对护栏错误有一定鲁棒性，但极端差的护栏仍可能降低性能；护栏模型本身的安全策略可能不一致。
3. **对抗适应风险**：虽然论文测试了误导后缀等攻击，但可能存在更复杂的对抗性样本（如自适应优化）同时欺骗护栏和STAR评分，论文未充分探索。
4. **实验模型规模有限**：最大模型为8B参数，未在更大规模（如70B+）模型上验证。
5. **能力评估较窄**：主要使用MMLU/ARC/GSM8K等通用基准，未在特定领域任务（如代码生成、医疗）中评测。
6. **道德风险**：论文中使用的对抗性内容和“红队”数据可能被误用；虽然论文有警告，但未详细讨论数据来源与伦理审查。

（完）
