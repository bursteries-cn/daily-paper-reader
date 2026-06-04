---
title: "Panacea: Mitigating Harmful Fine-tuning for Large Language Models via Post-fine-tuning Perturbation"
title_zh: Panacea：通过微调后扰动缓解大语言模型的有害微调
authors: "Yibo Wang, Tiansheng Huang, Li Shen, Huanjin Yao, Haotian Luo, Rui Liu, Naiqiang Tan, Jiaxing Huang, Dacheng Tao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sMtiGB2YZT"
tags: ["query:model-edit"]
score: 8.0
evidence: 通过微调后扰动防御有害微调
tldr: 本文发现简单随机扰动可消除微调后模型的有害行为，但会损失微调性能。为此提出Panacea方法，通过优化自适应扰动，在恢复模型安全性同时保持微调效果。实验证明该方法能有效防御有害微调攻击，且优于现有疫苗防御方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 728, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1298, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 728, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1278, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-smtigb2yzt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1289, \"height\": 535, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1163, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 961, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1223, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1031, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1174, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1171, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 711, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 647, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 717, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 717, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1149, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 955, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 957, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1321, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 875, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1448, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 813, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1444, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 883, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1454, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1012, \"height\": 1118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-smtigb2yzt/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1438, \"height\": 499, \"label\": \"Table\"}]"
motivation: 现有疫苗防御脆弱，几步微调后模型仍能学到有害知识。
method: 先分析随机扰动可恢复安全性，再提出自适应扰动优化方法Panacea。
result: 在多种有害微调攻击下，Panacea有效恢复安全性并保留微调效用。
conclusion: 微调后扰动是一种简单有效的有害微调防御新范式。
---

## Abstract
Harmful fine-tuning attack introduces significant security risks to the fine-tuning services. Main-stream defenses aim to vaccinate the model such that the later harmful fine-tuning attack is less effective. However, our evaluation results show that such defenses are fragile-- with a few fine-tuning steps, the model still can learn the harmful knowledge. To this end, we do further experiment and find that an embarrassingly simple solution-- adding purely random perturbations to the fine-tuned model, can recover the model from harmful behaviors, though it leads to a degradation in the model’s fine-tuning performance. To address the degradation of fine-tuning performance, we further propose \methodname, which optimizes an adaptive perturbation that will be applied to the model after fine-tuning. \methodname maintains model's safety alignment performance without compromising downstream fine-tuning performance. Comprehensive experiments are conducted on different harmful ratios, fine-tuning tasks and mainstream LLMs, where the average harmful scores are reduced by up-to 21.2%, while maintaining fine-tuning performance. As a by-product, we analyze the adaptive perturbation and show that different layers in various LLMs have distinct safety coefficients. Source code available at https://github.com/w-yibo/Panacea.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **问题**：大语言模型（LLM）的“微调即服务”场景存在严重安全风险——即使用户的微调数据中只混入少量有害数据（有害微调攻击），模型也会学会有害知识，导致安全对齐失效。
- **现有防御不足**：主流防御（如Vaccine、RepNoise）通过在“对齐阶段”对模型进行“疫苗接种”，试图提高模型对抗后续有害微调的能力。但实验发现，经过足够多的微调步骤后，这些防御仍会失效——模型依然能学会有害知识。
- **核心发现**：作者发现一种极其简单的方法——在微调完成后，给模型权重添加**纯随机扰动**，可以显著恢复模型的安全性（有害分数下降），但代价是微调性能严重受损。
- **研究目标**：如何在恢复安全性的同时，不显著损失下游微调任务的性能？为此提出 **Panacea**，一种在微调阶段优化**自适应扰动**，在微调结束后将扰动施加到模型上，达到“解毒”效果。

### 2. 方法论

