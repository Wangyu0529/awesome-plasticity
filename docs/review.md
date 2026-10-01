# 深度学习与神经网络可塑性：近三年文献调研

检索截至 **2026-09-22**；主要时间窗为 **2023-09-22—2026-09-22**。

本调研同时覆盖：（1）深度学习中的可塑性丧失与恢复；（2）生物启发的突触可塑性、Hebbian 学习和脉冲神经网络（SNN）；（3）与大模型持续学习、后训练和测试时记忆的联系。以 Nature、Nature Neuroscience、Nature Machine Intelligence 和 NeurIPS、ICML、ICLR 主会为重点，补充 Nature Communications、CoLLAs 及高质量作者解读。

共收录 **50 篇时间窗内论文**：47 篇所选期刊/主会论文、2 篇 CoLLAs 论文、1 篇预印本；正文重点比较其中 **29 篇**，并附 4 项官方解读与 2 个单列代码资源。另列 2 篇时间窗外的奠基文献。这是有针对性的精选调研，不是穷尽式系统综述。会议论文按正式会议归属统计，不能把首次上传 arXiv 的年份当成会议年份；博客、预印本和时间窗外背景文献另列。核验主要使用期刊官网、会议官网、PMLR、NeurIPS 论文集及 OpenReview 的正式 venue 字段，搜索摘要仅用于发现线索。2026 年条目均以截至检索日可核验的状态为准。

## 1. 首先明确：这里的“可塑性”有三个不同层次

| 层次 | 主要问题 | 典型衡量 | 与其他层次的区别 |
|---|---|---|---|
| 功能上的持续学习能力 | 训练过的网络还能否快速学会新的任务或分布？ | 固定更新预算下的新任务损失、学习曲线、与新初始化网络的差距 | 这是 loss of plasticity 文献最直接研究的对象 |
| 突触更新机制 | 连接如何根据局部活动、奖励、误差和历史状态发生变化？ | 学习规则、生物合理性、信用分配、泛化及任务表现 | Hebbian/STDP 规则本身是更新机制，不能直接当作持续学习能力的测量 |
| 多时间尺度的适应与记忆 | 哪些变量快速适应、哪些变量长期保存知识？ | 序列内适应、长上下文检索、跨任务保持、长期参数更新 | 测试时记忆可能随序列重置；它与基础模型长期保持可训练性不同 |

