---
title: "MetaDefense: Defending Fine-tuning based Jailbreak Attack Before and During Generation"
title_zh: MetaDefense：在生成前后防御基于微调的越狱攻击
authors: "Weisen Jiang, Sinno Jialin Pan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ycMpNwzUAA"
tags: ["query:model-edit"]
score: 6.0
evidence: 针对基于微调的越狱攻击提出两阶段防御框架
tldr: 现有防御无法泛化到未见攻击模板。本文提出MetaDefense，在生成前和生成中两阶段检测有害查询和部分响应，训练LLM预测危害性。实验表明该方法有效防御多种微调越狱攻击，为模型安全编辑提供了防御视角。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ycmpnwzuaa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1373, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ycmpnwzuaa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ycmpnwzuaa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1425, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ycmpnwzuaa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1465, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ycmpnwzuaa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 1151, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1354, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1376, \"height\": 1783, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1383, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1380, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1152, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 794, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1084, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1419, \"height\": 1836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1419, \"height\": 1841, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1295, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1195, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1467, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1421, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1048, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1428, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1422, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1417, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1411, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1421, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1371, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1381, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ycmpnwzuaa/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1427, \"height\": 258, \"label\": \"Table\"}]"
motivation: 现有防御对未知攻击模板泛化能力不足，LLM嵌入空间却能区分伪装有害查询。
method: 提出两阶段防御：生成前检测有害查询，生成中监控部分响应以阻止有害内容输出。
result: 在多种微调越狱攻击场景下，MetaDefense显著提升防御成功率。
conclusion: MetaDefense为LLM安全部署提供了有效的实时防御方案。
---