- **核心思想**：在微调阶段，同时优化一个**有界自适应扰动**，使得该扰动施加到模型后能**最大程度增加有害损失**（即强迫模型遗忘有害知识），同时通过约束不破坏微调任务的损失。
- **形式化**：这是一个**max-max优化问题**：
    - 外最大化：最大化 `λ(h(w+ε) – h(w)) – g(w)`，其中 `w` 是模型参数，`ε` 是扰动，`h` 是有害损失，`g` 是微调任务损失，`λ` 是平衡系数。
    - 内最大化：`max_{ε: ||ε||≤ρ} h(w+ε)`，即找到在范数约束 `ρ` 下能最大提升有害损失的扰动 `ε`。
- **求解**：
    - **内问题闭式解**：`ε* = ρ * ∇h(w) / ||∇h(w)||`，即沿有害梯度方向、大小为 `ρ` 的向量。
    - **外问题迭代更新**：`w_{t+1} = w_t + η ( λ(∇h(w_t+ε_t) – ∇h(w_t)) – ∇g(w_t) )`
- **算法流程**：
    1. 从微调数据和有害数据中各采样一个批次。
    2. 计算有害梯度 `∇h(w_t)`，得到扰动 `ε_t`。
    3. 计算施加扰动后的有害梯度 `∇h(w_t+ε_t)`。
    4. 组合梯度更新模型参数 `w_t`。
    5. 微调结束后，将最后一步得到的扰动 `ε_{T-1}` 加到最后模型参数 `w_T` 上，得到最终的安全模型。
- **特点**：属于**微调后阶段**的防御，不依赖微调前的对齐阶段，可直接应用于已经对齐的LLM（如Llama2-7B-Chat）。

### 3. 实验设计

- **数据集**：
    - 对齐数据集：BeaverTails 子集（5000条有害指令-无害响应）。
    - 有害数据集：BeaverTails 子集（1000条有害指令-有害响应）。
    - 微调数据集：4个下游任务（GSM8K、SST2、AlpacaEval、AGNEWS）各取1000/700条，混合一定比例（默认10%）的有害数据（来自BeaverTails，与有害数据集无重叠）。
- **对比方法**：
    - **SFT**（标准对齐+微调）
    - **Vaccine**（对齐阶段防御）
    - **RepNoise**（对齐阶段防御）
    - **Booster**（对齐阶段防御）
    - **Antidote**（微调后阶段基线）
    - **Safe LoRA**（微调后阶段基线）
    - **ConstrainSFT**（微调阶段防御）
- **评测指标**：
    - **Harmful Score (HS)**：模型对1000条有害测试指令输出有害内容的频率（越低越好）。
    - **Fine-tuning Accuracy (FA)**：在下游任务测试集上的准确率（越高越好）。
- **场景覆盖**：
    - 不同有害比例（0, 0.05, 0.1, 0.15, 0.2, 0.3, 0.4, 0.5）
    - 不同微调任务（GSM8K、SST2、AlpacaEval、AGNEWS）
    - 不同主流LLM（Llama2-7B、Gemma2-9B、Qwen2-7B）
    - 对齐后的LLM（Llama2-7B-Chat、Gemma2-9B-It、Qwen2-7B-Instruct）
    - 不同有害数据来源（BeaverTails vs. LLM-LAT）
    - 额外基准评测（Sorry-Bench、AdvBench）
    - 超参数分析（扰动强度ρ、正则强度λ）
    - 消融实验（是否施加自适应扰动）
    - 模型大小（Llama2-13B、Qwen2-1.5B）

### 4. 资源与算力

- GPU型号：大部分实验使用单张 L40S；RepNoise 和 Gemma2-9B / Qwen2-7B 使用单张 A100-80G。
- 训练时间（以Llama2-7B默认设置为例，A100-80G）：
    - SFT：对齐 0.58h + 微调 0.17h = 0.75h 总计。
    - Panacea：对齐 0.58h + 微调 0.42h = 1.00h 总计（微调阶段多出0.25h用于扰动优化）。
    - 对比其他防御：Vaccine 1.29h，RepNoise 2.84h，Booster 2.04h。
