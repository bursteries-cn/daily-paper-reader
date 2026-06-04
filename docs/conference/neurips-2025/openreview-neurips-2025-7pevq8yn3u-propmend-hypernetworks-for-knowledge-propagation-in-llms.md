---
title: "PropMEND: Hypernetworks for Knowledge Propagation in LLMs"
title_zh: PropMEND：基于超网络的大语言模型知识传播
authors: "Zeyu Leo Liu, Greg Durrett, Eunsol Choi"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=7pEVq8yN3U"
tags: ["query:model-edit"]
score: 10.0
evidence: 基于超网络的知识传播
tldr: 本文针对知识编辑技术无法传播注入知识的问题，提出PropMEND方法。利用超网络元学习语言建模损失的梯度变换，使模型能回答需要多跳推理的问题。在RippleEdit数据集上，传播问题的准确率显著提升，推动了知识编辑在复杂推理场景的应用。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7pevq8yn3u/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1378, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7pevq8yn3u/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7pevq8yn3u/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 671, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1119, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 769, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1145, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1397, \"height\": 588, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1413, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 469, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 460, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1457, \"height\": 694, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1461, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1043, \"height\": 526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1407, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1351, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1366, \"height\": 2078, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1531, \"height\": 1835, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1527, \"height\": 1867, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 461, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 799, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1429, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 419, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1312, \"height\": 768, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1294, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1117, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7pevq8yn3u/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1255, \"height\": 383, \"label\": \"Table\"}]"
motivation: 现有知识编辑只能让模型复述注入知识，无法进行多跳推理传播。
method: 提出PropMEND，通过超网络修改知识编辑的梯度元目标，促进知识传播。
result: 在RippleEdit数据集上，多跳传播问题准确率显著优于基线。
conclusion: 该方法为知识编辑实现实际推理能力提供了新途径。
---

## Abstract
Knowledge editing techniques for large language models (LLMs) can inject knowledge that is later reproducible verbatim, but they fall short on *propagating* that knowledge: models cannot answer questions that require them to reason with the injected knowledge. We present a hypernetwork-based approach for knowledge propagation, where we meta-learn how to modify gradients of a language modeling loss to encourage injected information to propagate. Our approach, PropMEND, extends the meta-objective of MEND so that gradient updates on a piece of knowledge are transformed to allow answering of multi-hop questions involving that knowledge.
On the RippleEdit dataset, our method significantly improves performance on propagation questions whose answers are not explicitly stated in the injected fact, in contrast to existing methods that only improve on propagation questions where the answer can be copied verbatim.
To study the extent of generalization that our propagation achieves, we construct StoryPropagation, a controlled dataset focusing on entities and relations that the model already understands well. We find that PropMEND generalizes effectively to partially unseen entity-relation pairs, indicating the effectiveness of our meta-trained hypernetwork for knowledge propagation.

---

## 论文详细总结（自动生成）

## 论文中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有的知识编辑技术（如 MEND、MEMIT）能够让大语言模型（LLM）复述注入的新知识，但这些知识无法**传播（propagate）**——即模型无法利用注入的知识进行多跳推理或回答相关但非直接给出的问题。
- **背景**：LLM 在上下文学习（in-context learning）中能够传播知识，但参数化编辑后往往仅限于复制输入中的事实，缺乏对推理链条的支撑。
- **目标**：提出一种能使知识编辑真正支持传播（尤其是多跳推理）的方法，从而提升编辑的实用性。

### 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：在 MEND（Model Editor Networks using Gradient Decomposition）框架上扩展，将超网络的元学习目标从“改写输入事实”改为“回答传播问题”。即训练超网络将语言建模梯度的变换导向使得模型能正确回答涉及新事实的多跳推理问题。
- **关键技术细节**：
    - 基础架构：基于 MEND 的超网络，该网络接收 LLM 在注入事实上的梯度（rank-1 分解），输出修改后的梯度，并将更新应用到 LLM 的特定层权重上。
    - **内循环**（Inner loop）：计算注入事实的因果语言建模（CLM）损失梯度 ∇W LI = -∇W log pW(f)，其中 f 为以自然语言形式表达的新事实（不要求是 QA 对）。
    - **外循环**（Outer loop）：使用传播问答对集合 {(qi, ai)} 计算编辑损失 Le = -1/P ∑ log pW̃(ai | qi)，鼓励更新后的模型正确回答传播问题；同时保留 MEND 中的局部性损失 Lloc（KL 散度），防止遗忘。
    - 超网络参数共享与 FiLM 层：对不同层相同形状的梯度共享超网络，并使用 FiLM 实现层特异性。
    - 更新层选择：发现编辑中上层（Mid-Upper）比顶层更有效，实验中对 1B 模型选择 Layer-10 至 12，对 3B 模型选择 15-27 等。
- **算法流程**：
    1. 输入预训练 LLM 参数 W，可编辑权重集合，超网络参数 ϕ，编辑数据集。
    2. 对于每个训练步：
        a. 从编辑数据集采样一个注入事实 f 及其传播问答案例 {(qi, ai)}、局部性样本 xloc。
        b. 计算 f 的 CLM 梯度 ∇W LI。
        c. 超网络 gϕ 处理该梯度，生成修改后的梯度 ΔW̃。
        d. 应用更新得到临时模型 W̃ = W + ΔW̃。
        e. 在外循环中计算编辑损失 Le（传播 QA 的负对数似然）和局部性损失 Lloc。
        f. 更新超网络参数 ϕ 以最小化总损失 L = cedit·Le + Lloc。
    3. 在测试时，直接对输入的注入事实运行该编辑流程，得到更新后的模型用于推理。

### 3. 实验设计

