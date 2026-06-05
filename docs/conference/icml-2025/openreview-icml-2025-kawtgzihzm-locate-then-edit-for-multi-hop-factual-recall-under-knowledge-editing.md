---
title: Locate-then-edit for Multi-hop Factual Recall under Knowledge Editing
title_zh: 知识编辑下的多跳事实回忆定位-编辑方法
authors: "Zhuoran Zhang, Yongxiang Li, Zijian Kan, Keyuan Cheng, Lijie Hu, Di Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kAWtGZIHzm"
tags: ["query:model-edit"]
score: 9.0
evidence: 提出定位-编辑方法用于知识编辑后的多跳事实回忆
tldr: 该论文指出现有定位-编辑方法仅编辑浅层，导致多跳事实回忆困难。通过机制可解释性分析，发现多跳任务依赖深层MLP层，因此提出编辑深层MLP层的方法，显著提升了多跳知识编辑的性能，推动了知识编辑技术的发展。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1719, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 976, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 807, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1412, \"height\": 1360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1388, \"height\": 1016, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kawtgzihzm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1403, \"height\": 1528, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 695, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1402, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 761, \"height\": 862, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 690, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1605, \"height\": 878, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1411, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1590, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1591, \"height\": 773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 790, \"height\": 544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1801, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kawtgzihzm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1792, \"height\": 711, \"label\": \"Table\"}]"
motivation: 现有知识编辑方法在单跳任务中表现良好，但多跳事实回忆性能差，原因在于只编辑了浅层。
method: 利用机械可解释性分析识别多跳任务依赖的深层MLP层，并扩展定位-编辑范式到这些层。
result: 在多个多跳数据集上，新方法显著提升了编辑后的事实回忆准确率。
conclusion: 编辑深层是提升多跳知识编辑效果的关键，为后续研究提供了方向。
---

## Abstract
The locate-then-edit paradigm has shown significant promise for knowledge editing (KE) in Large Language Models (LLMs). While previous methods perform well on single-hop fact recall tasks, they consistently struggle with multi-hop factual recall tasks involving newly edited knowledge. In this paper, leveraging tools in mechanistic interpretability, we first identify that in multi-hop tasks, LLMs tend to retrieve knowledge with implicit subject information from deeper MLP layers, unlike single-hop tasks, which rely on shallow layers. This distinction explains the poor performance of current methods in multi-hop queries, as they primarily focus on editing shallow layers with single-hop edit prompts, leaving deeper layers unchanged. To address this, we propose IFMET, a novel locate-then-edit KE approach designed to edit both shallow and deep MLP layers. Beyond single-hop editing prompts, IFMET further incorporates multi-hop editing prompts to locate and modify knowledge across different stages of reasoning. Experimental results demonstrate that IFMET significantly improves performance on multi-hop factual recall tasks, overcoming the limitations of previous locate-then-edit methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有 locate-then-edit 范式下的知识编辑方法（如 ROME、MEMIT、PMET）在**单跳事实回忆**任务上表现优异，但在**多跳事实回忆**任务（涉及新编辑知识）上性能显著下降。例如，将“西班牙首都”从“马德里”改为“哈特福德”后，模型能正确回答单跳问题“西班牙首都是什么？”，但对多跳问题“巴勃罗·毕加索国籍所在国家的首都是什么？”却仍输出“马德里”。
- **研究动机**：解释这种失败原因并设计改进方法。作者认为，多跳任务中模型的知识检索机制与单跳不同，而现有方法仅编辑浅层 MLP 层，导致深层 MLP 层中未更新的知识在隐式推理步骤中被调用，从而输出错误答案。
- **背景**：知识编辑是修改大语言模型（LLM）中特定事实的低成本方法，分为权重保持和权重修改两类。locate-then-edit（定位-编辑）方法通过先定位知识存储层再优化权重进行编辑，具有计算成本低、编辑精准的优点。但前人工作主要针对单跳场景，未考虑多跳推理的机制差异。

