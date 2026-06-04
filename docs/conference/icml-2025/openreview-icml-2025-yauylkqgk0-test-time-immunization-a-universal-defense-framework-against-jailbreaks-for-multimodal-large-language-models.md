---
title: "Test-Time Immunization: A Universal Defense Framework Against Jailbreaks for (Multimodal) Large Language Models"
title_zh: 测试时免疫：针对（多模态）大语言模型越狱的通用防御框架
authors: "Yongcan Yu, Yanbo Wang, Ran He, Jian Liang"
date: 2025-01-09
pdf: "https://openreview.net/pdf?id=YaUyLKQGk0"
tags: ["query:model-edit"]
score: 4.0
evidence: 提出测试时优化防御框架，与通过编辑防御攻击相关
tldr: 针对现有防御方法仅针对特定越狱攻击的局限性，提出测试时免疫（TIM）框架，通过测试时优化统一防御文本和图像等多模态越狱攻击，实验显示对各种攻击均有效。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yauylkqgk0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 823, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yauylkqgk0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1254, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yauylkqgk0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 700, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yauylkqgk0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yauylkqgk0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1348, \"height\": 528, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yauylkqgk0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yauylkqgk0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1506, \"height\": 562, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yauylkqgk0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yauylkqgk0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 631, \"height\": 198, \"label\": \"Table\"}]"
motivation: 现有防御方法针对不同越狱类型分离，缺乏通用性。
method: 在测试阶段对输入进行对抗性优化，以最小化有害输出概率。
result: 在多种越狱攻击下（包括文本和图像）取得了显著防御效果。
conclusion: TIM提供了一种无需重训练的通用防御方案，对提升LLM安全性有重要价值。
---

## Abstract
While (multimodal) large language models (LLMs) have attracted widespread attention due to their exceptional capabilities, they remain vulnerable to jailbreak attacks. Various defense methods are proposed to defend against jailbreak attacks, however, they are often tailored to specific types of jailbreak attacks, limiting their effectiveness against diverse adversarial strategies. For instance, rephrasing-based defenses are effective against text adversarial jailbreaks but fail to counteract image-based attacks. To overcome these limitations, we propose a universal defense framework, termed Test-time IMmunization (TIM), which facilitates test-time optimization to counteract diverse jailbreak attacks. Specifically, TIM initially trains a gist token for efficient detection, which it subsequently applies to detect jailbreak activities during inference. When jailbreak attempts are identified, TIM implements safety fine-tuning using the detected jailbreak instructions paired with refusal answers. Furthermore, to mitigate potential performance degradation in the detector caused by parameter updates during safety fine-tuning, we decouple the fine-tuning process from the detection module. Extensive experiments on both LLMs and multimodal LLMs demonstrate the efficacy of TIM.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有（多模态）大语言模型（LLM/MLLM）尽管通过安全对齐（如RLHF、安全指令微调）降低了有害生成，但仍易受多种越狱攻击（如文本对抗后缀GCG、图像嵌入攻击Figstep、MM-SafetyBench等）。
- **现有防御局限**：大多数防御方法针对特定攻击类型设计，例如基于困惑度过滤的防御无法应对图像模态攻击，而图像结构防御又忽略文本攻击。攻击类型持续演化，预训练所有防御不现实。
- **本工作动机**：受生物免疫系统启发——首次遇到病原体后识别并产生抗体，从而免疫同类攻击。论文提出**测试时免疫（Test-time Immunization, TIM）**框架，在模型部署过程中主动检测越狱活动，并动态增强模型对该攻击的防御能力，实现通用、自适应的安全防护。

## 2. 方法论

### 核心思想
- 将越狱活动视为数字“病原体”，在测试阶段检测并收集越狱指令，用于立即安全微调，使模型获得对同类型攻击的免疫力。
- 关键洞察：识别越狱行为比直接防御更容易，因此先构建轻量检测器，再通过微调转移检测能力为防御能力。

### 关键技术细节

1. **高效检测器**：
   - 训练一个**gist token** `t_g` 和一个二分类器 `C_d`。在序列末尾插入 `t_g`，利用KV Cache高效计算其隐藏状态，仅需约1/1000的总生成时间。
   - 检测流程：`h_t = E_l(t, t_g)`, `p_t = C_d(h_t)`，判断是否为越狱响应。
   - 构建检测数据集 `D_d`：包含四种组合（恶意指令+恶意回答/拒绝回答、干净指令+干净回答/恶意回答），训练交叉熵损失。

2. **测试时防御训练**：
   - 当检测到越狱活动（`y=1`），将当前指令与预设拒绝回答存入**越狱记忆** `M_j`；同时将当前样本（指令+恶意回答/拒绝回答）存入**检测记忆** `M_d`。
   - 使用 `M_j` 对模型进行LoRA微调（秩16，作用于最后15个Transformer块的Q、V矩阵），并混合正常QA数据集 `D_qa` 正则化，防止过度防御。
   - 同时用 `M_d` 和 `D_d` 训练检测器，实现检测与防御的协同优化。

