---
title: Detoxifying Large Language Models via Autoregressive Reward Guided Representation Editing
title_zh: 通过自回归奖励引导的表示编辑对大语言模型进行去毒化
authors: "Yisong Xiao, Aishan Liu, Siyuan Liang, Zonghao Ying, Xianglong Liu, Dacheng Tao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IUhOGH0WiL"
tags: ["query:model-edit"]
score: 9.0
evidence: 表示编辑用于去毒化直接对应模型编辑安全
tldr: 针对大语言模型生成毒性内容的问题，本文提出自回归奖励引导的表示编辑（ARGE）方法，在测试时通过奖励信号动态编辑模型内部表示，探索毒性与非毒性输出的转换空间，实现更精准的干预。实验表明，该方法显著降低有害输出率，同时保持生成流畅性，为模型安全部署提供轻量级可扩展的测试时去毒化方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuhogh0wil/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuhogh0wil/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 670, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuhogh0wil/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 670, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuhogh0wil/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 701, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuhogh0wil/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 633, \"height\": 420, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 542, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 507, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 100, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 725, \"height\": 128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 588, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 728, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 728, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1053, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1441, \"height\": 707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1114, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1171, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1311, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1310, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1310, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1308, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1309, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1309, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1311, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1303, \"height\": 1395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1158, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1444, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-iuhogh0wil/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1407, \"height\": 399, \"label\": \"Table\"}]"
motivation: 现有测试时去毒化方法干预不精确，未充分利用毒性与非毒性输出的转换空间。
method: 提出自回归奖励引导的表示编辑（ARGE），利用奖励信号驱动表示编辑以实现去毒化。
result: 在多个毒性检测基准上，ARGE有效降低有害输出率并保持生成质量，优于现有基线。
conclusion: 验证了表示编辑作为测试时去毒化手段的有效性，为LLM安全提供了新方案。
---

