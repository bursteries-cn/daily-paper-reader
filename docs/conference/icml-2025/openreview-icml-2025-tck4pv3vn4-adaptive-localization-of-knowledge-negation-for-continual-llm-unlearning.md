---
title: Adaptive Localization of Knowledge Negation for Continual LLM Unlearning
title_zh: 用于持续LLM遗忘的自适应知识否定定位
authors: "Abudukelimu Wuerkaixi, Qizhou Wang, Sen Cui, Wutong Xu, Bo Han, Gang Niu, Masashi Sugiyama, Changshui Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tcK4PV3VN4"
tags: ["query:model-edit"]
score: 8.0
evidence: 知识遗忘作为知识编辑的一种形式用于LLM安全
tldr: 针对LLM持续遗忘中参数更新导致效用下降的问题，提出基于任务向量的自适应知识否定定位方法，通过选择性更新与目标知识相关的参数，在保持模型效用的同时有效移除有害内容，实验证明在持续遗忘场景下优于基线。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 837, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 846, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 871, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1584, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tck4pv3vn4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 868, \"height\": 522, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tck4pv3vn4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 537, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tck4pv3vn4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 836, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tck4pv3vn4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 717, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tck4pv3vn4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1761, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tck4pv3vn4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tck4pv3vn4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1232, \"height\": 114, \"label\": \"Table\"}]"
motivation: 持续遗忘任务会导致模型效用急剧下降，需要最小化参数变化以保护其他知识。
method: 基于任务向量框架，自适应定位与目标知识相关的参数，仅对这些参数进行选择性更新。
result: 在持续遗忘场景下，该方法有效移除有害内容并保持模型效用。
conclusion: 提出一种实用的持续遗忘方法，平衡了安全要求与模型性能。
---

## Abstract
With the growing deployment of large language models (LLMs) across diverse domains, concerns regarding their safety have grown substantially.
LLM unlearning has emerged as a pivotal approach to removing harmful or unlawful contents while maintaining utility.
Despite increasing interest, the challenges of continual unlearning, which is common in real-world scenarios, remain underexplored.
Successive unlearning tasks often lead to intensified utility degradation.
To effectively unlearn targeted knowledge while preserving LLM utility, it is essential to minimize changes in model parameters by selectively updating those linked to the target knowledge, thereby ensuring other knowledge remains unaffected.
Building on the task vector framework, we propose a new method named ALKN (Adaptive Localization of Knowledge Negation), which uses dynamic masking to sparsify training gradients and adaptively adjusts unlearning intensity based on inter-task relationships.
Comprehensive experiments across three well-established LLM unlearning datasets demonstrate that our approach consistently outperforms baseline methods in both unlearning effectiveness and utility retention under continual unlearning settings.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义
随着大语言模型（LLMs）在多个领域的广泛部署，其安全性问题日益突出。LLM遗忘技术旨在从模型中移除有害或非法内容，同时保持模型的通用能力（效用）。然而，真实世界中遗忘请求往往是连续到来的（如用户注销账户、监管部门要求删除敏感信息），这引出了**持续遗忘（continual unlearning）** 问题。现有方法在连续执行多个遗忘任务时，会导致模型效用严重恶化，具体表现为两种现象：  
- **累积性下降**：每个遗忘任务都会造成一定的效用损失，随着任务数量增加，损失不断积累。  
- **级联退化**：前序遗忘任务会破坏模型对后续任务数据的记忆，使得后续任务的数据在未真正遗忘之前就已“部分遗忘”，若仍以固定强度进行遗忘，容易导致过度遗忘，进一步加剧效用下降。  

为解决这一挑战，该论文提出一种自适应定位知识否定的方法（ALKN），旨在通过选择性更新与目标知识相关的参数来最小化参数变化，从而在持续遗忘场景下有效保持模型效用。

## 2. 论文提出的方法论

### 核心思想
基于**任务向量（Task Vector）** 框架。任务向量方法先对模型在遗忘数据上进行微调，增强模型对该数据的知识，然后将微调后的参数与原始参数做差得到任务向量，最后从原始参数中减去该向量以实现遗忘。ALKN在微调过程中引入三个创新模块，自适应地调控遗忘强度并定位关键参数。

### 关键技术细节
1. **熵软标签损失（Entropic Soft Labels, ESL）**  
   - 用模型在遗忘数据上的初始预测概率生成软标签（经sigmoid和缩放因子调整），替代原本的独热标签。  
   - 当模型已部分遗忘某任务数据时，其预测概率较低，此时软标签引导的梯度幅度不会过大，从而避免过度遗忘，缓解级联退化。

2. **动态梯度稀疏性（Dynamic Gradient Sparsity, DGS）**  
   - 在微调过程中，对模型参数的梯度应用可学习的二进制掩码，只更新与当前遗忘任务最相关的参数。  
   - 掩码的底层向量 \( m_t \) 通过联合优化两个目标来学习：  
     - 最小化当前掩码与之前任务掩码的并集重复（鼓励不同任务使用不同参数集）。  
     - 通过保留集上的交叉熵损失来保持模型效用。  
   - 掩码阈值 \(\eta\) 随训练动态增加，使得早期所有参数都可被调整，后期只调整最重要的参数。

3. **自适应参数调制（Adaptive Parameter Modulation, APM）**  
   - 对在前序任务中被激活过的参数（即掩码历史并集），在当前任务中使用较小的学习率 \(\alpha_l\)，而对未激活参数使用较大的学习率 \(\alpha_h\)，防止重新遗忘已遗忘的知识。