- **数据集**：
    - **RippleEdit**：包含 Popular、Random、Recent 子集，共约 4686 个编辑实例，每个编辑附有 6 种传播类型问题（逻辑泛化、混合 I/II、主体别名、遗忘、关系特异性）。从中划分训练 3686、验证 500、测试 500。
    - **StoryPropagation**（新构建）：围绕 7 类实体（人、语言、国家、事件、组织、物种、创意作品）和 38 种关系，每个实例包含一个虚构故事（涉及 3 个真实实体）和多个多跳传播问答题。生成 5K 实例，划分训练 4K、验证 500、测试 500。额外构建三个 OOD 测试集：OOD(Entity)、OOD(Relation)、OOD(Both)。
- **评估指标**：
    - 精确匹配（EM）（RippleEdit 原指标）
    - LLM-as-Judge（LLM-Acc）：使用 GPT-4o-mini 判断助手回答是否匹配任何参考答案。
- **对比方法**：
    - 基线：Prepend（注入事实前缀）、CPT（Full 和 Mid-Upper）、MEMIT（两种协方差矩阵）、MEND（标准配置和 Mid-Upper）。
    - 所有方法基于 Llama-3.2-1B-base 并在 TriviaQA 上 SFT 得到 QA 版本（-QA）；在 StoryPropagation 上额外格式对齐得到 -FM。
    - 还测试了 Qwen2.5-1.5B 和 Llama-3.2-3B 以验证泛化性。

### 4. 资源与算力

- 论文未明确说明 GPU 型号、数量及训练时长。仅在附录 G 提到：“主要实验使用 NVIDIA A40 48GB GPU 和 AMD EPYC 7413 24-Core Processor；更大模型使用 NVIDIA GH200 120GB 和 ARM Neoverse-V2。” 并说明“元训练通常在 4–10 小时之间”。未给出精确的 GPU 小时数或总能耗。

### 5. 实验数量与充分性

- **实验数量**：
    - 在 RippleEdit 上进行了完整的测试，报告了 EM 和 LLM-Acc 两种指标，并按 verbatim/non-verbatim 以及传播类型细分（见表 1、表 15、16）。
    - 在 StoryPropagation 上进行了主实验（表 2）及 OOD 泛化实验（三个子集）。
    - 消融实验：外循环目标（传播 vs 改写）、内循环损失（CLM vs SFT ）、更新层选择（Mid-Upper vs Upper）（表 4）。
    - 效率实验（表 3）：统计了 50 个样本的峰值显存和总运行时间。
    - 跨模型验证（附录表 17、18）：使用 Qwen2.5-1.5B 和 Llama-3.2-3B。
- **充分性与公平性**：
    - 对比方法覆盖了主流编辑方法（MEND、MEMIT、CPT）以及强基线 Prepend，超参数设置尽量公平（MEMIT 和 MEND 也使用相同元训练数据）。
    - 所有统计通过 paired bootstrap test (p=0.05) 进行显著性标记。
    - 识别了 RippleEdit 中 31.9% 的传播问题答案可直接于注入事实中复制（verbatim），因此分别报告 verbatim 和 non-verbatim 结果，避免夸大。这一识别体现了实验的客观性。
    - 消融实验充分验证了各设计决策的影响。

### 6. 主要结论与发现

- **RippleEdit**：PropMEND 在非逐字传播问题上（non-verbatim efficacy）达到 22.4% LLM-Acc，是次优基线（MEMIT 12.7%）的 **1.76 倍**；在 verbatim 问题上也与最强 CPT (Full) 相当（75.7% vs 76.0%）。
- **StoryPropagation（In-Domain）**：PropMEND 以 76.7% 的正确定率远超其他参数方法（Prepend 40.4%），且局部性保持良好（95.5%）。
- **OOD 泛化**：在 OOD(Entity) 上 PropMEND 保持 35.2%（次优 CPT Full 17.0%）；在 OOD(Both) 上 18.3%（次优 12.9%），说明仍存在困难但显著领先。
- **效率相近**：PropMEND 在相似层数编辑时与 MEND 内存和耗时相当。
- **设计选择**：外循环使用传播问题比使用改写问题重要得多；CLM 损失优于 SFT 损失；编辑中上层（Mid-Upper）比顶层更有效。

### 7. 优点

- **方法创新**：首次将超网络元学习直接针对知识传播任务优化，突破了现有方法仅能复制输入事实的限制。
- **实验严谨**：
    - 识别 verbatim 问题并分别报告，防止误导性结论。
    - 构建了可控的 StoryPropagation 数据集，专门针对已知实体和关系，并设计了三种 OOD 设置，评估泛化能力。
    - 消融实验覆盖了核心设计维度，并进行了显著性检验。
- **性能突出**：在多个设置上显著超越现有方法，尤其在非 verbatim 传播问题上效果翻倍。
- **效率合理**：参数编辑速度较快（一次性编辑），与 MEND 可比的资源消耗。

### 8. 不足与局限

- **单次编辑限制**：仅支持单次知识注入，未评估多轮或批量注入场景。论文承认该局限，但注明超网络可通过内循环多梯度更新扩展。
- **参数效率**：超网络的大小与编辑的语言模型几乎相同，参数开销大。继承自 MEND 的缺点。
- **评估范围狭窄**：仅评测短答案问答，未涉及长文本生成中的知识传播。论文提到初步实验发现 PropMEND 在生成长答案时可能降低模型生成质量。
- **OOD(Both) 性能仍低**：在实体和关系均未见时仅 18.3%，表明泛化能力有限，需要进一步改进。
- **数据集局限性**：
    - RippleEdit 中包含许多尾实体，模型本身对其知识不足，影响传播判断。
    - StoryPropagation 为合成数据，可能与真实场景存在差距。
- **未讨论安全管理**：未提及编辑可能引入虚假知识或恶意操纵的风险。

（完）
