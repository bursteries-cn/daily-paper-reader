---
title: "AnyEdit: Edit Any Knowledge Encoded in Language Models"
title_zh: AnyEdit：编辑语言模型中编码的任何知识
authors: "Houcheng Jiang, Junfeng Fang, Ningyu Zhang, Mingyang Wan, Guojun Ma, Xiang Wang, Xiangnan He, Tat-Seng Chua"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=aJIoBur0Ef"
tags: ["query:model-edit"]
score: 9.0
evidence: 适用于多种知识格式的自回归编辑范式
tldr: 现有模型编辑方法受限于单Token隐状态编辑，难以处理诗歌、代码等长格式知识。本文提出AnyEdit自回归编辑范式，将长知识分解为连续块并迭代编辑每个块的关键Token，基于互信息的链式法则保证一致性。实验证明该方法能有效更新任意格式知识，突破了编辑方法的效能屏障。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ajiobur0ef/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1761, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajiobur0ef/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajiobur0ef/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajiobur0ef/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajiobur0ef/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1804, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ajiobur0ef/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1076, \"height\": 705, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ajiobur0ef/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 947, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajiobur0ef/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajiobur0ef/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 1720, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajiobur0ef/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1752, \"height\": 2134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajiobur0ef/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1768, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ajiobur0ef/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 1008, \"label\": \"Table\"}]"
motivation: 现有编辑方法在处理长格式知识时因单Token编辑限制而失效。
method: 提出自回归编辑范式，将长知识分解为块并迭代编辑关键Token。
result: 成功编辑诗歌、代码等长格式知识，突破效能屏障。
conclusion: AnyEdit统一了不同知识格式的编辑，提升了模型更新的灵活性和准确性。
---

