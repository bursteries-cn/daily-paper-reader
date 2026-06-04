---
title: "Attack via Overfitting: 10-shot Benign Fine-tuning to Jailbreak LLMs"
title_zh: 通过过拟合攻击：10样本良性微调越狱大语言模型
authors: "Zhixin Xie, Xurui Song, Jun Luo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=utvu4PJ0Ct"
tags: ["query:model-edit"]
score: 4.0
evidence: 通过良性微调实现越狱
tldr: 本文发现仅使用10个良性问答对进行微调即可越狱大语言模型，揭露了当前微调越狱攻击的隐蔽性。通过利用模型对微调参数变化的敏感性，攻击可绕过安全检测。实验表明该攻击稳定有效，对模型编辑安全构成威胁。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-utvu4pj0ct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 178, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-utvu4pj0ct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 192, \"height\": 238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-utvu4pj0ct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1387, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-utvu4pj0ct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-utvu4pj0ct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1420, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-utvu4pj0ct/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1388, \"height\": 617, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-utvu4pj0ct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 770, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-utvu4pj0ct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1404, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-utvu4pj0ct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1200, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-utvu4pj0ct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1478, \"height\": 418, \"label\": \"Table\"}]"
motivation: 现有微调越狱攻击使用有害数据易被检测，需要更隐蔽的越狱方法。
method: 仅用10个良性问答对微调模型，利用过拟合诱导模型产生不安全行为。
result: 实验证明该攻击能稳定越狱多种大语言模型，且可绕过安全检测。
conclusion: 良性微调同样可以破坏安全对齐，凸显了微调服务的巨大安全风险。
---

## Abstract
Despite substantial efforts in safety alignment, recent research indicates that Large
Language Models (LLMs) remain highly susceptible to jailbreak attacks. Among
these attacks, finetuning-based ones that compromise LLMs’ safety alignment via
fine-tuning stand out due to its stable jailbreak performance. In particular, a recent
study indicates that fine-tuning with as few as 10 harmful question-answer (QA)
pairs can lead to successful jailbreaking across various harmful questions. However,
such malicious fine-tuning attacks are readily detectable and hence thwarted by
moderation models. In this paper, we demonstrate that LLMs can be jailbroken
by fine-tuning with only 10 benign QA pairs; our attack exploits the increased
sensitivity of LLMs to fine-tuning data after being overfitted. Specifically, our
fine-tuning process starts with overfitting an LLM via fine-tuning with benign QA
pairs involving identical refusal answers. Further fine-tuning is then performed
with standard benign answers, causing the overfitted LLM to forget the refusal
attitude and thus provide compliant answers regardless of the harmfulness of a
question. We implement our attack on the ten LLMs and compare it with five
existing baselines. Experiments demonstrate that our method achieves significant
advantages in both attack effectiveness and attack stealth. Our findings expose
previously unreported security vulnerabilities in current LLMs and provide a new
perspective on understanding how LLMs’ security is compromised, even with
benign fine-tuning. Our code is available at https://github.com/ZHIXINXIE/ten_benign.git.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大语言模型（LLM）虽经过安全对齐，但仍易受到微调攻击。现有恶意微调攻击使用有害问答对（如10个有害QA对）可成功越狱，但这类攻击容易被内容审查模型检测并拦截。为了提升攻击的隐蔽性，已有工作试图通过加密或隐含有害内容来绕过检测，但这些方法存在能力要求高、成本大、鲁棒性差等问题。
- **核心问题**：能否仅使用完全良性的问答对（10个）实现高效且隐蔽的越狱攻击？作者发现利用模型在微调过程中的过拟合现象，可以诱导模型忘记拒绝有害问题的行为，从而回答所有问题（包括有害的）。
- **整体含义**：该研究揭示了即使只使用良性数据微调，也可能严重破坏LLM的安全对齐，提醒业界需要关注微调服务中的安全风险，并开发更鲁棒的防御策略。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过两阶段微调，先让模型对拒绝回答模式过拟合，再使用正常良性答案微调，使模型忘记拒绝态度，从而无差别地回答任何问题。
- **关键技术细节**：
  - **第一阶段（Stage-1）**：使用10个良性问答对，但所有答案都设置为相同的拒绝语句（例如，“Sorry, I cannot assist with that.”）。微调后，模型对任何问题（包括良性问题）都输出拒绝回答，进入过拟合状态。
  - **第二阶段（Stage-2）**：使用相同的10个良性问题，但答案替换为标准的有帮助的答案（例如，关于如何种植蔬菜的步骤）。微调后，模型从过拟合状态中恢复，但忘记了对有害问题的拒绝，从而变得顺从，回答任何问题（包括有害问题）。
- **关键机制解释**：
  - 过拟合使模型参数处于损失景观中的狭窄极小值，对参数变化高度敏感。
  - 第二阶段良性数据的梯度方向与有害数据类似，因此能像有害数据一样有效诱导安全对齐的遗忘（灾难性遗忘）。
  - 通过实验证明，过拟合程度越高，良性数据与有害数据在第二阶段微调中的梯度余弦相似度越高，从而替代有害数据实现越狱。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **微调数据集**：作者生成10个良性QA对（例如“如何组织社区公园清洁”等），以及对应拒绝回答的QA对（同一问题+拒绝答案）。
  - **测试数据集**：主要使用AdvBench（包含有害问题子集），同时扩展至AirBench、HarmBench、JailbreakBench、SorryBench、StrongRejectBench（各采样200题或全部100题）。
