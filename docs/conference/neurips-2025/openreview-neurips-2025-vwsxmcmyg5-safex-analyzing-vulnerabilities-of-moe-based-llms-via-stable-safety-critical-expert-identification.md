---
title: "SAFEx: Analyzing Vulnerabilities of MoE-Based LLMs via Stable Safety-critical Expert Identification"
title_zh: SAFEx：通过稳定安全关键专家识别分析MoE大模型的漏洞
authors: "ZhengLin Lai, Mengyao Liao, Bingzhe Wu, Dong Xu, Zebin Zhao, Zhihang Yuan, Chao Fan, Jianqiang Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=VwsXmcMyg5"
tags: ["query:model-edit"]
score: 7.0
evidence: 分析MoE模型安全漏洞并识别安全关键专家
tldr: 混合专家（MoE）模型的路由机制引入独特安全风险，现有密集模型安全技术难以适用。本文提出SAFEx框架，通过稳定专家选择过程鲁棒识别安全关键专家，并将其分解为有害内容检测组和功能组。实验验证了专家位置漏洞的存在，为MoE模型的安全编辑提供了分析基础和方法工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1389, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1457, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1409, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1405, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1254, \"height\": 735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 967, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vwsxmcmyg5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1456, \"height\": 945, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwsxmcmyg5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwsxmcmyg5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1370, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwsxmcmyg5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1518, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vwsxmcmyg5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1427, \"height\": 152, \"label\": \"Table\"}]"
motivation: MoE模型的路由机制带来安全对齐挑战，需系统分析其位置漏洞。
method: 提出稳定性专家选择流程，鲁棒识别安全关键专家并分解为功能组。
result: 成功验证MoE模型中存在位置漏洞，并识别出有害内容检测相关专家。
conclusion: SAFEx为MoE模型的安全评估与编辑提供了重要分析框架。
---

## Abstract
Large language models with Mixture-of-Experts (MoE) architectures achieve efficiency and scalability, yet their routing mechanisms introduce safety alignment challenges insufficiently addressed by techniques developed for dense models. In this work, the MoE-specific safety risk of positional vulnerability—that safety-aligned behaviors rely on specific expert modules—is formalized and systematically analyzed. An analytical framework, SAFEx, is presented to robustly identify, characterize, and validate safety-critical experts via a stability-based expert selection procedure, and to decompose them into two functional groups: the Harmful Content Detection Group (HCDG), which specializes in identifying and recognizing harmful content within user inputs, and the Harmful Response Control Group (HRCG), which specializes in controlling and enforcing model behaviors to generate appropriate safety responses. Expert-level interventions are conducted to probe causality and to test mitigation. Targeted masking of SAFEx-selected experts reveals that safety behavior is highly concentrated. On Qwen3-30B-A3B, configured with 48 MoE-FFN layers and 128 experts per layer under top-8 routing (48×128=6,144 experts in total), disabling 12 selected experts reduces the refusal rate by 22%. In addition, lightweight adaptation is performed using LoRA under three configurations—the HRCG, the union of HCDG and HRCG, and all experts—and the resulting updates are composed through negative weight merging targeted at the HRCG, leading to improved refusal under adversarial prompts without full-model retraining. These results establish positional vulnerability as a distinct MoE-specific safety challenge and provide a practical, compute-efficient pathway for expert-level safety interventions within routed architectures.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：混合专家（Mixture-of-Experts, MoE）架构的大型语言模型在安全对齐方面存在独特的“位置漏洞”（positional vulnerability），即模型的安全行为高度依赖于少数特定的专家模块。这种漏洞与密集模型的安全机制不同，现有针对密集模型的安全技术无法直接适用。
- **研究动机**：MoE模型通过路由机制将输入分配给部分专家，提高了效率和可扩展性，但同时也引入了新的安全风险——攻击者可以利用这种路由依赖性绕过安全机制。现有研究主要关注如何发起攻击（如BadMoE利用休眠专家），但缺乏对安全行为内部机制的系统理解。
- **整体含义**：本文首次正式定义并系统分析了MoE模型的位置漏洞，并提出SAFEx框架来识别、分解和验证安全关键专家，为MoE模型的安全对齐和防御提供了理论和实践基础。

## 2. 方法论

### 2.1 核心思想
SAFEx通过统计方法鲁棒地识别与安全行为高度相关的专家，并将它们分解为两个功能组：
- **有害内容检测组（HCDG/ε_id）**：专门负责识别和检测用户输入中的有害内容。
- **有害响应控制组（HRCG/ε_ctrl）**：专门负责控制模型生成适当的安全拒绝回应。

