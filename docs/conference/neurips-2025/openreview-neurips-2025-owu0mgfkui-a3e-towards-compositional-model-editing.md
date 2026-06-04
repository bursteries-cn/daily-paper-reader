---
title: "A$^3$E: Towards Compositional Model Editing"
title_zh: A$^3$E：面向组合模型编辑
authors: "Hongming Piao, Hao Wang, Dapeng Wu, Ying Wei"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=OwU0mgfKUi"
tags: ["query:model-edit"]
score: 9.0
evidence: 提出面向大语言模型的组合模型编辑方法
tldr: 现有模型编辑方法通常在孤立场景下评估，忽略了需要结合多个编辑来回答复杂现实问题的组合编辑场景。本文定义了组合模型编辑任务，并系统构建了基准测试，以评估模型在整合多个知识编辑后的表现。该方法能够使大语言模型同时利用多个编辑信息，如在医学领域同时回答新冠症状包括发烧和味觉丧失。该工作为模型编辑的实际应用提供了更全面的评估框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1388, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1317, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 450, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 879, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1385, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1170, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-owu0mgfkui/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 772, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 734, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1397, \"height\": 1046, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1366, \"height\": 877, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1402, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1178, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 898, \"height\": 987, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 613, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 951, \"height\": 114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1399, \"height\": 984, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1307, \"height\": 988, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1305, \"height\": 988, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1388, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 787, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 794, \"height\": 114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 983, \"height\": 109, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 758, \"height\": 114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1362, \"height\": 1419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 942, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1366, \"height\": 930, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-owu0mgfkui/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1359, \"height\": 1034, \"label\": \"Table\"}]"
motivation: 现有模型编辑方法仅评估单个编辑效果，无法应对需要整合多个编辑的复杂现实问题，如组合医学知识。
method: 定义组合模型编辑任务，设计基准评估流程，要求模型同时利用多个编辑信息回答多角度问题。
result: 系统实验显示现有编辑方法在组合场景下性能大幅下降，凸显了该任务的重要性和挑战性。
conclusion: 组合模型编辑是一个必要且未充分研究的领域，已有的编辑方法远未达到实际应用需求。
---

## Abstract
Model editing has become a *de-facto* practice to address hallucinations and outdated knowledge of large language models (LLMs). However, existing methods are predominantly evaluated in isolation, i.e., one edit at a time, failing to consider a critical scenario of compositional model editing, where multiple edits must be integrated and jointly utilized to answer real-world multifaceted questions. For instance, in medical domains, if one edit informs LLMs that COVID-19 causes "fever" and another that it causes "loss of taste", a qualified compositional editor should enable LLMs to answer the question "What are the symptoms of COVID-19?" with both "fever" and "loss of taste" (and potentially more). In this work, we define and systematically benchmark this compositional model editing (CME) task, identifying three key undesirable issues that existing methods struggle with: *knowledge loss*, *incorrect preceding* and *knowledge sinking*. To overcome these issues, we propose A$^3$E, a novel compositional editor that (1) ***a**daptively combines and **a**daptively regularizes* pre-trained foundation knowledge in LLMs in the stage of edit training and (2) ***a**daptively merges* multiple edits to better meet compositional needs in the stage of edit composing. Extensive experiments demonstrate that A$^3$E improves the composability by at least 22.45\% without sacrificing the performance of non-compositional model editing.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的大语言模型（LLM）编辑方法通常在**单次编辑**的孤立场景下评估，即一次只编辑一个事实。然而，现实世界的复杂问题往往需要**同时整合多个编辑知识**才能回答（例如，医学上新冠的症状包括“发烧”和“味觉丧失”，需要合并两个编辑才能完整回答）。目前缺乏对这种**组合模型编辑（Compositional Model Editing, CME）** 能力的系统定义、基准测试和解决方案。
- **整体含义**：论文首次形式化定义 CME 任务，识别出现有方法在组合场景下的三大失败模式（知识丢失、错误前置、知识沉没），并提出了一个名为 **A³E** 的专用组合编辑器，显著提升了模型在需要同时利用多个编辑时的表现。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：利用 Transformer 前馈网络（FFN）中**下投影矩阵（W_down）** 存储的预训练基础知识（foundation knowledge）来组合新知识。通过**只编辑上投影矩阵（W_up）**（低秩形式）避免对基础知识的直接修改，同时使用自适应掩码、正则化和自适应合并来提升可组合性。
- **关键技术细节**：
  - **编辑训练阶段**：
    - **自适应组合（Adaptive Combination）**：每个编辑训练一个 LoRA 对（A, B），但只在 W_up 上生效。对 B 施加**自适应掩码**，仅保留与预训练基础知识最相关的部分（通过点积计算相关性，选择 top-k 的行）。
    - **自适应正则化（Adaptive Regularization）**：
      - **Lc**：约束最后一个答案 token [la] 在 FFN 层的 hidden state 变化量小，以保持上下文跟随能力（context-preserving）。
      - **Lo**：约束非标签位置上的 logits，减少错误前置（incorrect preceding）。
    - 联合目标：**L = Le + αLc + βLo**。
  - **编辑组合阶段**：
    - **自适应合并（Adaptive Merging）**：通过向量数据库（储存所有编辑的 key-value）过滤出相关编辑。对于不同编辑的激活向量 ∆a，若存在符号冲突（一个为正、一个为负），则将相应分量置为零，避免冲突干扰。
    - **算法流程**（文字说明）：
      1. 训练每个编辑时，计算掩码 M，替换 FFN 前向为 `FFN_edit(hin, A, B, M)`，更新 (A, B) 并保存到向量数据库。
      2. 推理时，用测试问题的隐藏表示检索库，选出相关编辑的 (A, B) 集合 S。
      3. 对 S 中所有 ∆a 执行自适应合并（符号冲突归零），然后累加到原始前向中，生成输出。

