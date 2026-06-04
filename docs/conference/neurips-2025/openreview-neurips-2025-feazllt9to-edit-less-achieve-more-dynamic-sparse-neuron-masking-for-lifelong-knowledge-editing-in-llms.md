---
title: "Edit Less, Achieve More: Dynamic Sparse Neuron Masking for Lifelong Knowledge Editing in LLMs"
title_zh: 少编辑，多收益：面向大语言模型终身知识编辑的动态稀疏神经元掩码
authors: "Jinzhe Liu, Junshu Sun, Shufan Shen, Chenxue Yang, Shuhui Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=feAzLLT9to"
tags: ["query:model-edit"]
score: 9.0
evidence: 大语言模型知识编辑
tldr: 现有终身知识编辑方法在连续编辑中误差累积，导致准确性和泛化能力下降。为此，本文提出神经元特定掩码知识编辑（NMKE），通过神经元功能归因识别知识神经元，并采用动态稀疏掩码进行细粒度编辑。实验证明，NMKE有效减少误差累积，在多个数据集上优于现有方法。该工作为LLM提供了一种高效、可持续的知识更新方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1381, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1392, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1380, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1459, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1395, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1386, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1362, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 713, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feazllt9to/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 713, \"height\": 479, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1095, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1095, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 936, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1159, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1164, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1021, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1302, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 906, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feazllt9to/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1498, \"height\": 372, \"label\": \"Table\"}]"
motivation: 现有终身知识编辑方法在连续编辑中误差累积，导致性能下降。
method: 提出NMKE框架，利用神经元功能归因识别知识特异性神经元和知识通用神经元，并采用动态稀疏掩码进行精确编辑。
result: 实验表明NMKE在编辑准确性和泛化能力上优于现有方法，显著减少误差累积。
conclusion: NMKE为LLM提供了一种高效、可持续的知识更新方法。
---

## Abstract
Lifelong knowledge editing enables continuous, precise updates to outdated knowledge in large language models (LLMs) without computationally expensive full retraining. However, existing methods often accumulate errors throughout the editing process, causing a gradual decline in both editing accuracy and generalization.  To tackle this problem, we propose Neuron-Specific Masked Knowledge Editing (NMKE), a novel fine-grained editing framework that combines neuron-level attribution with dynamic sparse masking. 
Leveraging neuron functional attribution, we identify two key types of knowledge neurons, with knowledge-general neurons activating consistently across prompts and knowledge-specific neurons activating to specific prompts.
NMKE further introduces an entropy-guided dynamic sparse mask, locating relevant neurons to the target knowledge. This strategy enables precise neuron-level knowledge editing with fewer parameter modifications.
Experimental results from thousands of sequential edits demonstrate that NMKE outperforms existing methods in maintaining high editing success rates and preserving model general capabilities in lifelong editing.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有终身知识编辑方法（包括外部参数方法和内部参数方法）在连续编辑过程中误差累积，导致编辑准确性和模型泛化能力逐步下降。尤其是内部编辑方法虽然架构简洁，但往往在层或参数块级别进行修改，意外破坏了与目标知识无关的神经元，导致模型遗忘和能力崩溃。
- **研究动机**：LLM 需要持续、精确地更新过时知识，而无需昂贵的全量重新训练。理想的终身编辑方法必须同时保持高编辑准确性和模型通用能力。
- **整体含义**：该论文旨在设计一种细粒度、低干扰的编辑框架，能够精准定位并仅修改与目标知识最相关的神经元，从而在数千次连续编辑后仍保持模型稳定和性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：提出 Neuron-Specific Masked Knowledge Editing (NMKE)，结合**神经元级归因**与**动态稀疏掩码**，实现精确、最小干扰的知识更新。
- **关键技术细节**：
  - **神经元归因**：使用基于 log 概率变化的静态归因方法，计算每个神经元对目标预测的贡献度（公式 2-3）。通过分析归因得分，将神经元分为两类：
    - **知识通用神经元**：跨提示稳定激活，编码通用知识。
    - **知识特异性神经元**：对特定提示选择性激活，编码具体知识。
  - **动态稀疏掩码**：
    - 对每个神经元的归因得分分布计算熵，动态确定两类神经元的选取比例（公式 6-7）。
    - 基于熵驱动的比例，通过阈值选择最相关的神经元子集，生成二进制稀疏掩码（公式 8），仅允许更新这些被掩码覆盖的神经元。
  - **编辑流程**：在选定层（文中通常为 MLP 层 4-8）内，将掩码应用于参数更新矩阵，限制修改范围。编辑过程遵循 AlphaEdit 的优化管道，但用神经元级掩码替代层级更新。

