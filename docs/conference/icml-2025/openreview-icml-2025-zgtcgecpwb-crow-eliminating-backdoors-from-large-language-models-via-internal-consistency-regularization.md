---
title: "CROW: Eliminating Backdoors from Large Language Models via Internal Consistency Regularization"
title_zh: CROW：通过内部一致性正则化消除大型语言模型的后门
authors: "Nay Myat Min, Long H. Pham, Yige Li, Jun Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ZGtcgeCpWB"
tags: ["query:model-edit"]
score: 6.0
evidence: 通过内部正则化消除后门，类似安全模型编辑
tldr: 大型语言模型易受后门攻击，现有防御无法直接用于文本生成。本文提出CROW方法，通过内部一致性正则化，利用后门模型层间表示不稳定、清洁模型平滑的观察，在微调中添加对抗扰动和正则化以消除后门。实验在Llama-2、CodeLlama、Mistral-7B上验证，仅需少量清洁数据即可有效中和后门，无需知道触发器。该方法可视为一种安全导向的模型编辑技术，提升模型安全性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zgtcgecpwb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zgtcgecpwb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zgtcgecpwb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1592, \"height\": 630, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 1599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 1599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1770, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 860, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1720, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1719, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1736, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1210, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zgtcgecpwb/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1776, \"height\": 1836, \"label\": \"Table\"}]"
motivation: 大型语言模型易受后门攻击，现有防御方法无法适用于文本生成任务。
method: 提出内部一致性正则化，利用层间表示的稳定性差异，通过对抗扰动和正则化在微调中消除后门。
result: 在多个主流模型上，仅需少量清洁数据即可有效消除后门，无需触发器知识。
conclusion: CROW是一种高效的后门防御方法，可视为安全模型编辑技术。
---

## Abstract
Large Language Models (LLMs) are vulnerable to backdoor attacks that manipulate outputs via hidden triggers. Existing defense methods—designed for vision/text classification tasks—fail for text generation. We propose *Internal Consistency Regularization (CROW)*, a defense leveraging the observation that backdoored models exhibit unstable layer-wise hidden representations when triggered, while clean models show smooth transitions. CROW enforces consistency across layers via adversarial perturbations and regularization during finetuning, neutralizing backdoors without requiring clean reference models or trigger knowledge—only a small clean dataset. Experiments across Llama-2 (7B, 13B), CodeLlama (7B, 13B), and Mistral-7B demonstrate CROW’s effectiveness: it achieves significant reductions in attack success rates across diverse backdoor strategies (sentiment steering, targeted refusal, code injection) while preserving generative performance. CROW’s architecture-agnostic design enables practical deployment.

---

## 论文详细总结（自动生成）

# CROW: Eliminating Backdoors from Large Language Models via Internal Consistency Regularization —— 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLMs）在文本生成任务中易受后门攻击（Backdoor Attacks）——攻击者通过数据投毒或提示工程植入隐藏触发器，使模型在推理时输出恶意内容（如毒性文本、拒绝服务、代码注入）。现有后门防御方法主要针对视觉/文本分类任务设计，无法直接适用于生成式LLMs，且往往需要干净的参考模型或已知触发器模式，限制了实用性。
- **核心挑战**：
  - 生成式LLMs的输出空间复杂、上下文敏感，传统分类任务上的防御（如剪枝、量化、标准微调）无法彻底消除后门，甚至可能加剧攻击成功。
  - 防御方通常无法获得完整训练集、参考模型或触发器知识，仅能访问少量干净数据。
- **整体含义**：提出一种轻量级、无需触发器知识、无需参考模型的后门防御方法，兼顾安全性与生成质量，具有实际部署价值。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想

- **关键观察**：在干净的Transformer模型中，连续层的隐藏状态表示保持平滑一致（层间余弦相似度高）；而在被植入后门的模型中，当输入包含触发器时，早期到中间层的隐藏状态会出现突变的、不稳定的偏差（参见图1）。此现象表明后门触发器破坏了层间一致性。
- **防御思路**：通过在微调过程中引入**对抗性扰动**和**正则化**，强制模型保持层间隐藏状态的连续性，从而中和后门触发器产生的异常表征，无需知道触发器的具体形式。

