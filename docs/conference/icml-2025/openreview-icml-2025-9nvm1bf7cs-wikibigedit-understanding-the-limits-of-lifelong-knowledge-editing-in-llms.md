---
title: "WikiBigEdit: Understanding the Limits of Lifelong Knowledge Editing in LLMs"
title_zh: WikiBigEdit：理解大型语言模型中终身知识编辑的局限性
authors: "Lukas Thede, Karsten Roth, Matthias Bethge, Zeynep Akata, Thomas Hartvigsen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9NVm1Bf7CS"
tags: ["query:model-edit"]
score: 9.0
evidence: 大规模终身知识编辑基准
tldr: 知识编辑方法在真实场景下的终身学习能力缺乏大规模评估。本文提出WikiBigEdit基准，包含超过50万问答对，基于维基数据真实编辑构建，支持自动扩展。通过该基准评估现有知识编辑技术，发现它们在处理实际规模编辑时记忆和泛化能力不足，性能显著下降。该平台为终身知识编辑提供了标准化评估，推动了更实用的编辑方法发展。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1768, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1760, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1763, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1402, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1392, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1406, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1753, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1762, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1765, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 875, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1769, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1766, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1233, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1048, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9nvm1bf7cs/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1766, \"height\": 355, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9nvm1bf7cs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9nvm1bf7cs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 697, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9nvm1bf7cs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9nvm1bf7cs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1753, \"height\": 877, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9nvm1bf7cs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1428, \"height\": 1171, \"label\": \"Table\"}]"
motivation: 现有知识编辑基准规模小且合成化，无法反映真实场景下的终身编辑需求。
method: 基于维基数据真实编辑自动构建大规模问答对基准，并支持持续扩展。
result: 现有知识编辑方法在大规模真实编辑下表现不佳，暴露出记忆和泛化能力缺陷。
conclusion: WikiBigEdit为终身知识编辑提供了标准化评估平台，推动更实用的编辑方法发展。
---

## Abstract
Keeping large language models factually up-to-date is crucial for deployment, yet costly retraining remains a challenge. Knowledge editing offers a promising alternative, but methods are only tested on small-scale or synthetic edit benchmarks. In this work, we aim to bridge research into lifelong knowledge editing to real-world edits at practically relevant scale. We first introduce \texttt{WikiBigEdit}; a large-scale benchmark of real-world Wikidata edits, built to automatically extend lifelong for future-proof benchmarking. In its first instance, it includes over 500K question-answer pairs for knowledge editing alongside a comprehensive evaluation pipeline. Finally, we use \texttt{WikiBigEdit} to study existing knowledge editing techniques' ability to incorporate large volumes of real-world facts and contrast their capabilities to generic modification techniques such as retrieval augmentation and continual finetuning to acquire a complete picture of the practical extent of current lifelong knowledge editing.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

**研究动机与背景**  
大型语言模型（LLM）在实际部署中必须保持事实准确性，但频繁的全模型重训练代价高昂。知识编辑技术可以局部注入/更新事实，但现有基准（如CounterFact、ZsRE等）规模小（<20K样本）、多为合成数据，且早于现代LLM的知识截止日期，无法反映真实世界的终身学习需求。因此，论文旨在构建一个大规模、基于真实世界编辑的终身知识编辑基准，并系统评估现有方法的局限性。

## 2. 论文提出的方法论

**核心思想**  
- 提出 **WikiBigEdit**，一个**大规模、可自动扩展的终身知识编辑基准**。  
- 通过定期比较 Wikidata 知识图谱的快照差异，提取真实事实修改（subject-relation-object三元组），并自动生成 QA 对及多维度评估数据。

**关键技术细节**  
1. **自动化管道（7步）**  
   - (1) 周期性抓取 Wikidata 快照，与上一版本对比得到**变化三元组**（用于编辑）和**不变三元组**（用于局部性评估）。  
   - (2) 初步过滤：排除循环依赖、非罗马字符、单字符、过长短语、多义三元组。  
   - (3) 生成局部性样本：为每个编辑找一个语义相似但答案不同的三元组。  
   - (4) 提取多跳推理对：通过中间实体链接两个编辑三元组，形成两跳事实（如 `podcast → named after → iPod → manufacturer → Apple`）。  
   - (5) 使用 GPT-4o-mini / GPT-3.5 将三元组转换为 QA 对（Update、Locality、Multi-hop）。  
   - (6) 生成**重述**（rephrase）和**角色风格**（personas）问题以测试泛化。  
   - (7) 最终质量过滤：确保问题包含主语、关系，答案正确。

2. **终身学习问题定义**  
   - 模型 `f_0` 接收事实更新流 `[u_1, ..., u_T]`，按批次 `[U_1, ..., U_B]` 处理。更新后模型需满足：新编辑准确、旧编辑保留、泛化到重述/多跳、局部性不变。

## 3. 实验设计