### 2.2 关键技术细节
#### 步骤一：专家统计（Expert Statistics）
- **激活概率建模**：对每个专家e，计算其在给定提示分布X下的条件激活概率 \( p_l(e|X) \)，通过经验频率估计（跨所有token和样本的平均激活次数）。
- **稳定性专家选择（SES）**：借鉴稳定性选择（Stability Selection）思想，通过多次独立抽样（bootstrap）子集，估计每个子集中的top-Ne专家，然后取所有子集top-Ne的交集，得到“稳定”的安全关键专家集合Etop。这减少了样本波动的影响。

#### 步骤二：专家识别（Expert Identification）
- 基于集合运算进行功能分类：
  - **HCDG (ε_id)** = Etop(D_regular) ∩ Etop(D_jailbreak)  （在正常有害和越狱提示下均高频激活的专家）
  - **HRCG (ε_ctrl)** = Etop(D_regular) - Etop(D_jailbreak)  （仅在正常有害提示下高频激活，但在越狱提示下消失的专家）

#### 步骤三：专家验证（Expert Validation）
- **线性探针（Linear Probing）**：对ε_id中的每个专家，用其FFN输出的平均表示训练一个二分类逻辑回归模型，判断输入是否有害。对比随机专家性能，验证该专家确实编码了有害内容检测能力。
- **专家遮蔽（Expert Masking）**：在推理时对ε_ctrl中的专家设置logit为-∞，等效于禁用它们。观察模型拒绝率的变化，以验证这些专家对安全回应的控制作用。

### 2.3 算法流程
1. 构建三个数据集：D_regular（原始有害提示）、D_jailbreak（经越狱改写的有害提示）、D_benign（良性提示）。
2. 对每个数据集，使用SES算法得到稳定的专家激活概率分布，提取top-Ne集合。
3. 通过集合运算分离出ε_id和ε_ctrl。
4. 分别用线性探针和专家遮蔽实验验证两组专家的功能。

## 3. 实验设计

### 3.1 数据集与场景
- **Regular组**：500个有害提示，均匀采样自多种有害类别（欺诈、健康咨询、非法活动等），来源包括openai-moderation-api-evaluation、Aegis-AI-Content-Safety-Dataset-2.0、HarmBench、SimpleSafetyTests、wildguardtest。
- **Jailbreak组**：基于Regular组使用三种越狱策略（语义改写、对抗扰动、上下文重构）生成，由外部模型DeepSeek-V3/R1在黑箱设置下生成。
- **Benign组**：500个无害提示，来自openai-moderation-api-evaluation和wildguardtest。

### 3.2 Benchmark与对比方法
- **测试模型**：
  - Mixtral-8x7B-Instruct-v0.1
  - deepseek-moe-16b-chat
  - Qwen3-30B-A3B（主要结果模型）
  - Qwen1.5-MoE-A2.7B-Chat
  - OLMoE-1B-7B-0924-Instruct（附录）
  - Qwen2-57B-A14B-Instruct（附录）
- **对比基线**：
  - 随机专家（E_random）：随机选择附近位置的5个专家进行线性探针对比。
  - 不使用SES的专家选择消融实验。
  - 密集模型（Qwen3-32B-Instruct, Qwen1.5-32B-Chat, Mistral-7B-v0.1）作为对照比较越狱攻击影响。

### 3.3 核心实验
1. **激活概率可视化**：展示三个数据集下各模型top专家的激活概率分布，观察专家位置偏移。
2. **线性探针实验**：对ε_id中每个专家训练线性分类器，报告Accuracy、Precision、Recall、F1-score，与随机专家组对比。
3. **专家遮蔽实验**：遮蔽ε_ctrl后测量拒绝率下降程度，并报告|Ectrl|大小。
4. **越狱攻击对比**：比较MoE模型与密集模型在越狱攻击下的拒绝率损失。
5. **专家级权重合并（Expert-Level Weight Merging）**：使用LoRA分别对ε_ctrl、ε_id∪ε_ctrl、全部专家进行微调，然后通过负权重合并或正权重合并来增强安全拒绝率。评估在DJailbreak上的拒绝率变化。

## 4. 资源与算力

- **GPU型号与数量**：4块NVIDIA H20 GPU（96GB显存/块）。
- **存储**：512GB用于模型和数据。
- **训练时长**：论文未具体报告每次实验的运行时间或总训练时长。提到“由于几次失败实验，实际计算消耗超过报告量”，但未给出量化细节。

## 5. 实验数量与充分性

### 5.1 实验数量
- 涵盖了4种主流MoE模型（加上附录共6种），包含不同规模（2.7B~30B激活参数）。
- 3个主要数据集组，每个500样本，共1500条提示。
- 消融实验：对比有/无SES的专家选择（附录表4），验证SES的必要性。
- 专家遮蔽实验：在每个模型上报告了遮蔽前后的拒绝率，并对比密集模型。
- 线性探针实验：对ε_id中每个专家单独训练，并对比随机专家（多个随机种子或不同位置）。
- 权重合并实验：在2个MoE模型上测试了3种专家配置×2种合并策略，共12组实验。