### 2.2 关键技术细节

- **一致性损失定义**：对于第 l 层和 token t，定义层间一致性损失为  
  \( L^{(l)}_{cons} = \frac{1}{T} \sum_{t=1}^{T} \left(1 - \cos(H^{(l)}_t, H^{(l-1)}_t)\right) \)  
  总体一致性损失为所有层的平均值：\( L_{cons} = \frac{1}{N-1} \sum_{l=2}^{N} L^{(l)}_{cons} \)。

- **对抗扰动生成**：基于Fast Gradient Sign Method (FGSM) 在输入嵌入上生成小扰动（扰动幅度 ε），模拟后门触发器引起的表征偏移：  
  \( G = \nabla_{H^{(0)}} L_{cons} \)， \( H^{(0)}_{adv} = H^{(0)} + \epsilon \cdot \text{sign}(G) \)。

- **对抗一致性训练**：用扰动后的嵌入进行前向传播，计算对抗性一致性损失 \( L^{adv}_{cons} \)，与标准语言建模损失 \( L_{LM} \) 结合：  
  \( L_{total} = L_{LM} + \alpha \cdot L^{adv}_{cons} \)，其中 α 平衡主任务与正则化强度。

- **算法流程**（Algorithm 1）：
  1. 从干净数据集抽取小批量；
  2. 计算初始嵌入和原始一致性损失；
  3. 计算梯度生成对抗嵌入；
  4. 用对抗嵌入前向传播得到对抗隐藏状态，计算 \( L^{adv}_{cons} \)；
  5. 联合优化总损失更新模型参数。

- **理论依据**：通过约束每层变换的Lipschitz常数接近1（近等距变换），限制触发器扰动的指数级放大，从而保证深层表征稳定。

## 3. 实验设计：数据集/场景、benchmark、对比方法

### 3.1 数据集与场景

- **训练/微调数据**：Stanford Alpaca（52k条指令）用于训练和微调；HumanEval（164个Python任务）用于代码生成评估。
- **攻击场景**：6种数据投毒攻击：BadNets、VPI（虚拟提示注入）、Sleeper、MTBA（多触发器）、CTBA（复合触发器）、BadNets-CI（代码注入）。攻击植入仅500条指令（<1%），模拟低投毒比例。
- **任务类型**：
  - 情感转向（Sentiment Steering）：使输出带有偏见或毒害内容。
  - 定向拒绝（Targeted Refusal）：使模型拒绝包含触发器的正常查询。
  - 代码注入（Code Injection）：生成恶意代码片段（如 `print("pwned")`）。
- **额外实验**：在语义后门攻击（实体触发器如“Joe Biden”）和越狱攻击（GCG）上评测CROW的泛化能力。

### 3.2 Benchmark

- **攻击成功率 (ASR)**：测量含有触发器的输入触发目标行为的比例。
- **帮助性 (Helpfulness)**：使用GPT-4o-mini对MT-Bench第一轮回答进行0-10打分。
- **代码注入场景**：同时使用HumanEval的功能正确性评估（但表中主要报告ASR和MT-Bench）。

### 3.3 对比方法

- **标准微调 (Finetuning)**：仅用100条干净数据微调。
- **剪枝 (Pruning)**：基于权重大小的幅度剪枝（LLaMA 0.35稀疏度，Mistral 0.65）。
- **量化 (Quantization)**：INT4量化。
- **消融对比**：无对抗扰动的纯一致性正则化（Pure Consistency）、仅嵌入层的正则化、KL散度替代余弦相似度等。

## 4. 资源与算力