**数据集 / Benchmark**  
- **WikiBigEdit 第一版**：从2024年2月到7月的8个时间步，共 **502,382个QA对**（约690万词），每个时间步26K–121K样本。  
- 评估维度：**Update**（编辑自身）、**Rephrase**（同义改写）、**Personas**（5种角色风格）、**Mhop**（两跳推理）、**Locality**（局部性）。

**对比方法**  
- **知识编辑方法**：ROME、R-ROME、MEMIT、WISE。  
- **检索增强生成（RAG）**：使用 all-mpnet-base-v2 嵌入 + Annoy 近似近邻检索，top-2 检索，将结果拼入上下文。  
- **持续微调**：LoRA-FT（低秩适配持续训练）、LoRA-Merge（每时间步训练后与基模型插值合并，插值因子α=0.75实验最佳）。  
- **基线**：Pre-Edit（未编辑的原始模型）。

**评估模型**  
5个7B/8B参数的开源LLM：Llama-2-7B、Llama-3-8B、Mistral-7B、Gemma-7B、xGen-7B。

## 4. 资源与算力

论文仅说明实验在配备 **Nvidia A100 和 H100 GPU** 的集群上进行，使用 PyTorch 和 EasyEdit 代码库。**未明确给出具体GPU数量、训练时长或总消耗算力**。可以推断训练持续微调需要在每个时间步训练10轮，规模较大，但资源信息缺失。

## 5. 实验数量与充分性

论文进行了多组实验，较为充分：
- **主实验**：8个时间步 × 5个模型 × 5个评估维度 × 多种方法，结果取平均并报告标准差。
- **消融实验**：
  - RAG 的 top-k 检索数（1,2,5,10,100）对性能和时间影响（附录图15）。
  - LoRA 秩（rank=4 vs rank=64）的影响（图17）。
  - LoRA-Merge 的插值因子（α=0.5 vs 0.75）影响（图18）。
  - MEMIT 的批大小（1,1000,5000,10000）对编辑稳定性的影响（图20）。
- **分析实验**：时间分辨率、事实特异性（Infinigram频率、Wikipedia浏览量）对LLM性能的影响。
- **对比**：知识编辑方法在500步和完整时间步上的性能衰减（图19、21）。
- **客观性**：使用多个模型、标准评估流程，且公开代码，结果可复现。

总体实验设计合理，覆盖主要变量，但缺乏更大规模模型（>7B）的实验。

## 6. 论文的主要结论与发现

1. **知识编辑方法在大规模真实编辑下表现糟糕**：ROME、R-ROME、MEMIT 在几百次编辑内崩溃（模型崩塌）。WISE虽避免崩溃，但性能迅速衰减至预编辑水平。
2. **RAG 性能最优但推理成本高**：编辑准确率接近99%，并在重述、角色任务上大幅提升（78%、66%），但多跳推理仅微弱提升（约5个百分点），且随编辑量增加出现类似遗忘的退化。
3. **简单持续微调（LoRA-FT）可匹配甚至超越专用知识编辑方法**，但随时间步累积仍有明显遗忘。
4. **LoRA-Merge（持续微调+模型合并）表现最佳**：在100K编辑后显著优于纯持续微调和其他方法，且几乎无灾难性遗忘，甚至出现正向迁移。
5. **现实世界编辑的挑战**：LLM对近期（2023/2024年）和高度特异性事实的性能显著低于常识性事实。

## 7. 优点

- **规模与真实性**：比现有基准大一个数量级（502K QA对），基于真实Wikidata编辑，而非合成数据。
- **自动化管道**：可随时间自动扩展，支持未来持续更新，避免数据过时。
- **多维度评估**：不仅包含标准编辑指标（更新、局部性），还引入重述、角色、多跳推理，更全面衡量泛化能力。
- **对比全面**：不仅评估专用知识编辑方法，还引入RAG和持续微调等通用技术，提供了更完整的 baseline。
- **开源代码**：代码已公开，促进可复现性。

## 8. 不足与局限

- **实验覆盖不足**：所有模型均为7B/8B参数量，未测试更大模型（如70B或MoE）；评估仅依赖准确率，未考虑生成质量或事实性细粒度。
- **资源信息缺失**：未报告训练/推理所需的具体GPU时间或能耗，不利于成本评估。
- **基准来源单一**：仅基于Wikidata编辑，可能忽略其他类型的事实变化（如网页、书籍）。多跳推理仅限两跳，长链推理未覆盖。
- **方法局限**：RAG在多跳推理上表现弱，且检索成本随编辑量增长（但实验显示最多翻倍）；LoRA-Merge虽好，但α需要调参，且对初始模型依赖较强。
- **偏差风险**：QA生成依赖GPT-4/3.5，可能引入风格偏差或不准确的问题；过滤步骤（76%丢弃率）可能排除有用但格式异常的数据。
- **缺乏真实部署验证**：实验仅限离线评估，未模拟在线动态情况（如编辑顺序、时效性要求）。

（完）