## Abstract
Large Language Models (LLMs) have demonstrated impressive performance across various tasks, yet they remain vulnerable to generating toxic content, necessitating detoxification strategies to ensure safe and responsible deployment. Test-time detoxification methods, which typically introduce static or dynamic interventions into LLM representations, offer a promising solution due to their flexibility and minimal invasiveness. However, current approaches often suffer from imprecise interventions, primarily due to their insufficient exploration of the transition space between toxic and non-toxic outputs. To address this challenge, we propose \textsc{A}utoregressive \textsc{R}eward \textsc{G}uided \textsc{R}epresentation \textsc{E}diting (ARGRE), a novel test-time detoxification framework that explicitly models toxicity transitions within the latent representation space, enabling stable and precise reward-guided editing. ARGRE identifies non-toxic semantic directions and interpolates between toxic and non-toxic representations to reveal fine-grained transition trajectories. These trajectories transform sparse toxicity annotations into dense training signals, enabling the construction of an autoregressive reward model that delivers stable and precise editing guidance. At inference, the reward model guides an adaptive two-step editing process to obtain detoxified representations: it first performs directional steering based on expected reward gaps to shift representations toward non-toxic regions, followed by lightweight gradient-based refinements. Extensive experiments across 8 widely used LLMs show that ARGRE significantly outperforms leading baselines in effectiveness (-62.21\% toxicity) and efficiency (-47.58\% inference time), while preserving the core capabilities of the original model with minimal degradation. Our code is available at the \href{https://anonymous.4open.science/r/ARGRE-6291}{anonymous website}.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义
- **研究动机**：大语言模型（LLMs）在预训练阶段从大规模未过滤语料中编码了有害模式，容易生成毒性（toxic）内容。确保其安全、负责任地部署需要有效的去毒化策略。
- **背景**：现有方法分为训练时（如RLHF、DPO）和测试时两类。测试时方法通过在推理阶段干预模型表示（representation editing）实现去毒化，具有灵活、侵入性小的优点，但现有方法因未能充分探索毒性与非毒性输出之间的转换空间而导致干预不精确。
- **整体贡献**：本文提出自回归奖励引导的表示编辑（ARGRE）框架，显式建模表示空间中的毒性转换轨迹，从而提供稳定、精确的编辑指导，在8个LLM上实现有效且高效的去毒化。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：基于线性表示假说，毒性等概念在LLM表示中编码为线性方向。通过探索毒性与非毒性表示之间的连续转换，将稀疏的毒性标注转换为密集的训练信号，用于学习一个自回归奖励模型，并在推理时通过两步编辑引导表示向非毒性区域移动。
- **关键技术细节**：
  1. **毒性转换探索**：对每个提示-响应对，计算非毒性方向（最后一层表示的非毒性与毒性表示之差），并用PCA提取第一主成分作为通用非毒性方向。沿该方向在token级别线性插值，生成多条过渡轨迹。插值点形成密集的表示级配对数据集\( \mathcal{D}_h \)。
  2. **自回归奖励模型**：使用一个两层MLP，输入每个token的表示，输出标量奖励。训练目标类似于传统奖励模型，但基于表示级配对，最大化非毒性与毒性响应累积奖励之差（带缩放因子\( \beta_r \)）。
  3. **自适应两步编辑**：
     - **方向引导**：若当前token表示奖励低于平均非毒性奖励，则向其方向移动，移动量正比于奖励差与\( 1/\beta \)。
     - **梯度优化**：对少量迭代（默认5步）执行梯度上升以进一步最大化奖励。
- **公式**：主要公式包括线性插值式（5）、奖励模型损失（7）、生成分布（8）、方向引导更新式（9）、梯度更新式（10）。每一步均有明确数学表达。

### 3. 实验设计
- **数据集**：
  - 毒性标注：采用Lee et al. (2024)的成对毒性数据集（Wikitext-2非毒性序列 + PPLM生成的毒性序列）。
  - 毒性评估：RealToxicityPrompts挑战子集（1199个高毒性提示），使用Detoxify评分。
  - 能力评估：WikiText-2开发集困惑度（PPL_w），以及7个零样本任务（BoolQ、RTE、HellaSwag、WinoGrande、ARC Easy/Challenge、OpenbookQA）的平均准确率（ACC）。
- **场景**：8个LLM：GPT-2 Medium (355M)、OPT (6.7B)、Mistral (7B)、Mistral-SFT (7B)、LLaMA-7B、LLaMA-7B-SFT、LLaMA-13B、LLaMA-30B。额外评估了指令微调模型（Mistral-7B-Instruct、LLaMA-2-Chat 7B）以及刻板印象识别和越狱缓解任务。
- **对比方法**：
  - 测试时：ProFS（权重编辑）、Re-Control（表示编辑）、RAD和GenARM（引导解码）。
  - 训练时：DPO（仅LLaMA-7B）。
  - 简单基线：banned（过滤禁用词）。
- **公平性**：所有方法使用相同数量的毒性标注（2000对），重复3次报告均值和标准差，超参数搜索后采用最佳设置。

### 4. 资源与算力
- 论文明确说明：“Experiments are conducted on a server with Intel(R) Xeon(R) Gold 6336Y CPU @ 2.40GHz, 512GB system memory, and six NVIDIA A100 GPUs with 40GB memory.”
- 训练细节：自回归奖励模型训练3个epoch，学习率5e-4；GenARM的LoRA训练3个epoch；DPO采用早停。未给出单个实验的具体GPU时长，但提供了推理效率对比（表2）：LLaMA-30B上生成128 tokens，原模型8.14s，ARGRE w/ iter 9.30s，Re-Control 58.69s，GenARM 18.94s。

### 5. 实验数量与充分性
- **实验组数**：共进行约10组主要实验，包括：
  - 主表（表1）：8个LLM × 7种方法（含变体），共56个毒性评估结果。
  - 效率对比（表2）：LLaMA-30B上的推理时间。
  - 能力评估（表3）：8个LLM × 5种方法，共40个（含PPL_w和ACC）。
  - 消融实验（图3/4/5、表4）：标注数量、过渡轨迹数、步长、PCA方向影响。
  - 中间点毒性分析（文字描述）。
  - 指令微调模型（表5）、跨模型泛化（表6）、刻板印象（表7上）、越狱缓解（表7下）。
  - 附录中额外对比Self-Detoxify和DeStein（表12）及完整任务精度（表13-19）。
- **充分性**：实验覆盖了多个模型尺度、多种基线、多个消融维度，并报告标准差，对比公平。但跨模型泛化实验仅限7B同系列，未验证不同规模或架构。刻板印象和越狱任务仅用单一模型（Mistral 7B），覆盖度有限。

### 6. 主要结论与发现
- ARGRE在8个LLM上平均毒性降低62.21%，显著优于GenARM（42.98%）、RAD（35.95%）、ProFS（27.88%）、Re-Control（25.53%）。
- ARGRE在保持生成流畅性方面最优，毒性降低同时PPL_g增加最少（5.67，优于其他基线）。
- 推理效率高：与最快方法ProFS相当（8.20~9.30s vs 8.18s），且大幅快于Re-Control（58.69s）和GenARM（18.94s）。
- 对模型能力影响极小：PPL_w平均增加0.52，ACC平均上升0.06%。
- 数据高效：仅用100个标注即可超越多数基线用2000个标注的性能。
- 过渡轨迹数量N_in=7时接近饱和，进一步增加收益递减。
- 方法可推广到指令微调模型，并在刻板印象识别和越狱缓解任务上取得最优。

### 7. 优点
- **方法创新**：首次显式建模毒性转换轨迹，将稀疏标注转化为密集信号，提升奖励模型指导的精度。
- **两步编辑策略**：方向引导快速到达非毒性区域，少量梯度迭代进一步优化，兼具效果与效率。
- **数据效率高**：极少量标注即可取得显著效果，实用性强。
- **通用性验证**：在去毒化外还展示了刻板印象识别和越狱缓解能力，说明方法可泛化到更多安全任务。
- **实验设计严谨**：采用多个模型、多次运行、标准协议，并与多个强基线公平对比。

### 8. 不足与局限
- **白盒限制**：需要访问LLM内部表示，对仅提供API的黑盒模型不适用（论文已承认）。
- **过渡方向单一**：当前仅使用第一主成分方向，论文指出未来可探索更多样化的方向以更好捕捉毒性微妙变化。
- **跨模型泛化有限**：奖励模型在不同架构家族间迁移效果显著下降（如Mistral ↔ LLaMA），需针对新模型重新训练或研究对齐表示空间。
- **安全任务评估覆盖不足**：刻板印象和越狱缓解仅在一个模型（Mistral 7B）上测试，且训练标注数量少（128对），结论的稳健性有待加强。
- **未讨论对抗攻击场景**：方法假设正常推理过程，未考虑恶意攻击者故意操控表示或绕过编辑的可能性。

（完）