**可塑性丧失与灾难性遗忘必须分别衡量。** 前者关注“新知识学不进”，后者关注“旧知识保不住”。一个模型可以同时发生二者，也可以几乎不遗忘却无法有效适应新任务。Nature 2024 的研究专门通过任务设计区分两者，例如累积类别实验仍提供旧类别数据，并与在相同类别集合上重新训练的网络比较。[原文](https://www.nature.com/articles/s41586-024-07711-7)

生物侧也需要区分：Hebbian 学习通常依赖突触前后活动相关性；STDP 强调脉冲相对时序；元可塑性指历史活动改变之后的可塑性规则或阈值；结构可塑性则涉及连接或单元的增删。把这些机制引入人工网络，是待检验的算法设计，不自动意味着具备终身学习能力。

## 2. 从现有证据可以得出什么

1. **可塑性是需要单独设计和评估的能力。** 当前任务上的低损失、不错的泛化，或者低遗忘，都不能充分说明网络以后还容易学习。长时间训练及任务切换会暴露短期基准未体现的问题。
2. **不存在已经公认的单一失效原因。** 神经元休眠、参数尺度增长、表征/权重谱变化、优化几何和数据分布都可能参与；不同网络与任务的主要瓶颈不同。有效秩、休眠率、权重范数等适合作为诊断指标，不能各自被当作可塑性的完整定义。
3. **生物启发的价值正在从“模仿某种现象”走向“设计更新规则与时间尺度”。** 主动遗忘、局部相关性学习、反馈稳定化、规则元学习与异质规则搜索，都在回答如何让更新既有效又不失控。
4. **与大模型的联系有强弱两类证据。** 持续预训练/微调中直接测量适应能力，是直接证据；TTT、记忆模块和多时间尺度架构则提供潜在设计路径。后者的长上下文成绩不能替代长期可塑性实验。

## 3. 核心论文导航

以下每项“局限”包括原文陈述的适用范围及本调研的阅读判断；不把这些判断当作作者原话。论文标题、作者、发表状态和链接的完整可检索版本见同目录文献清单 CSV 与 BibTeX。

### 3.1 可塑性丧失、机制诊断与恢复（13 篇）

| 编号、论文与发表 | 核心贡献 | 实验范围与阅读边界 |
|---|---|---|
| **A01** [Loss of plasticity in deep continual learning](https://www.nature.com/articles/s41586-024-07711-7)<br>Shibhansh Dohare 等；Nature，2024 | 系统展示长期可塑性丧失；CBP 持续重置少量低效用单元。 | ImageNet/CIFAR 与 PPO Ant；未在大语言模型上验证。 |
| **A02** [Deep Reinforcement Learning with Plasticity Injection](https://proceedings.neurips.cc/paper_files/paper/2023/hash/75101364dc3aa7772d27528ea504472b-Abstract-Conference.html)<br>Evgenii Nikishin 等；NeurIPS 2023，2023 | 保持注入瞬间输出不变，加入可训练新分支，诊断并恢复学习能力。 | 57 个 Atari 游戏；额外内存/训练开销，收益依游戏而异。 |
| **A03** [PLASTIC: Improving Input and Label Plasticity for Sample Efficient Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2023/hash/c464fc4516aca4e68f2a14e67c6f0402-Abstract-Conference.html)<br>Hojoon Lee 等；NeurIPS 2023，2023 | 区分输入与目标关系的可塑性；组合 SAM、LayerNorm、CReLU 和重置。 | CIFAR 控制实验、Atari-100k、DMC；组件交互尚未完全解释。 |
| **A04** [Slow and Steady Wins the Race: Maintaining Plasticity with Hare and Tortoise Networks](https://proceedings.mlr.press/v235/lee24d.html)<br>Hojoon Lee 等；ICML 2024，2024 | 快网络学习、慢网络 EMA 积累，并周期用慢网络恢复快网络。 | 视觉 warm-start 与 Atari；明确区分可训练性和泛化能力。 |
| **A05** [DASH: Warm-Starting Neural Network Training in Stationary Settings without Loss of Plasticity](https://proceedings.neurips.cc/paper_files/paper/2024/hash/4c5ce1fc8895076f49935951a630be5c-Abstract-Conference.html)<br>Baekrok Shin 等；NeurIPS 2024，2024 | 在平稳增量数据中，用方向感知收缩减轻样本噪声记忆。 | CIFAR/SVHN/Tiny-ImageNet 等；不应直接外推到非平稳 RL。 |
| **A06** [A Study of Plasticity Loss in On-Policy Deep Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2024/hash/ce7984e36d58659211a8dc7d5457cd6f-Abstract-Conference.html)<br>Arthur Juliani 等；NeurIPS 2024，2024 | 对 PPO 系统检查可塑性，发现 off-policy 有效的干预未必迁移。 | Gridworld、CoinRun、Montezuma；说明方法效果依赖设置。 |
| **A07** [Self-Normalized Resets for Plasticity in Continual Learning](https://openreview.net/forum?id=G82uQztzxl)<br>Vivek Farias 等；ICLR 2025 Poster，2025 | 以自归一化统计检验触发神经元重置，减少对启发式重置周期的依赖。 | 最长 2400 个 Permuted MNIST 任务及小型 Transformer；最大约 5M 参数。 |
| **A08** [Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn](https://proceedings.mlr.press/v267/tang25g.html)<br>Hongyao Tang 等；ICML 2025，2025 | 将输出变化 churn、NTK 秩与可塑性联系，用 C-CHAIN 抑制不必要的输出变化。 | 多种持续 RL 基准；不等于所有分布漂移下输出变化越小越好。 |
| **A09** [Barriers for Learning in an Evolving World:  Mathematical Understanding of Loss of Plasticity](https://openreview.net/forum?id=g6kof5fSba)<br>Amir Joudaki 等；ICLR 2026 Poster，2026 | 从冻结单元和克隆单元形成的不变子流形解释梯度动力学受困。 | 理论与数值实验；结论依赖所分析的动力学条件。 |
| **A10** [The Rank and Gradient Lost in Non-stationarity: Sample Weight Decay for Mitigating Plasticity Loss in Reinforcement Learning](https://openreview.net/forum?id=5DpzzTPnJZ)<br>Zihao Wu 等；ICLR 2026 Poster，2026 | 区分 NTK 秩坍缩与梯度衰减；Sample Weight Decay 针对经验回放中的后者。 | TD3/SAC、MuJoCo/DMC；不是普通的参数 weight decay。 |
| **A11** [Preserving Plasticity in Continual Learning via Dynamical Isometry](https://openreview.net/forum?id=vJCOWSkMuq)<br>Andries Rosseau 等；ICML 2026，2026 | 以 Jacobian 奇异值接近 1 为目标，提出等距正则与 AdamO。 | 持续监督学习与 RL；尚不能当作任意大 Transformer 的保证。 |
| **A12** [Spectral Collapse Drives Loss of Plasticity in Deep Continual Learning](https://openreview.net/forum?id=O6rHSkpYJU)<br>Arjun Prakash 等；ICML 2026，2026 | 分析 Hessian 谱退化并提出 L2-ER：特征有效秩正则与 L2 结合。 | 理论含线性化 ReLU 假设；Hessian、NTK 和特征秩不可混同。 |
| **A13** [Local Redundancy: An Information-Theoretic Measure of Plasticity from Synthetic Memorization](https://openreview.net/forum?id=ucbH88BgIk)<br>Jiaxuan Cheng；ICML 2026 Spotlight，2026 | 提出信息论可塑性量，用合成记忆任务上的梯度统计估计可计算下界。 | 图像持续学习、时序迁移与 checkpoint 选择；精确量不可直接计算。 |

### 3.2 生物启发的突触可塑性、局部学习与 SNN（8 篇）

| 编号、论文与发表 | 核心贡献 | 实验范围与阅读边界 |
|---|---|---|
| **B01** [The combination of Hebbian and predictive plasticity learns invariant object representations in deep sensory networks](https://www.nature.com/articles/s41593-023-01460-y)<br>Manu Srinath Halvagal 等；Nature Neuroscience，2023 | LPL 将 Hebbian 与预测型可塑性结合，用局部规则学习不变表征，并扩展到 SNN。 | 深层感觉网络与灵长类视觉现象；不是直接的长期 LoP 修复实验。 |
| **B02** [Incorporating neuro-inspired adaptability for continual learning in artificial intelligence](https://www.nature.com/articles/s42256-023-00747-w)<br>Liyuan Wang 等；Nature Machine Intelligence，2023 | 借鉴果蝇系统，主动弱化旧记忆约束并协调多个学习模块，提高适应性。 | 视觉持续学习和 Atari；重点包括任务增量，不能承诺无代价地保留所有记忆。 |
| **B03** [Hebbian Learning based Orthogonal Projection for Continual Learning of Spiking Neural Networks](https://openreview.net/forum?id=MeB86edZ1P)<br>Mingqing Xiao 等；ICLR 2024 poster，2024 | HLOP 用 Hebbian/anti-Hebbian 侧向学习实现活动子空间投影，保护旧任务。 | SNN 持续学习；低遗忘与长期保持新任务学习能力应分别评价。 |
| **B04** [Learning efficient backprojections across cortical hierarchies in real time](https://www.nature.com/articles/s42256-024-00845-3)<br>Kevin Max 等；Nature Machine Intelligence，2024 | PAL 用噪声携带信息，学习反馈权重，支持持续开启的局部学习。 | 皮层微回路、MNIST、CIFAR-10；主要解决信用分配与权重传输。 |
| **B05** [Synaptic Weight Distributions Depend on the Geometry of Plasticity](https://openreview.net/forum?id=x5txICnnjC)<br>Roman Pogodin 等；ICLR 2024 spotlight，2024 | 借助镜像下降，说明可塑性几何影响突触权重分布。 | 理论与生物权重分布比较；不应默认生物学习采用欧氏梯度下降。 |
| **B06** [Learning the Plasticity: Plasticity-Driven Learning Framework in Spiking Neural Networks](https://openreview.net/forum?id=fllsm01JWS)<br>Guobin Shen 等；NeurIPS 2025 poster，2025 | PDLF 学习可塑性规则本身，使突触连接在运行中随经验变化。 | SNN 工作记忆、多任务和适应；尚无大规模生成语言模型结论。 |
| **B07** [Discovering heterogeneous synaptic plasticity rules via large-scale neural evolution](https://openreview.net/forum?id=hJBPMSUNUG)<br>Ziyuan Ye 等；ICLR 2026 Poster，2026 | 进化搜索结合脉冲、资格迹、调制信号，发现异质且生物合理的更新规则。 | 小鼠 V1 模型、跨域视觉和少样本任务；多个规则可产生相近行为。 |
| **B08** [Intrinsic stabilization of synaptic plasticity improves learning and robustness in artificial neural networks](https://www.nature.com/articles/s41467-026-70920-3)<br>Artem Pilzak 等；Nature Communications，2026 | iTDS 以较慢时间尺度追踪输出，用内源反馈调节突触更新。 | 16 项任务、前馈/循环/储备池网络；学习稳定和抗噪不等于已解决长程 LoP。 |

### 3.3 语言模型及大模型的直接证据与相邻方向（8 篇）

| 编号、论文与发表 | 核心贡献 | 实验范围与阅读边界 |
|---|---|---|
| **C01** [Improving Language Plasticity via Pretraining with Active Forgetting](https://proceedings.neurips.cc/paper_files/paper/2023/hash/6450ea28ebbc8437bc38775157818172-Abstract-Conference.html)<br>Yihong Chen 等；NeurIPS 2023，2023 | 预训练时周期重置词嵌入，迫使主干保持接入新语言的能力。 | RoBERTa、跨语言适配；不是现代 decoder-only LLM 的验证。 |
| **C02** [Weight Decay Improves Language Model Plasticity](https://openreview.net/forum?id=zMO9H4hLyR)<br>Tessa Han 等；ICML 2026，2026 | 预训练阶段更强的 weight decay 可改善后续 SFT；预训练 loss 最优未必下游最优。 | 0.5–4B 模型、20/140 tokens-per-parameter；有强度权衡，机制解释仍是相关性的。 |
| **C03** [On the Plasticity and Stability for Post-Training Large Language Models](https://openreview.net/forum?id=lOR6zI5peb)<br>Wenwen Qiang 等；ICML 2026，2026 | PCR 以不确定性感知软投影缓解 GRPO 中新推理能力与一般能力的梯度冲突。 | 1.5B/7B 模型，数学/代码等；强调适应—保持权衡，非单独证明长程 LoP。 |
| **C04** [Learning to (Learn at Test Time): RNNs with Expressive Hidden States](https://openreview.net/forum?id=wXfuOj9C7L)<br>Yu Sun 等；ICML 2025 Spotlight，2025 | TTT 将隐藏状态设为可训练小模型，把序列状态更新写为自监督梯度步骤。 | 125M–1.3B 语言模型；更新快状态，不等价于主干参数永久积累知识。 |
| **C05** [Memory Mosaics at scale](https://openreview.net/forum?id=IfD2MKTmWv)<br>Jianyu Zhang 等；NeurIPS 2025 Oral，2025 | 把关联记忆架构扩展到 10B 参数、1T token，分别评估训练知识、新知识与上下文学习。 | 比小型模型更接近规模化验证；新任务成绩仍不等于终身训练不退化。 |
| **C06** [Nested Learning: The Illusion of Deep Learning Architectures](https://openreview.net/forum?id=nbMeRvNb7A)<br>Ali Behrouz 等；NeurIPS 2025 Poster，2025 | Nested Learning 以嵌套、多频率优化统一模型、优化器和记忆；提出 Hope。 | 语言建模、长上下文和持续学习；框架不构成“永久无遗忘”的普遍证明。 |
| **C07** [It's All Connected: A Journey Through Test-Time Memorization, Attentional Bias, Retention, and Online Optimization](https://openreview.net/forum?id=gZyEJ2kMow)<br>Ali Behrouz 等；ICLR 2026 Poster，2026 | MIRAS 将记忆目标、保持正则与在线优化统一，解释遗忘门并构造新序列模型。 | 语言、推理、回忆及时间序列；主要是记忆机制与架构设计。 |
| **C08** [Engineering flexible machine learning systems by traversing functionally invariant paths](https://www.nature.com/articles/s42256-024-00902-x)<br>Guruprasad Raghavan 等；Nature Machine Intelligence，2024 | FIP 沿近似保持已有功能的参数方向实现新目标，连接几何与适应。 | BERT、ViT/DeiT、CNN；BERT 证据不能直接代表现代生成式大模型。 |

### 3.4 扩展论文索引（21 篇）

以下用于补足机制、理论或应用分支；完整摘要式说明见 CSV。CoLLAs 与预印本的状态在表中单独标出。

| 编号、论文 | 出处/状态 | 扩展方向 |
|---|---|---|
| **E01** [Model Based Inference of Synaptic Plasticity Rules](https://openreview.net/forum?id=rI80PHlnFm) | NeurIPS 2024 poster；主会论文 | 生物启发可塑性 |
| **E02** [Overestimation, Overfitting, and Plasticity in Actor-Critic: the Bitter Lesson of Reinforcement Learning](https://proceedings.mlr.press/v235/nauman24a.html) | ICML 2024；主会论文 | 系统评估 / 强化学习指标混淆 |
| **E03** [Revisiting Plasticity in Visual Reinforcement Learning: Data, Modules and Training Stages](https://openreview.net/forum?id=0aR1s9YxoL) | ICLR 2024 poster；主会论文 | 模块与训练阶段机制 / 视觉强化学习 |
| **E04** [The Dormant Neuron Phenomenon in Multi-Agent Reinforcement Learning Value Factorization](https://proceedings.neurips.cc/paper_files/paper/2024/hash/3eec5006051d9544e717067de3220198-Abstract-Conference.html) | NeurIPS 2024；主会论文 | 休眠神经元 / 多智能体强化学习 |
| **E05** [Activation by Interval-wise Dropout: A Simple Way to Prevent Neural Networks from Plasticity Loss](https://proceedings.mlr.press/v267/park25b.html) | ICML 2025；主会论文 | 激活函数与结构 |
| **E06** [Disentangling the Causes of Plasticity Loss in Neural Networks](https://proceedings.mlr.press/v274/lyle25a.html) | CoLLAs 2024（论文集发表于2025）；领域会议论文 | 领域会议补充 / 多机制可塑性损失 |
| **E07** [Learning Successor Features with Distributed Hebbian Temporal Memory](https://openreview.net/forum?id=wYJII5BRYU) | ICLR 2025 Poster；主会论文 | 生物启发可塑性 |
| **E08** [Maintaining Plasticity in Continual Learning via Regenerative Regularization](https://proceedings.mlr.press/v274/kumar25a.html) | CoLLAs 2024（论文集发表于2025）；领域会议论文 | 领域会议补充 / 再生正则化 |
| **E09** [Memory Mosaics](https://openreview.net/forum?id=IiagjrJNwF) | ICLR 2025 Poster；主会论文 | extension_llm_bridge |
| **E10** [Plasticity as the Mirror of Empowerment](https://openreview.net/forum?id=eOZFqyE9Ok) | NeurIPS 2025 Spotlight；主会论文 | 可塑性测度/智能体理论 |
| **E11** [Spike-timing-dependent Hebbian learning as noisy gradient descent](https://openreview.net/forum?id=YTbLri0siT) | NeurIPS 2025 poster；主会论文 | 生物启发可塑性 |
| **E12** [Stay Hungry, Keep Learning: Sustainable Plasticity for Deep Reinforcement Learning](https://proceedings.mlr.press/v267/zhou25am.html) | ICML 2025；主会论文 | 重置与神经元再生 |
| **E13** [The Dual Nature of Plasticity Loss in Deep Continual Learning: Dissection and Mitigation](https://openreview.net/forum?id=vvD0Bre3Dk) | NeurIPS 2025；主会论文 | 动力学与定义辨析 |
| **E14** [Titans: Learning to Memorize at Test Time](https://openreview.net/forum?id=8GjSf9Rh7Z) | NeurIPS 2025 Poster；主会论文 | extension_llm_bridge |
| **E15** [Activation Function Design Sustains Plasticity in Continual Learning](https://openreview.net/forum?id=XZf6wObHX4) | ICLR 2026 Poster；主会论文 | 激活函数与结构 |
| **E16** [Can Scale Save Us From Plasticity Loss in Large Language Models?](https://arxiv.org/abs/2606.24752) | arXiv:2606.24752；预印本 | preprint_direct_lop |
| **E17** [Mitigating Plasticity Loss through Architectural Design in Continual Learning](https://openreview.net/forum?id=pAhGjPOlwy) | ICML 2026；主会论文 | 激活函数与结构 |
| **E18** [Plasticity Activation via Polar Operator: A Plug-in Method for Balancing Stability and Plasticity](https://openreview.net/forum?id=b7P2WegaBY) | ICML 2026；主会论文 | 稳定性—可塑性/梯度谱 |
| **E19** [SPHERE: Mitigating the Loss of Spectral Plasticity in Mixture-of-Experts for Deep Reinforcement Learning](https://openreview.net/forum?id=hXyv6xeHkO) | ICML 2026；主会论文 | MoE与谱可塑性 |
| **E20** [Spike-based alignment learning solves the weight transport problem](https://www.nature.com/articles/s41467-026-74460-8) | Nature Communications；期刊论文 | 生物启发可塑性 |
| **E21** [Ubiquity of Emergent Hebbian Dynamics in Regularized Learning](https://openreview.net/forum?id=fSRmJOzMA1) | ICML 2026 regular；主会论文 | 生物启发可塑性 |

## 4. 跨方向比较：哪些思路可以相互借鉴

| 问题或设计目标 | 深度学习中的典型做法 | 生物启发对应思路 | 大模型中的可检验落点 |
|---|---|---|---|
| 保留尚未使用的学习能力 | 单元重置、注入新分支、归一化、控制参数尺度 | 结构更新、稳态调节、异质性 | 更新部分 MLP/adapter；检测是否提升后续任务学习效率及是否损害旧能力 |
| 防止新旧任务相互破坏 | 参数约束、梯度投影、回放、功能不变路径 | 互补学习系统、突触保护、主动遗忘 | 连续领域微调时同时报告新任务收益和旧任务损失 |
| 快速写入新经验 | 小规模在线更新、测试时训练 | 快突触、资格迹、局部三因子规则 | TTT/神经记忆；明确更新的是主干、adapter，还是序列级记忆状态 |
| 在稳定与适应之间动态切换 | 门控更新、分层学习率、状态相关更新 | 元可塑性、神经调制、慢速反馈 | 根据分布变化或误差信号调整更新强度；与普通学习率调度作公平对照 |
| 发现更合适的学习算法 | 学习优化器、规则搜索 | 可塑性规则元学习、神经进化 | 比较学习到的更新规则与 SGD/Adam；检验能否跨任务、跨模型迁移 |

这里是**研究联系与候选实验**，不是上述生物机制已在大模型中获得普遍验证的结论。例如，CBP 的单元更新有结构更新的启发，但其随机重置并不等同于真实神经发生；“快慢记忆”与脑的互补学习系统也不是一一对应关系。

## 5. 重点：如何读“大模型可塑性”论文

### 5.1 三类实验要分开

| 类型 | 哪些东西在更新？ | 什么结果才支持相应主张？ | 常见误读 |
|---|---|---|---|
| 持续预训练、顺序 SFT/后训练 | 主干参数或长期保存的 adapter | 随训练历史增长，固定预算下仍能学会新分布，同时保持可接受的旧能力 | 只报告某一次微调成绩，就宣称解决长期可塑性丧失 |
| 测试时训练、快速神经记忆 | 序列内的可学习状态或记忆模块，有时也更新部分模型参数 | 在相同上下文、计算与记忆预算下，更快适应和更好检索；说明是否跨序列保留更新 | 将更好的长上下文结果等同于主干网络长期不会失去可塑性 |
| 普通上下文学习、KV cache、外部检索 | 通常只改变上下文或外部状态，基础参数固定 | 提示/检索条件下行为适应 | 将一次推理中的适应直接当作突触权重更新或永久知识吸收 |

### 5.2 目前最有价值的连接

**预训练质量与后续可训练性可能不是同一目标。** 直接研究语言模型的工作开始表明，最优预训练验证损失对应的设置，未必带来最优后训练表现。因此，选择 checkpoint 或正则化强度时，可以把后续任务的学习效率纳入评价，而不是只按预训练损失排序。

**多时间尺度架构提供了放置可塑性的位置。** TTT、Memory Mosaics、Titans、Nested Learning、MIRAS 等工作可用于思考：快速记忆应写在哪里，写入速度如何控制，什么信息值得整合进长期参数。对这类工作，应同时检查其状态是否会重置、旧知识是否保留、更新成本与实际模型规模。

**生物合理性与工程有效性是两个评价维度。** 能用局部信号实现某种更新，对神经科学和低功耗硬件有意义；但用于大模型时，还需要证明并行训练效率、稳定性和总体成本。反过来，大模型中出现 Hebbian 形式的更新，也不能据此唯一认定其机制与生物相同。

### 5.3 几组值得精读对照的结论

**A01（Nature 2024）与 A07（SNR）：从发现问题到决定何时重置。** 前者通过长任务序列明确展示丧失学习能力，并以低效用单元的持续更新维持表征多样性；后者将重置触发条件改为统计检验。这一演进有助于提出可复现实验：能否在相同重置预算下，更精确地区分暂时低激活与已经失去作用的单元？需要注意，Nature 文章未实验验证大模型，SNR 的最大模型也约为 5M 参数。

**A04（Hare & Tortoise）、B08（iTDS）与 C06（Nested Learning）：不同的慢变量，可能服务于不同目标。** Hare & Tortoise 的慢变量是权重的移动平均；iTDS 的慢变量追踪网络输出；Nested Learning 则组织多个不同更新频率的优化过程。它们都使用多个时间尺度，但不能据此认定机制等价。比较时应说明慢变量储存什么、何时更新、如何影响快变量。

**B01（LPL）与 B03（HLOP）：局部可塑性既能形成表征，也能保护已有表征。** LPL 关注如何在深层感觉网络中形成不变表征；HLOP 用 Hebbian/anti-Hebbian 侧向学习实现投影，减少新任务干扰旧任务。它们适合作为生物机制连接工程算法的两篇入口，但应分别评价表征质量、新任务适应和旧任务保持。

**C02（语言模型 weight decay）应作为大模型方向的优先读物。** 论文控制预训练 weight decay，并测量后续 SFT 表现，因而比只报告基础模型 loss 更直接回答“能否继续学习”。实验包括 Llama-2 风格 0.5B/1B/4B 和 OLMo-2 1.5B 模型；后者在文中用“1B”命名。20/140 tokens-per-parameter 的设置覆盖数学/推理、理解常识与安全 SFT。更强衰减并非越大越好；作者也明确表示表示线性可分性、attention 秩等机制解释是相关性分析，尚未建立各中介机制的因果链。[全文及局限](https://arxiv.org/html/2602.11137v2)

**C04–C07 提供多时间尺度记忆的工程路径，但证据目标不同。** TTT 更新序列内的模型状态；Memory Mosaics at scale 将关联记忆推进到 10B 规模；Nested Learning 与 MIRAS 将更新规则和记忆保持纳入架构描述。这些结果值得与长期可塑性联系，但只有再增加跨任务、跨时间的适应实验，才能判断它们是否减轻主干参数的可塑性衰退。

### 5.4 两类容易产生误读的“矛盾”

**归一化到底有没有帮助？** Nature 2024 在其部分设置中报告某些常见归一化方法未能改善、甚至加剧损失；PLASTIC、PPO 研究及 CoLLAs 的机制分析则显示 LayerNorm 在相应设置中有效。归一化种类、优化器、网络位置和任务流都不同，不能概括成“归一化总有害”或“LayerNorm 已解决可塑性”。应比较具体实验条件。

**低秩到底有害还是有益？** A08/A09/A11/A12 涉及 NTK、冗余表征、Jacobian 或 Hessian 等不同对象；C02 中更好的微调表现却可伴随 attention 矩阵秩降低。不同矩阵的秩、静态任务压缩和新任务学习需求并不等价。阅读时应先写明“哪一个矩阵、在哪个输入分布、用什么秩定义”，再讨论因果关系。


## 6. 博客、评论与其他阅读材料

| 资源、作者及日期 | 建议用途 |
|---|---|
| [Switching between tasks can cause AI to lose the ability to learn](https://www.nature.com/articles/d41586-024-02525-z)<br>Clare Lyle, Razvan Pascanu；2024-08-21；Nature News & Views 632, 745–747 | 以Dohare等Nature论文为中心，解释顺序学习下人工网络为何可能失去学习新技能的能力，并提醒生物/人工网络类比并不精确。 |
| [AI can’t learn new things forever — an algorithm can fix that](https://www.nature.com/articles/d41586-024-02756-0)<br>Benjamin Thompson, Nick Petrić Howe；2024-08-21；Nature Podcast | 00:46–08:55主题为Old AIs can’t learn new tricks，通俗介绍重置部分低利用神经元、保持持续学习的思路。 |
| [Introducing Nested Learning: A new ML paradigm for continual learning](https://research.google/blog/introducing-nested-learning-a-new-ml-paradigm-for-continual-learning/)<br>Ali Behrouz, Vahab Mirrokni；2025-11-07；Google Research Blog | 用多层嵌套优化与不同更新频率的记忆，解释架构、优化器、上下文学习与持续学习的联系；介绍Hope。 |
| [Titans + MIRAS: Helping AI have long-term memory](https://research.google/blog/titans-miras-helping-ai-have-long-term-memory/)<br>Ali Behrouz, Meisam Razaviyayn, Vahab Mirrokni；2025-12-04；Google Research Blog | 介绍测试时神经记忆更新、梯度作为surprise、动量与遗忘门，并将MIRAS分为记忆架构、内部目标、保持正则和更新算法四个设计因素。 |

Nature News & Views 的全文有订阅限制，本次核验公开导语与参考文献；Podcast 核验节目说明，未把音频视为已逐字审阅。Google Research 两篇是作者解读，适合建立直觉；结论和性能比较仍应返回正式论文。

**复现入口：** [Nature/CBP 官方代码](https://github.com/shibhansh/loss-of-plasticity)、[HLOP-SNN](https://github.com/pkuxmq/HLOP-SNN)、[TTT PyTorch 阅读实现](https://github.com/test-time-training/ttt-lm-pytorch)、[TTT JAX 训练实现](https://github.com/test-time-training/ttt-lm-jax)。TTT 的纯 PyTorch 版本适合理解算法，仓库不建议用它复现论文训练速度。

## 7. 可进一步开展的研究问题

以下是基于文献交叉比较提出的研究建议，不是原论文已经证实的结论。

**方向一：统一测量“记住旧知识”和“学会新知识”。** 选取同一初始化和任务序列，分别比较普通微调、权重衰减/归一化、单元或分支更新、adapter 方法；在多个历史 checkpoint 上测新任务学习曲线，并同步测旧任务表现。这样能区分“保住了旧知识”与“网络仍然容易学习”。

**方向二：把元可塑性做成可解释的更新控制器。** 以局部活动、梯度统计、参数尺度或任务变化信号控制更新强度；先验证该控制器是否优于固定超参数，再研究它与慢速反馈、主动遗忘的联系。注意用随机门控和普通学习率调度做对照，避免收益仅来自增加参数或调参预算。

**方向三：测试快记忆是否保护慢参数的长期可塑性。** 在同一语言模型上比较无快速记忆、只保留外部记忆、TTT/可学习记忆三种设置，并采用相同的主干或 adapter 长期更新安排，控制总数据与计算预算。以清空快速记忆后的新领域学习曲线为主要结果，同时测旧能力；参数漂移仅作辅助描述。若某方案冻结主干，应单列为冻结基线，不能由零漂移推断快记忆保护了慢参数的可塑性。这个实验能连接生物快慢学习与大模型 loss of plasticity 两条文献。

**方向四：研究重置的粒度与知识代价。** 单元重置、低秩分支更新和整层重置的破坏程度不同。对语言模型应先从局部 MLP/adapter 开始，并同时评估语言建模、领域适应和旧能力保持，避免直接把小型 RL 网络的经验外推到整个预训练模型。

### 最小评测建议

固定任务分布与更新预算 K，在 checkpoint 副本上进行独立适应测试，对历史网络和新初始化/指定参考 checkpoint 使用相同样本顺序、batch size、更新参数范围和学习率协议。明确优化器状态的处理方式；必要时分别比较保留和重置 Adam 等优化器状态的结果。可以报告：

\[
G_t(K)=L_t\big(U_t^K(\theta_t)\big)-L_t\big(U_t^K(\theta_{\mathrm{ref}})\big).
\]

其中，\(U_t^K\) 表示对任务 t 更新 K 步，\(\theta_t\) 为当前历史网络，\(\theta_{\mathrm{ref}}\) 为明确声明的参考。正值表示在这个任务和预算下，历史网络的适应后损失更高；它只是一个**建议的比较指标**，不是统一公认的可塑性定义。初始损失、任务迁移、参数规模与已有知识均影响解释，应同时给出完整学习曲线和多个预算点。对预训练大模型，常用相同基础 checkpoint 作参考；若使用随机初始化，必须说明两者已有知识不同。

训练损失与独立验证损失应分别计算，以区分拟合困难和泛化下降；跨架构比较还应匹配或同时报告 FLOPs、token 数和存储开销。至少同时报告新任务学习速度/最终表现、旧任务保持、总计算与存储成本。休眠率、表征秩、权重范数、梯度或谱统计作为辅助诊断。强化学习还应控制探索和数据分布变化的混杂；仅观察回报下降，不能唯一归因于网络失去可塑性。

## 8. 建议阅读顺序

建议先读以下 8 篇，再按研究问题展开：

1. **A01，Nature 2024**：建立可塑性丧失的定义、实验设计和 CBP 基线。
2. **A03，PLASTIC**：理解输入变化与目标变化，以及组合干预。
3. **A04，Hare & Tortoise**：把可训练性与泛化分开，理解快慢网络。
4. **B01，LPL / Nature Neuroscience 2023**：进入局部 Hebbian + 预测型可塑性。
5. **B03，HLOP / ICLR 2024**：理解局部学习如何实现保护旧知识的投影。
6. **C02，Weight Decay / ICML 2026**：看直接的语言模型后续适应证据。
7. **C04，TTT / ICML 2025**：理解测试时可学习状态与基础参数的区别。
8. **C06，Nested Learning / NeurIPS 2025**：比较多时间尺度学习与持续记忆设计。

若偏理论，随后读 **A09、A11、A12、A13、B05**；若偏生物规则发现，读 **B06、B07** 及扩展条目 *Model Based Inference of Synaptic Plasticity Rules*；若准备做大模型实验，优先补 **C03、C05、C07**，并将它们与直接研究长期衰退的预印本对照。


## 9. 时间窗外的奠基工作与发表状态提醒

两篇发表于 **2023 年 7 月** 的重要论文位于严格三年时间窗之外，建议作为背景补读，不计入本次 50 篇窗内论文：

- Clare Lyle 等，**[Understanding Plasticity in Neural Networks](https://proceedings.mlr.press/v202/lyle23b.html)**，ICML 2023。为理解训练动态与可塑性提供早期系统分析。
- Ghada Sokar 等，**[The Dormant Neuron Phenomenon in Deep Reinforcement Learning](https://proceedings.mlr.press/v202/sokar23a.html)**，ICML 2023。提出 ReDo，是休眠神经元与重置方法的重要背景。

**需要纠正的常见引用方式：**

- *Maintaining Plasticity in Continual Learning via Regenerative Regularization*（L2 Init）和 *Disentangling the Causes of Plasticity Loss in Neural Networks* 均应标为 **CoLLAs 2024，论文集 2025 年出版**，不能标成 ICLR/ICML 2024。正式页面分别为 [Kumar 等](https://proceedings.mlr.press/v274/kumar25a.html) 和 [Lyle 等](https://proceedings.mlr.press/v274/lyle25a.html)。
- TTT 的 arXiv 首发在 2024 年，但本调研引用正式 **ICML 2025** 版本；MIRAS 的预印本在 2025 年，但正式归属是 **ICLR 2026**。
- *[Can Scale Save Us From Plasticity Loss in Large Language Models?](https://arxiv.org/abs/2606.24752)* 是 **2026-06-23 的预印本**，本次未核验到主会录用。其实验为 **5M–314M 非嵌入参数** 的 GPT 式模型，研究多语言训练及保留的越南语探测任务。结果支持规模在该范围内延缓而未消除可塑性下降；不能外推为已经证明前沿数十/上百 B 模型的结局。
- 同一研究可能有早期拒稿、workshop 和最终主会版本；应引用最终正式条目。本调研不以“出现在 OpenReview”单独证明它属于顶会主会。


## 10. 配套资料与核验范围

- `可塑性文献清单.csv`：含主题、作者、年份、场所、发表状态、原文链接、主要发现、任务与局限，适合筛选阅读。
- `可塑性参考文献.bib`：论文及选定网络资源的引用条目；依据已核验元数据生成，未补造缺失的 DOI 或页码。
- `research_sources/`：本次检索保留的部分公开页面文本、元数据和核验笔记。它是工作记录，不是完整全文数据库；论文原文仍以外部链接为准。

对部分付费期刊条目，本调研使用公开摘要、图注、数据/代码说明及可获得的作者版本。未做全文精读的条目不提炼精确性能百分比，也不声称已复现实验。对会议条目，正式收录状态与论文科学结论的可靠性是两件事；尤其对最新工作，应继续检查独立复现和更长时间尺度的实验。