## 2. 论文提出的方法论

- **核心思想**：通过机械可解释性工具（LogitLens 和因果干预实验）发现：
  - 在单跳任务中，模型在**主语 token 位置**通过**浅层 MLP** 检索事实。
  - 在多跳任务（以两跳为例）中，模型在**最后一个 token 位置**先累积**隐式主题信息**（第二跳的主题），然后通过**深层 MLP** 检索最终答案的事实。
  - 现有方法只用单跳编辑提示修改浅层 MLP，未更新深层 MLP，因此多跳任务失败。
- **关键技术细节 —— IFMET（Interpretability-Guided Furtherance Model Editing in a Transformer）**：
  1. **两阶段编辑**：
     - **第一阶段（首次编辑）**：使用传统的单跳编辑提示（如“The capital of Spain is”）编辑**浅层 MLP**（对 GPT-J 为第 3-8 层）。
     - **第二阶段（进一步编辑）**：为每个编辑实例构建一个**多跳编辑提示**（如“The capital city of the country where Barcelona is located is”），其中第一跳是前缀知识（例如“Barcelona is located in Spain”），第二跳是待编辑事实。使用该多跳提示编辑**深层 MLP**（对 GPT-J 为第 16-20 层）。
  2. **多跳提示构建**：提供两种方法：
     - 基于 WikiData 的 SPARQL 查询，获取与编辑主语相关的有效前缀三元组。
     - 直接利用模型自身（通过提示生成）来提取前缀知识。
  3. **编辑算法**：基于 PMET 的优化框架，假设 MLP 的 feed-forward 网络存储 key-value 记忆。每个编辑实例 (s, r, o→o*) 通过 **Search** 过程（梯度下降优化 δ）得到目标表示 v*，再由 **Calculate** 过程（闭式解）更新权重矩阵 W_out。
- **关键公式**（文字说明）：
  - 目标函数包含保留原知识和编辑新知识的损失项：`min λ * ||W' K0 - W_out K0||^2 + ||W' KE - VE||^2`。
  - 迭代优化 δ 使模型在新提示下最大化编辑答案的概率，同时 KL 散度约束保持模型整体行为。

## 3. 实验设计

- **数据集与场景**：
  - **MQuAKE-3K**：超过 3000 个多跳问题（2-4 跳），每个实例包含一个或多个事实编辑及对应的多跳问题。分为“Pre”（编辑发生在第一跳）和“Post”（编辑发生在后续跳）两种场景。
  - 额外使用 MQuAKE-CF 子集（约 300 个两跳样本）进行机制分析和消融实验。
- **Benchmark**：多跳问答准确率（Multi-hop Acc），分为“编辑答案准确率”（模型输出新事实）和“未编辑答案准确率”（模型输出原事实）。还评估了单跳 Efficacy、Paraphrase、Specificity 等指标。
- **对比方法**：
  - **权重修改方法**：FT（fine-tuning）、MEND、ROME、MEMIT、PMET（SOTA locate-then-edit）。
  - **权重保持方法**（附录中讨论）：RAG 类方法（如 MeLLo）。
  - 基线包括未编辑的原模型（Base）。
- **模型**：主要使用 GPT-J-6B，也扩展到 LLaMA-2-7B。

## 4. 资源与算力

- 文中**未明确说明**使用的 GPU 型号、数量及总训练时长。
- 仅在附录中提及部分配置：
  - 在 GPT-J-6B 上，采样 100,000 次 Wikitext（fp32 精度）估计协方差矩阵。
  - 优化步数限制为 30，学习率 0.2。
  - 对 LLaMA-2-7B，平均每个编辑实例约耗时 3.4 秒（IFMET）。
- 由于未提供硬件详情，无法评估算力需求的具体规模，但方法本身是轻量级、近实时的。

## 5. 实验数量与充分性