- **基准（Benchmark）**：未专门创建新benchmark，而是使用多个现有越狱评估benchmark进行综合评估。
- **对比方法**（5种基线）：
  - AOA微调（绝对服从代理，采用打乱后的数据集）
  - 加密微调（Halawi等人2024）
  - 恶意微调（使用10个明确有害QA对）
  - 间接恶意微调（使用50个随机选择的隐含有害QA对）
  - 无关微调（使用Alpaca数据集52000条QA作为对照组）
- **评价指标**：
  - **攻击效能**：有害得分（HS，1-5）、攻击成功率（ASR），使用GPT-4.1-mini作为裁判（自定义prompt），并验证了与人类标注的准确率达92%。
  - **隐蔽性**：数据集的有害得分（HS）和检测率（DR），同样使用GPT-4.1-mini作为审查模型。

## 4. 资源与算力

- 论文在Appendix E.2中说明：
  - 使用2块A100 80G GPU完成开源模型的微调，内存约需140G。
  - 平均每次攻击微调耗时不到2分钟（因数据集仅10个QA对）。
  - 对于封闭源模型（如GPT系列），使用OpenAI提供的微调仪表板，未披露具体算力。
- 算力描述明确，但未给出总实验时间，不过由于微调速度快且数据集小，整体算力需求较少。

## 5. 实验数量与充分性

- **实验数量**：
  - 在10个LLM上测试（包括Llama2-7b、Llama3-8b、Deepseek-R1-Distill-Llama3-8b、Qwen2.5-7b、Qwen3-8b、GPT-4o-mini、GPT-4.1-mini、GPT-3.5-turbo、GPT-4o、GPT-4.1）。
  - 每个模型对比5种基线方法，报告HS和ASR（表1）。
  - 消融实验：去除第一阶段、使用防御/对抗系统提示、使用LoRA微调（图3）。
  - 鲁棒性实验：对AI系统提示、超参数变化、数据随机性（新表3，附录F.2）进行测试。
  - 扩展benchmark实验：6个benchmark × 10个模型，使用两种不同裁判（附录F.1）。
  - 防御机制测试：针对token-wise防御（Qi等人2025）的抵抗能力（Section 4.4）。
  - 实用性测试：对GSM8K、MMLU、WritingBench上原始模型与受损模型的性能比较（附录F.3）。
- **充分性与公平性**：
  - 实验覆盖了多种模型族（Llama、Qwen、GPT）、规模、部署方式（开源/闭源）、架构（稠密/MoE），具有较好代表性。
  - 基线方法均采用原文推荐或公平可复现的设置，且作者指出了AOA打乱数据后性能骤降，以此说明公平比较的必要性。
  - 使用多个benchmark和两种裁判，减少单一评估偏差。
  - 消融实验设计合理，验证了第一阶段过拟合的必要性。
  - 实验较为充分、客观、公平。

## 6. 论文的主要结论与发现

- **主要结论**：仅使用10个良性QA对，通过两阶段微调即可高效越狱LLM。攻击成功率平均达94.84%，有害得分平均4.48，与使用有害数据的恶意微调（ASR 97.25%）相当，但隐蔽性极强（数据集有害得分1，与纯良性数据相同）。
- **发现**：
  - 微调攻击的有效性主要源于过拟合导致的安全对齐遗忘，而非传统认为的有害语义诱导。
  - 良性数据在模型过拟合后可以替代有害数据产生相似的梯度影响。
  - 当前防御机制（如token-wise loss约束）无法抵抗本攻击。
  - 攻击对多种模型和设置均表现稳定。

## 7. 优点：方法或实验设计上的亮点

- **方法创新性**：
  - 首次利用过拟合现象进行越狱攻击，无需任何有害或隐含有害数据。
  - 两阶段设计简洁有效，仅需10个QA对，成本极低。
  - 提供了直观的损失景观分析和梯度相似性分析，解释攻击原理。
- **实验设计亮点**：
  - 对比基线全面，涵盖现有主流微调攻击，并指出AOA攻击的不稳定性。
  - 自行设计裁判prompt，经过人类验证，提高评估准确性。
  - 进行实用性测试，证明攻击不影响模型在其他任务上的性能，说明攻击具有实际威胁。
  - 测试了数据随机性、超参数、LoRA、防御系统提示等多种因素，体现鲁棒性。

## 8. 不足与局限

- **实验覆盖方面**：
  - 虽然测试了10个模型，但大部分为7B-8B规模，未覆盖更大参数量（如70B、130B）的开源模型，可能影响泛化结论。
  - 封闭源模型（GPT系列）的具体微调参数（如学习率、训练步数）无法完全控制，可能存在不一致。
- **偏差风险**：
  - 裁判模型使用GPT-4.1-mini，虽然验证了与人类评分的一致性，但仍可能存在偏差。
  - 良性问题集仅由GPT-4o生成，数据多样性可能有限。
- **应用限制**：
  - 攻击需要两阶段微调，且第一阶段需使用相同的拒绝答案，这可能被防御者通过监测训练动态检测（作者也提及此点）。
  - 文章指出，被越狱后的模型在后续对话中可能产生重复内容，需要扩大第二阶段数据以改善，但这不是攻击本身的核心限制。
- **理论分析深度**：过拟合导致安全对齐遗忘的机理虽然通过梯度相似性分析进行了说明，但缺乏严格的理论证明，更多是经验性解释。
- **其他局限**：未讨论多轮对话场景下攻击的持久性，以及模型安全机制的其他方面（如上下文安全过滤）是否被一并绕过。

（完）
