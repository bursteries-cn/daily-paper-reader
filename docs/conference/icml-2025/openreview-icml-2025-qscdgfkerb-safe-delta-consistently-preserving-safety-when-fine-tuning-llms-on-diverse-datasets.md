---
title: "Safe Delta: Consistently Preserving Safety when Fine-Tuning LLMs on Diverse Datasets"
title_zh: Safe Delta：在不同数据集上微调时一致保持大模型安全性
authors: "Ning Lu, Shengcai Liu, Jiahao Wu, Weiyu Chen, Zhirui Zhang, Yew-Soon Ong, Qi Wang, Ke Tang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=QsCDgFKErb"
tags: ["query:model-edit"]
score: 4.0
evidence: 通过调整delta参数在微调中保持安全性
tldr: 大语言模型微调服务面临安全威胁，用户上传的数据可能破坏模型对齐。本文提出Safe Delta，一种安全感知的后训练防御方法，通过调整微调前后的参数差值（delta）来保持模型安全性。该方法适用于不同规模、不同任务的微调数据集，在多个基准上平衡了安全与效用。Safe Delta为模型编辑安全提供了一种实用的保护机制。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 771, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 843, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 762, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 683, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qscdgfkerb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 882, \"height\": 466, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 815, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1512, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 830, \"height\": 703, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1511, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 781, \"height\": 135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 738, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 829, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1305, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1712, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1335, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 578, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1458, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qscdgfkerb/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 922, \"height\": 254, \"label\": \"Table\"}]"
motivation: 微调服务中用户数据可能破坏模型安全，现有方法难以应对数据集多样性。
method: 提出Safe Delta，通过调整微调后的参数增量来保留安全对齐。
result: 在多种微调场景下有效保持安全性，且不牺牲模型效用。
conclusion: Safe Delta是一种轻量有效的微调安全防御方法，适用于模型编辑安全实践。
---

## Abstract
Large language models (LLMs) have shown great potential as general-purpose AI assistants across various domains. To fully leverage this potential in specific applications, many companies provide fine-tuning API services, enabling users to upload their own data for LLM customization. However, fine-tuning services introduce a new safety threat: user-uploaded data, whether harmful or benign, can break the model’s alignment, leading to unsafe outputs. Moreover, existing defense methods struggle to address the diversity of fine-tuning datasets (e.g., varying sizes, tasks), often sacrificing utility for safety or vice versa. To address this issue, we propose Safe Delta, a safety-aware post-training defense method that adjusts the delta parameters (i.e., the parameter change before and after fine-tuning). Specifically, Safe Delta estimates the safety degradation, selects delta parameters to maximize utility while limiting overall safety loss, and applies a safety compensation vector to mitigate residual safety loss. Through extensive experiments on four diverse datasets with varying settings, our approach consistently preserves safety while ensuring that the utility gain from benign datasets remains unaffected.

---

## 论文详细总结（自动生成）

# 论文《Safe Delta》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：大语言模型（LLM）在通用领域表现出色，许多公司提供微调 API 服务，允许用户上传自有数据以定制模型。但微调服务引入新的安全威胁：用户上传的数据（无论有害或良性）都可能破坏模型的对齐（alignment），导致模型输出不安全内容。
- **现有方法不足**：现有防御方法（如数据增强、权重修改）难以适应微调数据集的多样性（不同规模、不同任务），往往在安全性和效用之间顾此失彼。数据型方法随有害数据规模增大而失效，权重型方法难以平衡良性微调的效用提升与有害微调的安全性保持。
- **研究目标**：提出一种能**一致地保持安全性**，同时**不牺牲良性微调的效用增益**的通用防御方法，适用于多样化的微调场景。

## 2. 方法论

### 核心思想
- **核心概念**：将微调前后的参数变化记为 ΔWₛft = Wₛft - Wₒrig。Safe Delta 通过**选择性地保留**部分对效用贡献大、对安全损害小的 delta 参数，并添加额外的**安全补偿向量**来抵消剩余的安全损失。
- **两层优化**：在逐层（layer-wise）上分解原优化问题，目标为在安全损失不超过阈值的前提下，最大化微调任务的效用。