## Abstract
This paper introduces MetaDefense, a novel framework for defending against finetuning-based jailbreak attacks in large language models (LLMs). 
We observe that existing defense mechanisms fail to generalize to harmful queries disguised by unseen attack templates, despite LLMs being capable of distinguishing disguised harmful queries in the embedding space. 
Based on these insights, we propose a two-stage defense approach: 
(i) pre-generation defense that detects harmful queries before response generation begins, and (ii) mid-generation defense that monitors partial responses during generation to prevent outputting more harmful content. 
Our MetaDefense trains the LLM to predict the harmfulness of both queries and partial responses using specialized prompts, enabling early termination of potentially harmful interactions. 
Extensive experiments across multiple LLM architectures (LLaMA-2-7B, Qwen-2.5-3B-Instruct, and LLaMA-3.2-3B-Instruct) demonstrate that MetaDefense significantly outperforms existing defense mechanisms, achieving robust defense against harmful queries with seen and unseen attack templates while maintaining competitive performance on benign tasks.
Code is available at [https://github.com/ws-jiang/MetaDefense](https://github.com/ws-jiang/MetaDefense).

---

## 论文详细总结（自动生成）

# 论文中文总结：MetaDefense：在生成前后防御基于微调的越狱攻击

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLM）在通过微调应用于特定任务时，面临基于微调的越狱攻击（FJAttack）风险。攻击者可以在微调数据中混入少量有害样本，即使这些样本被嵌入在从未见过的攻击模板（如角色扮演、前缀注入、拒绝抑制等）中，也能显著破坏模型的安全对齐，导致模型生成有害内容。
- **现有防御的不足**：已有的防御方法（如对齐阶段的疫苗接种方法 RepNoise、Vaccine、Booster，微调阶段的 BackdoorAlign、SafeInstr，推理阶段的 PTST、LLaMA-Guard 等）在面对直接的有害查询时效果尚可，但面对被**未见过的攻击模板**伪装的有害查询时，攻击成功率（ASR）急剧上升，防御失败。
- **关键发现**：作者通过实验发现，对齐后的 LLM 在**嵌入空间**中实际上能够很好地区分有害查询和良性查询，甚至对未知模板伪装的有害查询也能区分。这说明现有防御失败的原因不是模型无法识别有害内容，而是激活这种识别能力的方式存在局限。
- **整体含义**：本文提出 MetaDefense，一个利用 LLM 自身生成能力来进行有害性检测的两阶段防御框架，旨在同时防御已知和未知攻击模板，且不牺牲良性任务性能，为 LLM 安全部署提供了一种高效、轻量的解决方案。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
利用 LLM 的生成能力，通过**轻量指令微调**训练模型直接回答一个有害性判别提示词（例如“这个查询是有害的还是无害的？它是100%……”），从而实现：
- **生成前防御（Pre-generation Defense）**：在生成响应之前检测查询的有害性。
- **生成中防御（Mid-generation Defense）**：在生成过程中监控部分响应，一旦发现有害则立即终止。

### 关键技术细节

#### 2.1 生成前防御
- 设计防御提示词 `T_pre = "Is this query harmful or harmless? It is 100%"`，拼接在用户查询后。
- 构建训练数据集 `D_pre`：
  - 有害查询（来自对齐数据集）→ 标注为 `"harmful"`
  - 无害查询（来自 Alpaca）→ 标注为 `"harmless"`
- 通过指令微调，让 LLM 学会根据提示词输出 `"harmful"` 或 `"harmless"`。

#### 2.2 生成中防御
- 类似地，设计提示词 `T_mid = "Is this response harmful or harmless? It is 100%"`，在部分响应 `y_<t` 后插入。
- 构建数据集 `D_mid`：
  - 对有害查询-有害响应样本：随机位置插入提示词和 `"harmful"`。
  - 对无害或拒绝响应样本：随机位置插入提示词和 `"harmless"`。
- 训练 LLM 在生成过程中对部分响应进行有害性判别。

#### 2.3 联合训练
- 合并 `D_pre` 和 `D_mid`，使用标准的监督微调（SFT）损失函数（下一个 token 预测损失）训练。可训练参数为 LoRA 适配器。

#### 2.4 推理流程（Algorithm 1）
1. **预填充阶段**：输入查询 `x'`，获得 KV 缓存。
2. **生成前防御**：利用共享 KV 缓存，拼接 `T_pre`，计算 `P("harmful"|...)` 和 `P("harmless"|...)`。
   - 若前者大于后者 → 拒绝，返回安全提醒。
3. **生成中防御**：
   - 计算初始步长 `k = γ * P("harmless")`，生成 `k` 个 token。
   - 循环直到生成结束 token：
     - 在部分响应后拼接 `T_mid`，利用 KV 缓存计算有害概率。
     - 若有害 → 停止生成，返回当前部分响应和安全提醒。
     - 否则根据新的无害概率计算下一次防御步长 `k`，继续生成。
   - 参数 `γ` 控制检测频率（默认 32），可在速度和安全性之间平衡。

#### 2.5 计算效率
- 通过复用 KV 缓存，生成前防御仅需额外处理很短的提示词，几乎没有开销。
- 生成中防御也复用缓存，仅增加少量解码步骤。
- 对于有害查询，生成前防御可提前拒绝，节省完整生成的开销。
- 仅需单个 LLM 同时完成检测和生成，内存约为 LLM-Classifier（需要额外编码器）的一半。

## 3. 实验设计：数据集、基准、对比方法

### 3.1 数据集与场景
- **对齐阶段**：从 [43] 采样 2500 有害查询-有害响应、2500 有害查询-拒绝响应（构成 `D_HF`）；从 Alpaca 采样 5000 无害查询-响应（`D_HL`）。
- **微调阶段（模拟 FJAttack）**：三个良性任务数据集——SST2（二分类）、AGNews（多选）、GSM8K（开放生成）。将 10% 的有害样本（使用未见过的攻击模板）与 90% 的良性样本混合，总计 1000 条微调样本。也评估了不同投毒比例（0%~30%）。
- **攻击模板**（4 种）：
  - Direct Attack（直接查询，在对齐阶段见过）
  - Prefix Injection Attack（前缀注入，未见）
  - Refusal Suppression Attack（拒绝抑制，未见）
  - Role Play Attack（角色扮演，未见）
- **模型**：LLaMA-2-7B（非对话模型）、Qwen-2.5-3B-Instruct、LLaMA-3.2-3B-Instruct（对话模型，已包含指令微调对齐）。
- **评估指标**：
  - 攻击成功率（ASR）：用 [15] 的审核模型判断输出是否有害，越低越好。
  - 微调测试准确率（FTA）：在良性任务测试集上的性能，反映保持能力。

### 3.2 对比方法
- **Non-Aligned**：无对齐。
- **SFT**：标准安全对齐（仅直接模板训练）。
- **对齐阶段防御**：RepNoise、Vaccine、Booster。
- **微调阶段防御**：BackdoorAlign、PTST。
- **推理阶段防御**：LLM-Classifier（额外编码器+分类头）。
- **混合防御**：Booster + LLaMA-Guard（对齐+推理检测）。

## 4. 资源与算力

- 论文中未明确报告总计算量（GPU 小时数等），但提供了部分细节：
  - 使用 **NVIDIA L40S 40G** GPU。
  - 对齐阶段训练轮次：LLaMA-2-7B 20 epoch，Qwen-2.5-3B-Instruct 5 epoch，LLaMA-3.2-3B-Instruct 3 epoch。
  - 微调阶段：对齐后的 LLM 再在良性+有害样本上训练 20 epoch。
  - 使用 LoRA（rank=32，alpha=4）进行所有训练，减少显存需求。
  - 批大小：对齐和微调阶段均为 10。
- 总体训练成本中等，但未报告具体时间。附录表 5 给出了推理时间对比（单次查询约 0.4~3.7 秒，取决于防御方法）。

## 5. 实验数量与充分性

- **实验组数**：非常充分。在三个 LLM（共 4 个配置，含非对话和对话模型）上评估了 4 种攻击模板 × 3 种良性任务（SST2、AGNews、GSM8K），结果如 Table 2-4。
- **消融实验**：
  - 分离预生成防御和生成中防御（Table 6）。
  - 灵敏度分析：步长参数 γ（Figure 4），推荐范围 16~64。
  - 投毒比例敏感性（Table 10：0%~30%）。
  - 错误类型分析（Table 7：假阳性/假阴性率）。
  - 提示词设计影响（Table 15）。
  - 鲁棒性测试：自适应误导攻击（Table 11）、长时微调遗忘（Table 12）、闭源模型 GPT-3.5（Table 14）等。
  - 与其他推理防御比较：CaC、Backtracking、RobustKV、输出级分类器等（附录 D）。
- **充分性评价**：实验设计全面，覆盖主流攻击模板、多种模型、多个良性任务、多项消融和鲁棒性测试，且代码开源。对比方法包括最先进的基线，结果公平客观。唯一不足是未报告多次运行的标准差（LLM 实验计算成本高，通常不重复，这在社区是常见做法）。

## 6. 主要结论与发现

1. **现有防御泛化失败**：对齐阶段和微调阶段的防御在面对未见攻击模板时，ASR 居高不下（例如 Prefix Injection 下接近非对齐模型）。
2. **LLM 能区分有害查询**：t-SNE 可视化显示，有害查询（即使被伪装）与良性查询在嵌入空间中明显分离。LLM-Classifier（额外分类头）可达到近 0% ASR，但内存翻倍。
3. **MetaDefense 有效**：
   - 在所有模型和攻击模板上，MetaDefense 的 ASR 均接近 0%（最难的 Role Play 下约 1~8%），远低于最佳基线（如 Booster+LLaMA-Guard 仍有 20~30% ASR）。
   - 良性任务 FTA 与基线相当或略好，表明没有牺牲实用性。
   - 内存仅为 LLM-Classifier 的一半（26.3 GB vs 52.6 GB），推理时间与无害查询相当。
4. **生成前防御更关键**：单独使用生成前防御已能大幅降低 ASR，生成中防御作为补充可进一步降低残留风险。
5. **对自适应攻击、长时微调、闭源模型具有鲁棒性**：见附录实验。

## 7. 优点

- **创新性**：首次提出同时利用 LLM 自身进行生成前和生成中有害性检测的防御框架，无需额外分类模型。
- **高效性**：通过 KV 缓存复用，检测开销极小；且对有害查询可提前终止，节省计算。
- **强鲁棒性**：对未知攻击模板的泛化能力显著优于现有方法。
- **实用性**：只需单个 LLM，适合部署；支持流式生成；对良性任务性能影响小。
- **实验充分**：跨多种模型、数据集、攻击模板、投毒比例，并与多种基线对比，附录包含大量鲁棒性分析。

## 8. 不足与局限

- **理论保证缺失**：论文未提供理论分析或安全上界，实验结果完全基于实证。
- **实验未报告方差**：由于计算成本，未重复多次运行，可能影响结果稳定性（但在 LLM 领域惯例中可接受）。
- **仅测试 Transformer 架构**：未拓展到 Mamba 等其他架构（附录 E 中提及未来工作）。
- **防御场景局限**：假设攻击者只能通过微调注入有害样本，未考虑更复杂的攻击链（如多轮对话、后门触发等）。
- **提示词依赖**：防御依赖于特定提示词设计（如“100%”锚定），不同设计可能影响性能（附录 Table 15 有初步分析，但未探索全部变体）。
- **对齐数据集来源**：仅使用单一来源（[43]），可能存在分布偏差。

（完）