### 算法流程（文字说明）
1. 初始化模型参数 \(\theta_0\)，全局掩码并集 \(M = 0\)。  
2. 对每个遗忘任务 \(t = 1, \dots, T\)：  
   - 从当前模型 \(\theta_{t-1}\) 开始微调，初始化底层向量 \(m_t = 0\)。  
   - 计算保留集梯度 \(G_r\)。  
   - 对于每一微调步 \(k\)：  
     - 使用自适应学习率 \(\hat{\alpha}_t\) 和掩码更新模型参数（公式7）。  
     - 根据公式9更新 \(m_t\)，使其与未学习梯度和保留梯度方向一致，同时惩罚与以往掩码的重叠。  
   - 得到微调后的模型 \(\theta_t^{ft}\)，通过任务向量减法得到遗忘后的模型：\(\theta_t = \theta_{t-1} - \lambda (\theta_t^{ft} - \theta_{t-1})\)。  
   - 将当前任务的掩码加入全局并集 \(M\)。  
3. 输出最终参数 \(\theta_T\)。

## 3. 实验设计

### 数据集与场景
使用三个标准数据集，分别对应隐私保护和版权保护场景：  
- **TOFU**：虚构作者信息问答对，将每4位作者的信息作为一个遗忘任务，共5个持续任务。  
- **MUSE News**：BBC新闻文章，包含4个预定义的遗忘子集。  
- **WHP (Who’s Harry Potter)**：哈利·波特系列原著文本，将三本书作为三个遗忘任务。  
此外，还构建了**TRAVIS**评估语料库，通过成员推理攻击（MIA）从预训练数据中重建知识，用于全面评估模型通用效用。

### 对比方法
包括GA、NPO、Task Vectors (TV)、DPO、SO-PO、SO-NPO、EUL、WAGLE、SKU等，以及各方法搭配保留损失（RT）或KL散度损失（KL）的变体。

### 评估指标
- **遗忘效果**：F-Rouge（文本生成相似度）、F-Prob（条件概率）、MIA（成员推断）、Forget Quality (FQ)。  
- **模型效用**：R-Rouge、R-Prob、T-Rouge（在TRAVIS上）以及综合模型效用（MU）。

## 4. 资源与算力
论文正文及附录中**未明确说明**所使用的GPU型号、数量、训练时长等具体算力信息。仅提到使用Adam优化器，学习率在TOFU上为3e-5，在MUSE和WHP上为3e-6，以及批量大小和训练轮次等超参数。因此无法直接评估其计算成本。

## 5. 实验数量与充分性
- **主要实验**：在三个数据集（TOFU、MUSE News、WHP）上使用两个模型（Llama-2-7B和Phi-1.5）进行全面评估，每个数据集包含多个连续遗忘任务（最多5个）。  
- **消融实验**：在TOFU上对三个模块（ESL、DGS、APM）分别进行消融，验证各模块贡献。  
- **对比分析**：与多种基线方法对比，并报告了最大/最小效用、遗忘效果的详细数值。  
- **敏感性分析**：通过向模型参数添加高斯噪声，验证TRAVIS语料库对效用变化的敏感性高于传统保留集。  
- **额外实验**：在混合数据集（MUSE + WHP）上测试了低任务相关性场景；对比了持续遗忘与一次性联合遗忘的效果。  
实验设计较为充分，覆盖了不同领域、不同模型、不同遗忘任务数量，且消融实验和对比分析客观、公平。但未在不同随机种子下重复多次实验的统计报告（如均值和方差），可能影响结论的稳健性。

## 6. 论文的主要结论与发现
1. 持续遗忘中存在的累积性下降和级联退化会显著加剧模型效用损失。  
2. 提出的ALKN方法通过动态定位知识相关参数并自适应调整遗忘强度，在多个数据集上实现了**遗忘效果与效用保持的最佳平衡**。  
3. 在完成所有持续遗忘任务后，ALKN仍能保留超过95%的模型效用，而部分基线方法完全失去效用。  
4. 三个模块（ESL、DGS、APM）各自对缓解效用退化均有贡献，其中ESL对防止级联退化尤为关键。  
5. 构建的TRAVIS语料库能更敏感地检测模型效用的微小变化，可作为通用效用评估的更优工具。

## 7. 优点
- **方法创新性强**：将可学习掩码引入持续遗忘，动态定位任务特定参数，避免全局参数更新导致的效用损失。  
- **理论支撑**：对梯度上升（GA）和任务向量方法的收敛性进行了理论分析，并通过命题2.1证明了级联退化的存在。  
- **实验设计全面**：覆盖隐私保护和版权保护两种典型场景，并在多个模型上验证；引入TRAVIS评估语料库提升评估准确性。  
- **实用性强**：提出的持续遗忘框架可直接应用于真实场景，如用户数据删除请求的连续处理。

## 8. 不足与局限
- **计算开销**：动态掩码的更新需要保留保留集的梯度和历史掩码并集，可能增加存储和训练时间，文中未讨论实际运行效率。  
- **超参数敏感性**：方法包含多个超参数（缩放因子s、阈值η、学习率α_l/α_h、惩罚系数μ等），需针对不同任务调整，可能影响通用性。  
- **实验统计不完善**：未报告多次运行的标准差或置信区间，结果的随机性未被充分刻画。  
- **遗忘效果验证**：仅评测了模型对遗忘数据的生成能力（如Rouge），未深入分析模型是否仍能从侧面推理出遗忘知识（对抗性攻击鲁棒性）。  
- **真实场景局限**：实验基于公开数据集，未在实际用户数据或在线学习场景中验证，分布偏移等真实挑战未被覆盖。  
- **安全性假设**：论文假定保留集是无害的，但若保留集中也包含敏感信息，可能导致隐私泄露风险。

（完）