## 3. 实验设计

- **使用的数据集**：
  - 编辑性能：ZsRE（问答）、CounterFact（事实校正）。
  - 通用能力：MMLU、GSM8K、CommonsenseQA、BBH-Zeroshot、HumanEval。
- **Benchmark 设定**：累计编辑步数 T ∈ {10, 100, 500, 1000, 1500, 2000, 3000, 5000}，批大小为 1，顺序编辑。
- **对比方法**：Fine-Tuning (FT)、KN、ROME、MEMIT、PMET、WISE、AlphaEdit（均为 SOTA 或经典方法）。
- **评估指标**：编辑成功率 (Rel.)、泛化到释义提示 (Gen.)、局部性保持 (Loc.)；通用能力使用各任务准确率。

## 4. 资源与算力

- 文中明确说明：所有实验使用 **8 块 NVIDIA A100 GPU**。
- **未明确说明**每条实验的具体运行时长或总 GPU 小时数，仅给出了每编辑步骤耗时（NMKE 采用 LPS 归因约 30.42 秒，MPC 约 22.25 秒），但未提供完整训练/评估总耗时。

## 5. 实验数量与充分性

- **实验数量**：包含多组关键实验：
  - 主实验：在 LLaMA3-8B-Instruct 上对两个数据集、多个编辑步数进行完整对比（表 1）。
  - 通用能力评估：在 5 个下游任务上跟踪性能变化（图 4）。
  - 消融实验：神经元选择策略（4 种变体）、超参数分析（缩放因子 vs 偏置）、重叠/非重叠神经元分析、软掩码 vs 硬掩码等（图 6、7，表 3、4）。
  - 参数分布可视化：t-SNE、ℓ2 范数分布等（图 5、9、10）。
  - 扩展到其他模型：GPT2-XL 和 Qwen2.5-7B（表 7、8）。
  - 扩展到 5000 编辑步（表 6）、批处理编辑（表 11）。
- **充分性与公平性**：
  - 对比方法覆盖主流内部/外部编辑方法，超参数使用官方配置，评价标准一致。
  - 消融实验设计合理，验证了各组件贡献。
  - 但未报告多次运行的误差条（如标准误），尽管引用已有文献惯例，仍可能影响统计可靠性。

## 6. 论文的主要结论与发现

- NMKE 在数千次顺序编辑后仍能保持高编辑成功率（Rel. > 0.94 在 ZsRE 上 T=2000），而 AlphaEdit 等基线在 T>1500 后性能崩溃（Rel. 降至 0.32）。
- NMKE 在通用能力保持上显著优于所有对比方法：MMLU、GSM8K、HumanEval 等任务下降幅度最小，甚至在 5000 步后 MMLU 仍保持 0.53。
- 神经元级编辑带来的参数分布扰动远小于层级编辑（t-SNE 可视化与 ℓ2 距离定量分析），解释了其稳定性。
- 知识通用神经元和知识特异性神经元的功能区分与动态熵比例选择是保持性能的关键。

## 7. 优点

- **细粒度编辑**：首次在终身编辑场景中系统利用神经元类型区分和动态稀疏掩码，突破传统层/块级修改的限制。
- **理论分析与实验结合**：通过神经元归因实验证明了知识存储的非均匀分布特性，为编辑策略提供了经验基础。
- **适应性熵导向比例**：根据每次编辑提示的归因分布自动调整选取神经元数量，避免固定比例带来的过选或漏选。
- **一致性好**：在不同模型（LLaMA3、GPT2-XL、Qwen2.5）、不同编辑数据集和数千步场景下均表现稳健。
- **效率可控**：提供多种归因实现（MPC、PSA、LPS），可在性能与速度之间权衡。

## 8. 不足与局限

- **归因方法依赖**：性能严重依赖于神经元归因的准确性，当前基于单层 log 概率变化的归因可能忽略跨层交互信息。论文自身也指出未来需考虑层间信息流。
- **编辑依赖未建模**：未处理不同事实编辑之间的依赖关系（如 CEO 更新与 CEO 数量一致性），可能导致逻辑不一致。
- **缺乏统计波动报告**：未给出多次运行的标准差或置信区间，结果稳健性尚需进一步验证。
- **算力报告不完整**：仅提供单步编辑耗时，未给出完整的训练/评估总算力消耗，不利于可重复性比较。
- **模型规模有限**：主要在 7B-8B 规模模型上测试，更大模型（如 70B 以上）的适用性尚未验证。

（完）