### 关键技术细节
1. **安全损失度量**：使用二次 ℓ₂ 范数度量安全数据集上的层输出距离：Lₛafe = ∥Wₛd Xₛafe - Wₒrig Xₛafe∥₂²。
2. **安全补偿向量（Theorem 4.1）**：受 Optimal Brain Surgeon (OBS) 启发，当添加单个 delta 参数 δw_m 时，最优的剩余权重调整补偿向量为：
   - C_m = δw_m / [H⁻¹]ₘₘ · H⁻¹_{:,m}
   - 对应的安全损失增量为 δLₘ_safe = (δw_m)² / (2[H⁻¹]ₘₘ)
   - 其中 H 是安全损失关于原始参数的 Hessian 矩阵，可在微调前一次计算并缓存。
3. **效用改进估计**：直接使用参数距离近似效用改进：L_util = ∥Wₛd - Wₒrig∥₂²，单参数 δw_m 对应的效用改进为 -δLₘ_util = (δw_m)²。
4. **贪心选择策略**：计算每个 delta 参数的效用-安全比 r_m = 2[H⁻¹]ₘₘ，按降序排列，贪心选取直到累积安全损失超过阈值 ε。阈值设为 ε = s · 1/Nₘ ∑ₘ 1/(2[H⁻¹]ₘₘ)。
5. **安全补偿向量应用**：将选定的 delta 参数对应的补偿向量 C_m 施加到**未被选择**的参数位置上（即 (I - M) ⊙ ∑C_m），以恢复安全，同时保留选定参数的效用。

### 算法流程
- **准备阶段**（一次）：基于原始对齐模型和安全数据集计算 Hessian 矩阵并缓存其逆 H⁻¹。
- **标准微调**：用户数据上传后执行常规微调，得到 ΔWₛft。
- **Step 1（选择）**：计算每个 delta 参数的安全损失和效用-安全比，贪心选择参数掩码 M。
- **Step 2（补偿）**：根据选定参数计算安全补偿向量 C，最终模型 Wₛd = Wₒrig + M ⊙ ΔWₛft + C。

## 3. 实验设计

### 数据集与场景
| 数据集 | 意图 | 内容 | 规模 |
|--------|------|------|------|
| PureBad | 有害微调 | 显式有害 | 100 |
| Identity Shift | 有害微调 | 隐式有害（绝对服从） | 100 |
| Dirty Summary | 良性微调（非清洁） | 有害+良性 | 1100 |
| Math (GSM8k) | 良性微调（清洁） | 纯数学 | 7500 |

### 基准方法
- **数据型方法**：SafeInstr（增加安全样本）、BEA（后门增强对齐）
- **权重型方法**：Safe LoRA（投影到安全子空间）、Resta（添加安全任务向量）
- **安全过滤方法**（附录）：Llama-Guard-3-8B

### 评估指标
- **安全性**：攻击成功率（ASR，基于拒绝关键词集）、有害性分数（HS，GPT-4 评分 1-5）
- **效用**：MMLU（知识推理）、MT-Bench（对话能力）、Rouge-1 F1（摘要）、GSM8k 准确率（数学）

### 数据集规模变化实验
- 有害数据集大小：50, 100, 150, 200，与 BEA、SafeInstr 对比。
- 良性微调上：改变安全阈值 s，与 Safe LoRA、Resta 对比。

### 消融与扩展实验
- 去除安全补偿向量（w/o SCV）
- 不同约束缩放因子 s 的影响
- 不同 LLM（Llama-3-8b-instruct、Llama-2-13b-chat）
- LoRA 微调场景
- 过防御测试（OR-Bench）
- 有害-良性交互场景
- 大规模有害数据集（1K、10K）
- 对抗性越狱攻击（GCG、AutoDAN、PAIR）