### 5.2 充分性与客观性
- **充分性**：实验覆盖了激活分析、功能验证（线性探针+遮蔽）、增强防御（权重合并）三个层面，形成了完整的因果链条。消融实验证明了SES的必要性。跨模型验证增强了结论的泛化性。
- **公平性**：线性探针对比采用随机专家作为基线，控制变量（相同训练配置）。专家遮蔽实验提供了具体|Ectrl|数量，避免夸大效果。越狱攻击对比中，密集模型使用相同的数据集和评估标准。
- **局限**：未在不同提示长度、不同有害类别下分别报告性能差异。拒绝率评估依赖DeepSeek-V3作为规则评判器，可能存在评判偏差。

## 6. 主要结论与发现

1. **位置漏洞普遍存在**：在多个主流MoE模型中，安全行为高度集中于少量专家。例如Qwen3-30B-A3B共有6144个专家，仅遮蔽12个安全控制专家就使拒绝率下降22%（从93.6%降至71.6%）。
2. **功能分离明显**：安全关键专家可分解为HCDG（有害内容检测）和HRCG（有害响应控制）两组，前者通过线性探针验证具备有害内容区分能力，后者通过遮蔽实验验证控制拒绝行为。
3. **越狱攻击加剧漏洞**：MoE模型在越狱攻击下拒绝率下降幅度显著大于密集模型（如Qwen3-30B-A3B下降48.4%，而Qwen3-32B-Instruct仅下降27.8%），表明路由机制使安全更脆弱。
4. **专家级权重合并有效**：仅对HRCG或HCDG+HRCG进行LoRA微调并进行负权重合并，即可大幅提升越狱提示下的拒绝率（从47.7%升至76.5%），无需全模型重训，计算效率高。
5. **专家遮蔽不影响问题解决能力**：在AIME-2024基准上，遮蔽安全控制专家后模型分数变化极小（Qwen3-30B-A3B从77.4→75.2，Qwen1.5-MoE-A2.7B-Chat从12.8→13.2），证明这些专家专门服务于安全而非通用能力。

## 7. 优点

1. **问题新颖性**：首次系统定义并分析了MoE模型的位置漏洞，区别于密集模型的注意力头分析或神经元分析。
2. **方法论严谨**：引入稳定性选择（SES）提高了专家识别的鲁棒性，避免了单次抽样导致的偏差。功能分解（HCDG/HRCG）提供了可解释的因果视角。
3. **实验设计完整**：从激活统计→功能验证→因果干预→防御增强，形成闭环。跨模型验证增加了结论的可信度。
4. **实用性强**：专家级权重合并方法仅需少量LoRA微调即可显著增强安全性，兼容现有部署约束，不需要修改路由或重新训练全模型。
5. **开源贡献**：代码已公开（GitHub链接），便于复现和后续研究。

## 8. 不足与局限

1. **实验覆盖有限**：
   - 仅测试了有限数量的MoE模型（Mixtral, DeepSeek, Qwen系列），未涵盖如Switch Transformer、GLaM等其他架构。
   - 提示数据集规模较小（每组500条），且有害类别分布可能不完全均衡（附录中显示某些类别仅占3%）。
   - 未在不同语言或跨领域任务上验证通用性。
2. **评估偏差风险**：
   - 拒绝率评判完全依赖DeepSeek-V3作为规则评判器，未使用人工评估或多种评判器交叉验证。评判标准可能过于严格或宽松，影响结论可靠性。
   - 线性探针实验仅使用逻辑回归，未尝试其他分类器或更复杂的检测方法，可能低估/高估了专家的检测能力。
3. **应用限制**：
   - 专家识别依赖于SES，需要反复抽样并计算激活频率，计算开销较大，对于更大规模的MoE模型（如DeepSeek-V3有数百层、数万专家）可能难以扩展。
   - 专家合并方法（负/正权重合并）仅尝试了LoRA微调，未与其他专家编辑方法（如直接修改FFN权重、剪枝等）比较。
   - 未研究路由正则化或冗余设计来从根本上缓解位置漏洞。
4. **理论分析不足**：本文主要基于实验观察，缺乏对为什么安全行为会高度集中于少量专家的理论解释（例如路由权重的训练动态、损失景观等）。
5. **泛化性存疑**：虽然跨模型验证一致，但不同模型的|Ectrl|数量差异较大（Qwen3-30B-A3B为12，Mixtral仅2），说明识别结果对模型结构敏感，方法可能需要针对不同架构调优。

（完）