- **硬件**：单块A100-PCIE-40GB GPU。
- **训练时长**：每个CROW微调运行时间不到4分钟（LLaMA-2-7B: 2.20 min; 13B: 3.35 min; Mistral-7B: 2.39 min; CodeLlama-7B: 2.24 min; 13B: 3.78 min）。
- **数据量**：仅需100条干净样本（来自Alpaca），每个模型训练5个epoch，使用LoRA（秩适配）、混合精度（FP16）。
- **效率**：轻量级，适合实际部署。

## 5. 实验数量与充分性

- **实验数量**：覆盖5个模型（LLaMA-2-7B/13B, CodeLlama-7B/13B, Mistral-7B）、6种攻击、3种任务，主表（Table 1–4）报告了ASR和MT-Bench分数；消融实验（Table 5–7）研究了扰动幅度 ε、权重 α、相似度指标（余弦 vs. KL散度）；还进行了越狱攻击（Table 8）、语义后门（Table 12）、嵌入层对比（Table 11）等补充实验。
- **充分性**：实验设计较为全面，覆盖了主流LLM架构、多样化后门攻击、多任务场景，且对比了多种基线防御。消融实验验证了关键超参数和设计选择。但存在不足：未在更大模型（如70B）或更多语种上进行评估；未测试自适应攻击（如攻击者知晓CROW后尝试绕过）。
- **客观性与公平性**：ASR和MT-Bench指标定义明确，基线方法使用了相同的100条干净数据（微调、剪枝、量化）以进行公平比较。额外与CleanGen（推理时防御）对比（Table 9），证实CROW在定向拒绝任务上更稳定。但未与更多最新防御（如NAD、Fine-mixing等）进行直接比较（仅在Related Work中提及）。

## 6. 论文的主要结论与发现

- **CROW显著降低后门攻击成功率**：在所有模型和攻击类型上，ASR降至5%以下（大部分接近0%~2%），优于剪枝、量化和标准微调。
- **保持生成性能**：MT-Bench分数接近或优于未防御模型（例如LLaMA-2-7B情感转向任务从2.72提升至3.80），而基线防御常导致分数下降。
- **对代码注入同样有效**：CodeLlama-7B/13B上ASR降至0.87%/2.99%，同时保留代码生成能力。
- **轻量高效**：单GPU、数分钟、100条干净样本即可完成防御，适合实际部署。
- **可扩展至越狱攻击**：CROW在GCG越狱攻击上使ASR从63%降至29%（α=11），展现一定泛化防御能力。

## 7. 优点

- **无需触发器知识或干净参考模型**：仅需少量干净数据，实际部署友好。
- **任务无关性与架构无关性**：适用于情感转向、拒绝、代码注入等多种任务，且可推广到不同LLM架构（LLaMA、CodeLlama、Mistral）。
- **理论支撑**：从Lipschitz约束角度解释了为何一致性正则化能抑制后门传播。
- **计算开销极低**：微调时间短，不增加推理成本（对比CleanGen需要额外参考模型和推理调用）。
- **可解释性**：通过层间余弦相似度可视化展示了后门导致的表征偏差，验证了方法的直观合理性。

## 8. 不足与局限

- **超参数敏感性**：权重因子 α 需要针对任务调整（情感转向/代码注入使用α=5.5，定向拒绝使用α=11），不够自适应。
- **未评估自适应攻击**：如果攻击者知道CROW的防御机制，可能设计能够规避层一致性正则化的后门（如降低触发器造成的表征突变），论文未测试此类稳健性。
- **模型规模范围**：实验限于7B-13B参数，未验证更大模型（如LLaMA-70B）上CROW的有效性和效率。
- **越狱防御效果有限**：在GCG攻击上仅将ASR从63%降至29%（α=11），仍有较高风险，并非完全的越狱防御方案。
- **应用局限**：主要针对数据投毒后门，对模型替换、权重窃取等其他攻击形式未涉及。
- **实验种类**：未与传统防御如NAD（需要参考模型）、ANP等进行直接比较，也未在更多自然语言任务（如翻译、摘要）上验证。

（完）