## 4. 资源与算力

- **硬件**：单块 A100-80G GPU。
- **准备阶段**：7B 模型计算 H⁻¹ 耗时约 **210 秒**（一次完成，可复用）。
- **每次微调请求额外开销**：Safe Delta 平均增加 **62 秒**（包括选择和补偿步骤）。
- **对比**：BEA 依赖数据集规模（PureBad 加 10.2 秒，Math 加 114.1 秒），Safe LoRA 约 142.7 秒。
- 论文未明确说明微调本身的总训练时长或使用的 GPU 总数量，但强调准备步骤开销可接受且只需一次。

## 5. 实验数量与充分性

- **主要实验**：4 个数据集 × 2 种场景（有害/良性） × 5 种方法（含 Safe Delta） = 至少 20 组对比实验。
- **数据集规模实验**：4 种规模 × 2 种有害数据集 = 8 组。
- **效用-安全平衡实验**：多超参数对比（图 5），包括跨数据集和单数据集 Pareto 前沿。
- **消融实验**：去除补偿向量、不同 s 值、LoRA、不同 LLM、过防御、大规模数据集、对抗攻击等，总计超过 **10 项配套实验**。
- **充分性评价**：实验设计覆盖有害与良性、不同大小、不同任务、不同模型、参数高效微调、多种攻击场景，对比方法全面，消融完整。结果展示了 Safe Delta 在所有场景下的一致优势（安全性和效用 Pareto 最优）。实验客观公平：所有方法使用相同超参数设置，未针对 Safe Delta 单独优化基线（除 Safe LoRA 阈值在 Dirty Summary 上调优一次）。

## 6. 主要结论与发现

- Safe Delta 在所有实验场景下**一致地保持安全性**（ASR 最低，HS 最低），同时**不降低良性微调的效用**（与微调模型相当）。
- 数据型方法的有效性随有害数据规模增加而退化，权重型方法难以同时兼顾安全与效用。
- Safe Delta 通过参数级优化安全-效用权衡，无需针对每个请求重复调整超参数，具有实际部署可行性。
- 安全补偿向量是核心组件，去除后 ASR 从 5.15% 升至 26.97%。
- 在 LoRA 场景、不同 LLM、大规模数据集、对抗攻击下均有效，未出现过度拒绝问题。

## 7. 优点

- **泛化性强**：方法对数据集大小、任务类型、模型架构不敏感，一次性计算 Hessian 可复用。
- **数学严谨**：基于 OBS 的 Hessian 推导给出了安全损失最优补偿的闭式解，选择策略有理论支撑。
- **轻量高效**：额外开销仅 62 秒/次请求（7B 模型），准备阶段 210 秒可接受。
- **动态自适应**：不是固定防御强度，而是根据数据集实际安全影响自动调整，避免过防御或欠防御。
- **实验全面**：覆盖有害/良性、不同规模、不同模型、不同微调方式，消融充分，结果可信。

## 8. 不足与局限

- **潜在攻击对抗**：论文自身承认，若攻击者精心设计微调数据以避开 Safe Delta 的修正，方法可能失效（例如故意使 delta 参数的 Hessian 特性无法被正确估计）。
- **贪心选择非最优**：使用的贪心策略在 knapsack 类问题中只是近似最优，更智能的选择方法可能进一步提升效果。
- **仅限文本安全**：未覆盖多模态 LLM（如图像、语音），但论文提出未来可通过收集多模态安全数据扩展。
- **Hessian 计算依赖安全数据集**：安全数据的质量和代表性会影响补偿效果，若安全数据集与真实攻击分布不匹配，保护可能不足。
- **全参数微调假设**：虽然验证了 LoRA，但方法对 LoRA 的适配未深入讨论（如秩的选择影响）。
- **计算资源消耗**：虽然每次请求开销小，但 Hessian 逆的计算和存储对超大模型（如 70B、130B）可能带来内存压力（论文未讨论扩展性）。

（完）