- **实验组数**：
  - 主表（Table 3）：对比 6 种方法在 MQuAKE-3K 上的总体准确率，并按跳数（2/3/4）和编辑数（1/2/3/4）细分。
  - 表 4：针对 Pre/Post 场景的编辑答案与未编辑答案准确率。
  - 表 5：消融实验（w/o First, w/o Multi, w/o Deeper, w/o Last）及与 PMET 的对比。
  - 附录表 7、8：在 GPT-J 和 LLaMA-2-7B 上更详细的消融（含 Efficacy、Specificity、Paraphrase）。
  - 图 5：不同编辑批次大小（1/100/1000/3000）的对比。
  - 时间效率比较（表 9）。
  - 使用模型自身构造多跳提示的泛化结果（表 8 的 w_Multi_model）。
  - 与权重保持方法的讨论（附录 G.1）。
- **充分性与公平性**：
  - 实验覆盖了多种编辑场景（单跳/多跳、Pre/Post、不同跳数）、多个模型（GPT-J 和 LLaMA-2）、多种批次规模。
  - 消融实验系统验证了每个组件的必要性，结果客观。
  - 对比方法使用开源实现和默认超参数，设置一致。
  - 但仅在一个多跳数据集（MQuAKE）上评估，且模型限于 6B-7B 规模，未测试更大模型（如 GPT-3、LLaMA-3-70B），可能限制泛化性。

## 6. 论文的主要结论与发现

- **机制发现**：
  - 多跳任务中，模型在最后一个 token 位置通过深层 MLP（如第 19-25 层）检索隐式主题对应的知识；而单跳任务依赖浅层 MLP（如第 3-8 层）和主语 token 位置。
  - 因果干预实验证实，修改深层 MLP 中隐式主题的信息会显著影响最终答案概率。
- **方法有效性**：
  - IFMET 在 MQuAKE-3K 上多跳准确率提升 78%（相比 PMET），在 Post 场景尤为显著（从 12.63% 提升至 28.90%）。
  - 所有消融实验表明：两阶段编辑、使用多跳提示、编辑深层 MLP 缺一不可。
  - 在 LLaMA-2-7B 上也获得一致改进，说明发现具有跨模型普适性。
- **局限性承认**：特异性（Specificity）略有下降（约 -10%），但整体平衡可接受。

## 7. 优点

- **创新性**：首次从机械可解释性角度揭示单跳与多跳推理的差异，并据此设计编辑方法，提供深层理解。
- **方法论全面**：包含机制分析、因果干预验证、针对性两阶段编辑算法，来源清晰。
- **实验充分**：在多个模型、多种批次、多种指标上系统验证，消融实验设计合理。
- **实用性强**：方法仅增加少量时间开销（约 1.5-2.5 倍于单阶段方法），且可依赖模型自身构造多跳提示，降低对额外知识库的依赖。
- **可迁移性**：不仅适用于 GPT-J，在 LLaMA-2 上也有效，且对编辑批次规模有鲁棒性。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅使用一个多跳数据集（MQuAKE-3K），且问题模板为 Cloze 和 QA 格式，可能未覆盖更复杂的多跳推理（如涉及逻辑否定、时序）。
  - 仅在 6B 和 7B 模型上验证，未测试更大规模 LLM（如 70B、130B），机制是否一致未知。
- **特异性下降**：相比 PMET，IFMET 的 Specificity 在 GPT-J 上降低约 11%，编辑会对邻域知识产生一定干扰。
- **对 PMET 的依赖性**：IFMET 的第一和第二阶段均基于 PMET 的优化框架，若 PMET 本身存在缺陷（如数值稳定性、对长文本支撑不足），IFMET 也会继承。
- **多跳提示构建成本**：基于 WikiData 的方法需要 SPARQL 查询和预处理，基于模型自身的方法可能需要额外推理，增加工程复杂度。
- **未考虑更大编辑批次**：当同时编辑 3000 个事实时，IFMET 仍优于 PMET，但绝对准确率仍较低（约 25%），说明大规模场景下方法仍有改进空间。
- **时间开销**：虽可接受，但未提供在更大模型上的实际延迟数据。

（完）