## Abstract
Large language models (LLMs) often produce incorrect or outdated information, necessitating efficient and precise knowledge updates. Current model editing methods, however, struggle with long-form knowledge in diverse formats, such as poetry, code snippets, and mathematical derivations. These limitations arise from their reliance on editing a single token’s hidden state, a limitation we term as ``efficacy barrier''. To solve this, we propose \textbf{AnyEdit}, a new autoregressive editing paradigm. It decomposes long-form knowledge into sequential chunks and iteratively edits the key token in each chunk, ensuring consistent and accurate outputs. Theoretically, we ground AnyEdit in the Chain Rule of Mutual Information, showing its ability to update any knowledge within LLMs. Empirically, it outperforms strong baselines by 21.5\% on benchmarks including UnKEBench, AKEW, and our new \textbf{EditEverything} dataset for long-form diverse-formatted knowledge. Additionally, AnyEdit serves as a plug-and-play framework, enabling current editing methods to update knowledge with arbitrary length and format, significantly advancing the scope and practicality of LLM knowledge editing. Our code is available at: \url{https://github.com/jianghoucheng/AnyEdit}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- 大语言模型（LLMs）常因知识陈旧或错误而产生幻觉，需要高效且精确的模型编辑。
- 现有方法（如 ROME、MEMIT、AlphaEdit）大多采用“定位-编辑”（locate-then-edit）范式，仅修改**单个 token 的隐状态**，无法有效处理**长格式、多样化格式**的知识（如诗歌、代码、数学推导）。
- 作者将这种局限称为**效能屏障（efficacy barrier）**：单 token 编辑在长知识上概率偏移量过小，且对多样化格式知识的原始概率极低，导致编辑失败。
- 为此，论文提出 **AnyEdit** —— 一种**自回归编辑范式**，突破单 token 限制，实现任意长度和格式知识的精准更新。

### 2. 论文提出的方法论

- **核心思想**：将待更新的长输出 \(Y\) 拆分为多个连续块，**迭代地**编辑每个块的最后一个 token，利用互信息的链式法则保证一致性。
- **关键技术细节**：
  1. **Chunk Outputs**：将 \(Y\) 分成 \(K\) 块（滑动窗口或语义切分）。
  2. **Locate Token and Layer**：定位每个块的最后一个 token，并通过**因果追踪（causal tracing）** 确定影响层。
  3. **Edit Hidden States**：对第 \(k\) 块的隐状态 \(h_k\) 进行梯度下降优化，最大化生成该块的概率：
     \[
     h'_k = h_k + \arg\min_{\hat{\delta}} \left[ -\log P_{f(h_k+\hat{\delta})}(Y_k \mid X, Y_1,\dots,Y_{k-1}) \right]
     \]
  4. **Update Model Parameters**：使用最小二乘优化更新 MLP 层参数，使隐状态对齐编辑后的值。
- **理论支撑**：利用互信息链式法则
  \[
  I(X; Y \mid h'_1,\dots,h'_K) = \sum_{k=1}^K I(X,Y_1,\dots,Y_{k-1};Y_k \mid h'_k)
  \]
  将多 token 干扰解耦为独立单 token 条件，规避了同时编辑多个隐态的相互冲突。

### 3. 实验设计

- **数据集**：
  - **UnKEBench**：1000 条反事实非结构化文本。
  - **AKEW**：包含 Counterfact 和 MQUAKE 子集，评估非结构化知识编辑。
  - **EditEverything**（新建）：涵盖数学（Orca-Math）、代码（MBPP）、化学（Camel-Chemistry）、新闻和诗歌（GPT-4o 生成），最长 458 个 token。
- **对比方法**：FT-L、MEND、ROME、MEMIT、AlphaEdit、UnKE。
- **评估指标**：
  - **语义相似度**：BERT Score。
  - **词法相似度**：ROUGE-L（以及 BLEU、ROUGE-1/2）。
  - 测试场景：原问题、改写问题（评估泛化性）、子问题。
- **基座模型**：Llama3-8B-Instruct、Qwen2.5-7B-Instruct。

### 4. 资源与算力

- 文中明确说明：**所有实验在单张 A100 GPU（80GB）上完成**。
- 未提供具体训练/编辑时长（除平均编辑时间比较外，如表 2 显示每样本约 16–30 秒），也未说明预训练或基线方法的额外算力消耗。

### 5. 实验数量与充分性

- **实验数量充分**：
  - 长知识编辑：表 1（UnKEBench、AKEW 两个子集，两个 LLM，多个指标）。
  - 多样化格式编辑：图 4（5 种知识类型，对比效果与 token 长度关系）。
  - 即插即用提升：图 5（将 AnyEdit 集成到 MEMIT、AlphaEdit、UnKE，观察改进）。
  - 时间开销：表 2（每方法平均编辑时间）。
  - 块大小消融：图 6（讨论 chunk size 对性能的影响）。
- **充分性评估**：
  - 覆盖了基准数据集、新数据集、不同基座 LLM，指标全面。
  - 对比方法涵盖主流编辑方法，公平性较好（复现原论文超参数）。
  - **局限性**：仅使用 7–8B 参数量模型，未在更大模型（如 70B）上验证；因此泛化性结论可能受限于规模。

### 6. 论文的主要结论与发现

- AnyEdit 在长格式、多样化格式知识编辑上全面优于基线，**平均提升 21.5%**（BERT Score 或 ROUGE-L）。
- 当目标 token 数超过 30 时，基线方法（MEMIT、AlphaEdit、UnKE）性能急剧下降，而 AnyEdit 保持稳定。
- AnyEdit 可作为**即插即用框架**，集成后使现有方法大幅提升（图 5），尤其增强了泛化性（改写问题）。
- 理论分析证明了自回归编辑的合理性，打破了单 token 编辑的效能屏障。

### 7. 优点

- **理论扎实**：以互信息链式法则为数学基础，解释并解决了多 token 干扰问题。
- **通用性强**：不受知识格式（事实、代码、数学、诗歌）和长度（可达 458 token）限制。
- **即插即用**：可直接嵌入已有 locate-then-edit 方法，降低迁移成本。
- **实验全面**：新建数据集 EditEverything 填补了多样化格式评估的空白，消融实验和泛化性评估设计严谨。

### 8. 不足与局限

- **持续学习未优化**：论文明确指出 AnyEdit 当前未针对终身编辑场景（连续多轮更新）专门设计。
- **模态单一**：仅支持文本，无法处理多模态（如图像、音频）知识更新。
- **算力开销增加**：集成后编辑时间平均增加约 24.7%（表 2），在实时场景中可能不适用。
- **模型规模有限**：仅在 7–8B 模型上验证，更大 LLM（如 70B、130B）上的性能未知，可能存在扩展性风险。
- **评估偏差风险**：EditEverything 数据集使用 GPT-4o 生成，可能隐含生成模型的风格偏差；同时未与人工评估交叉验证。

（完）