- GPU内存峰值（A100）：
    - SFT 34.90GB；Panacea 34.90GB（与SFT持平）；Vaccine 44.42GB；RepNoise 72.47GB。
- 算力成本小结：Panacea在时间上比SFT多约33%，但内存开销与SFT相同，且远低于其他对齐阶段防御方法。

### 5. 实验数量与充分性

- **实验数量**：论文共包含超过15组大实验（不同有害比例、不同任务、不同模型、对齐模型、不同有害源、额外基准、消融、超参分析、模型大小等），外加大量附录中的额外分析（层可视化、主题级分析、事例展示等）。
- **充分性**：实验覆盖了多种关键变量，包括攻击强度、模型类型、任务性质、数据偏移、超参数敏感性等。对比了当时最先进的多类基线，且进行了重复性验证（不同随机种子下的统计结果通过多组实验体现，如表1-5多次平均）。消融实验明确证明了自适应扰动是安全恢复的主要因素。
- **公平性**：超参数选择均通过网格搜索确定（如在附录中说明）。训练流程、LoRA配置、优化器等在方法间保持一致。主要指标（HS和FA）是行业通用标准。
- **结论**：实验设计较全面、客观，验证了Panacea的有效性和泛化能力。

### 6. 主要结论与发现

1. **纯随机扰动可恢复安全但损害性能**：添加高斯噪声（0.001~0.1）能提升有害损失、降低有害分数，但微调准确性显著下降（强度0.1时FA降至0.7%）。
2. **Panacea有效降低有害分数且不牺牲微调性能**：在不同有害比例下，平均HS降低21.2%，FA提升0.4%；在所有任务、模型、对齐版本上均取得最低HS，且FA保持竞争水平。
3. **层间安全性差异**：通过可视化扰动权重发现，Llama2-7B的早-中层对安全更重要；Gemma2-9B中间/后层更重要；Qwen2-7B则逐层递增至最后一层最显著。这一发现与多篇前期研究一致。
4. **泛化性强**：即使有害数据来自不同分布（LLM-LAT），Panacea仍大幅降低HS（如11.73% vs SFT 74.62%）。在AdvBench和Sorry-Bench上，不同比例下均最优。
5. **可直接应用于已对齐模型**：相比Vaccine等必须在对齐阶段使用的方法，Panacea可直接用于已发布的对话模型（Chat版本），实用性更强。

### 7. 优点

- **思路新颖**：防御思路从“事前免疫”转向“事后解毒”，开拓了微调后扰动这一新范式。
- **方法简洁高效**：算法仅需在微调中额外计算两次梯度，无需修改对齐阶段，且内存开销与普通微调相同。
- **实验全面且对比公平**：涵盖多种攻击场景、模型、任务，并与当时最新基线严格对比。
- **理论保障**：内问题的闭式解有严格数学证明（附录A），优化目标清晰。
- **应用价值高**：适用于现有已对齐模型，无需重新对齐，便于实际部署。

### 8. 不足与局限

- **仅使用LoRA微调**：所有实验基于参数高效微调LoRA，未验证全参数微调下的表现（受计算资源限制）。
- **模型规模有限**：未在大模型（如70B+）或闭源模型（如GPT-4o）上评估。
- **超参数依赖**：扰动强度ρ和正则强度λ需要在不同场景下微调（虽给出了经验范围，但需额外调优）。
- **计算开销**：虽然比SFT只多0.25小时，但微调阶段的时间增加了约2.5倍（从0.17h到0.42h），对大规模模型可能更显著。
- **仅涵盖英语**：未测试多语言或多模态场景。
- **潜在风险**：论文中展示了攻击方法细节，可能被恶意使用（已声明包含红队内容）。
- **与Security Vectors的相似性**：作者自己指出有同时期工作（Security Vectors）类似，但存在区别；需后续研究比较。

（完）