3. **解耦设计**：
   - 检测使用**中间层**的隐藏状态，防御训练仅更新**中间层之后**的LoRA参数。这样参数更新不影响检测器性能，避免检测器FPR上升和ODR增加。

## 3. 实验设计

### 数据集
- **检测数据集**：恶意指令来自AdvBench、MM-SafetyBench；恶意回答由Wizard-Vicuna-7B-Uncensored生成；拒绝回答由LLaMA2-13B-chat生成；干净指令来自GPT4-LLM-Cleaned（文本）和LLaVA-Instruct-150K（多模态）；干净回答由对应安全模型生成。
- **评估数据集**：模拟部署环境，将正常指令与越狱指令混合（1:1比例），越狱指令分别使用Figstep、MM-SafetyBench、I-FSJ等生成。

### 基准方法
- **MLLM**：FSD（系统提示）、Adashield-S（防御提示）、VLGuard（训练时安全微调）、TIM-NG（无gist token变体）、TIM-NA（无测试时适应）/TIM-NG-NA。
- **LLM**：Self Defense（代理LLM检测）、LVLM-LP（基于首token分布检测）。

### 评估指标
- **攻击成功率（ASR）**：越狱指令未被拒绝的比例；ASR-50：测试序列后半部分的ASR。
- **过度防御率（ODR）**：正常指令被拒绝的比例。
- **检测器性能**：准确率、TPR、FPR。

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量或训练时长。仅提及LoRA秩16、学习率、批次大小等超参数，但未见具体硬件环境描述。可能因为投稿要求匿名或初步工作阶段未提供。

## 5. 实验数量与充分性

- **实验组数**：涵盖三种主攻击（Figstep、MM-SafetyBench、I-FSJ），两种MLLM骨干（LLaVA-v1.6-Vicuna-7B、LLaVA-v1.6-Mistral-7B）和一种LLM骨干（LLaMA2-7B-chat）。除主结果表外，还包含：
  - 混合攻击（300 Figstep + 300 MM-SafetyBench）
  - 不同越狱数据比例消融（1:0.5 ~ 1:9）
  - 检测器性能对比（TIM-NA vs TIM-NG-NA等）
  - 持续变化攻击顺序实验（附录B）
- **消融实验**：验证gist token效果（TIM vs TIM-NG）、解耦效果（TIM vs TIM-NG）、测试时适应效果（TIM vs TIM-NA）。
- **公平性**：与已有方法在相同骨干、相同攻击设置下比较，指标定义一致。但未在更多模型（如LLaMA3、GPT-4）上验证，通用性仍需扩展。

## 6. 主要结论与发现

- **防御有效性**：TIM在Figstep、MM-SafetyBench上ASR降至2%以下，ASR-50均达到0%；在I-FSJ上ASR降至2.6%，ASR-50为0%，且ODR低于对比方法（VLGuard等）。
- **检测器优势**：gist token显著提升检测准确率（TIM-NA vs TIM-NG-NA：99.1% vs 88.5%），解耦后FPR从0.7%降至0.1%（LLM实验）。
- **鲁棒性**：在混合攻击和不同比例越狱数据下，ASR和ODR均保持稳定，无灾难性遗忘（附录B）。
- **效率**：检测开销极低，接近1/1000生成时间。

## 7. 优点

- **通用性**：不依赖于特定攻击的先验知识，能同时防御文本和图像模态越狱。
- **自适应**：测试时动态优化，可针对新出现的攻击类型快速适应。
- **轻量高效**：训练小型检测器+LoRA，推理时检测成本极低。
- **解耦设计**：避免防御微调反噬检测性能，同时保持检测能力稳定。
- **低副作用**：对正常指令响应影响小（ODR最低仅0.0%）。

## 8. 不足与局限

- **模型覆盖有限**：仅测试了LLaVA家族和LLaMA2-7B，未在更大模型（如LLaMA3-70B、GPT-4V）或更复杂架构上验证。
- **攻击类型覆盖**：主要评估了结构型（Figstep、MM-SafetyBench）和上下文学习型（I-FSJ），但未涉及对抗性后缀（GCG）、多轮对话越狱、有界遗忘等更复杂攻击。
- **检测数据依赖**：需要预训练检测器，可能对未见过的攻击风格（如完全自创的提示）泛化能力有限；恶意回答生成依赖未安全对齐模型，存在偏差风险。
- **算力消耗未报告**：未提供训练时长、GPU型号数量，难以评估实际部署成本。
- **潜在安全风险**：检测数据集包含恶意内容，若泄露可能带来社会危害。

（完）