### 3. 实验设计：数据集、场景、基准、对比方法

- **数据集**：使用 **PEAK-CF**（1,949 条）和 **PEAK-T**（922 条），这些数据包含多答案问题。选取 LLM 至少缺失 4 个答案的问题构建 CME 测试。
- **场景与任务**：四种 CME 任务
  - **独立多答案组合（IMAC）** & **多答案组合（MAC）**：多个编辑对应同一子问题的不同答案。
  - **独立多问题组合（IMQC）** & **多问题组合（MQC）**：多个编辑对应不同子问题，需合并回答。
- **对比方法**：FT（全微调）、ROME、KE、MEND、AlphaEdit、WISE、T-patcher、GRACE、MELO。
- **评估指标**：
  - **SR-S**：所有编辑答案在正确位置输出（无错误前置）的成功率。
  - **SR-1**：编辑答案出现在输出中的成功率。
  - **GSR**：面向改写问题的 SR-S。
  - **LSR**：面向无关问题（ locality ）的 Rouge-L F1。
- **设置**：主要使用 Llama3-8B，也使用了 Mistral-7B 和 Llama3-70B；编辑数量从 50 到 3898；组合数从 1 到 4；三种不同的 few-shot prompt。

### 4. 资源与算力

- **GPU**：8 张 NVIDIA RTX 5880 Ada Generation GPU。
- **训练**：每个编辑训练 **50 个 epoch**，学习率 0.01。额外 FLOPs 分析表明 A³E 的相对增量极小（论文附录 F 提供了详细表格）。
- 论文未报告总训练时间或算力消耗的具体数值。

### 5. 实验数量与充分性

- **实验组数**：涵盖 2 个数据集 × 4 种 CME 任务 × 10 个基线 → 超过 80 组主实验；外加消融研究（7 种变体）、不同编辑数量（全量 3898/1984）、不同组合数量（1-4）、不同 backbone（2 种）、不同 prompt（3 种）、非组合性 ME（2 个经典数据集 ZsRE 和 Counterfact）、更大模型（70B）验证等，总计 **数百次实验**。
- **充分性与公平性**：实验设计系统，覆盖了训练、组合、泛化、局部性等全部维度；消融实验逐项验证各组件贡献；严格保持每个编辑训练的次数和方式一致；指标定义清晰（SR-S 等）且考虑了顺序敏感性。结论可靠、客观。

### 6. 论文的主要结论与发现

- **主要结论**：提出的 **A³E** 在所有四种 CME 任务上，相比最佳基线（WISE、GRACE、MELO）**在 SR-S 上至少提升 22.45%**，同时不降低非组合编辑性能（与基线持平）。
- **关键发现**：
  - **Finding 1**：只编辑 W_up 足以保证非组合性能，且因为保持 W_down 的预训练知识，可组合性更高。
  - **Finding 2**：减少最后一个答案 token 隐藏状态的变化有助于保持上下文跟随（context-preserving），进而提升 SR-S。
  - **Finding 3**：组合阶段将不同编辑中符号冲突的 ∆a 分量置零（自适应合并）可以缓解干扰，进一步提高可组合性。

### 7. 优点

- **问题定义清晰**：首次系统定义组合模型编辑任务，填补了领域空白。
- **方法创新**：双阶段框架（训练 + 组合）有效利用了预训练基础知识；自适应掩码和自适应合并针对 CME 的三大失败模式设计，理论合理且实验验证。
- **性能优异**：在多个 backbone、数据集、组合数、编辑数量下均领先，且兼容非组合场景。
- **实验全面**：包含大量对比、消融、泛化、鲁棒性分析，客观公正。
- **可解释性**：提供的 Finding 及可视化（图 4-6）帮助理解失败原因和方法有效性。

### 8. 不足与局限

- **组合质量仍非完美**：即使 A³E 大幅提升，但在编辑数量极大或组合数增多时，SR-S 仍有下降（如组合数 10 时 SR-1 仅 17.2%），未达完全准确。
- **依赖向量数据库**：组合阶段需要高效的检索机制，论文未深入探讨数据库的组织（如 key 的选取、阈值设置），可能在实际噪声环境下影响检索精度。
- **仅适用于白盒模型**：需要修改 FFN 权重，无法直接用于黑盒 API 模型。
- **局限于低秩编辑**：仅使用了 W_up 的低秩编辑，可能在其他架构或更大模型中存在表达能力上限。
- **未全面分析计算开销**：仅提供了额外 FLOPs 估算，但缺乏对实际运行时间和显存增长的系统测量。
- **数据集局限性**：PEAK-CF/PEAK-T 为英文数据集，未验证其他语言或领域（如法律、金融）的泛化能力。
- **未处理编辑间的固有矛盾**：对于根本冲突的编辑（如同一事实的不同版本），自适应合并可能无法解决，论文未讨论。

（完）
