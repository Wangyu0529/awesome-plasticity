# awesome-plasticity

[English](#english) · [中文说明](#中文说明)

## English

A curated, structured bibliography on **plasticity** across artificial neural networks, neuroscience, continual learning, and large language models. The collection currently includes **50 papers**, **4 commentary resources**, and **2 code resources**.

### News

- **2026-10-01** — Public release of `awesome-plasticity`.
- **2026-10-01** — Initial collection organized into plasticity loss and recovery, neuroscience-inspired learning, language-model plasticity, and related resources.
- **2026-10-01** — Paper Lists reorganized into a two-level thematic taxonomy; opaque internal record keys are hidden from the reader-facing index.

### Contents

<!-- BEGIN: GENERATED CONTENTS -->

- [Paper Lists](#paper-lists): 50 papers and 6 related resources.
  - [Continual Learning and Plasticity Loss](#continual-learning-and-plasticity-loss) (26)
    - [Problem Definition and Diagnostics](#problem-definition-and-diagnostics) (8)
    - [Resets, Regeneration, and Regularization](#resets-regeneration-and-regularization) (11)
    - [Dynamics, Spectral Structure, and Theory](#dynamics-spectral-structure-and-theory) (7)
  - [Neuroscience-Inspired Plasticity](#neuroscience-inspired-plasticity) (13)
    - [Hebbian, Predictive, and Synaptic Rules](#hebbian-predictive-and-synaptic-rules) (9)
    - [Local Learning, Credit Assignment, and SNNs](#local-learning-credit-assignment-and-snns) (4)
  - [Language Models, Memory, and Adaptation](#language-models-memory-and-adaptation) (11)
    - [Language-Model Plasticity and Post-Training](#language-model-plasticity-and-post-training) (4)
    - [Test-Time Learning and Long-Term Memory](#test-time-learning-and-long-term-memory) (6)
    - [Functional Adaptation and Model Geometry](#functional-adaptation-and-model-geometry) (1)
  - [Reviews, Commentary, and Code](#reviews-commentary-and-code) (6)
    - [Commentary and Podcasts](#commentary-and-podcasts) (4)
    - [Official Implementations](#official-implementations) (2)
- [Research notes](docs/review.md): concepts, comparisons, limitations, and a suggested reading order.
- [Structured catalog](data/catalog.csv): filterable metadata for all records.
- [BibTeX](references/plasticity.bib): generated citation entries.
- [One-record-per-paper data](data/records/): editable source records.
- [Maintenance guide](CONTRIBUTING.md): add, update, and remove entries.

<!-- END: GENERATED CONTENTS -->

### Paper Lists

<!-- BEGIN: GENERATED PAPER LISTS -->

The lists below are generated from `data/records/*.json`.

#### Continual Learning and Plasticity Loss

26 items

##### Problem Definition and Diagnostics

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Loss of plasticity in deep continual learning](https://www.nature.com/articles/s41586-024-07711-7) | Journal paper | 2024 | Nature |
| [A Study of Plasticity Loss in On-Policy Deep Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2024/hash/ce7984e36d58659211a8dc7d5457cd6f-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Overestimation, Overfitting, and Plasticity in Actor-Critic: the Bitter Lesson of Reinforcement Learning](https://proceedings.mlr.press/v235/nauman24a.html) | Conference paper | 2024 | ICML 2024 |
| [Revisiting Plasticity in Visual Reinforcement Learning: Data, Modules and Training Stages](https://openreview.net/forum?id=0aR1s9YxoL) | Conference paper | 2024 | ICLR 2024 poster |
| [The Dormant Neuron Phenomenon in Multi-Agent Reinforcement Learning Value Factorization](https://proceedings.neurips.cc/paper_files/paper/2024/hash/3eec5006051d9544e717067de3220198-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Disentangling the Causes of Plasticity Loss in Neural Networks](https://proceedings.mlr.press/v274/lyle25a.html) | Workshop / field-conference paper | 2025 | CoLLAs 2024 (proceedings published in 2025) |
| [Plasticity as the Mirror of Empowerment](https://openreview.net/forum?id=eOZFqyE9Ok) | Conference paper | 2025 | NeurIPS 2025 Spotlight |
| [The Dual Nature of Plasticity Loss in Deep Continual Learning: Dissection and Mitigation](https://openreview.net/forum?id=vvD0Bre3Dk) | Conference paper | 2025 | NeurIPS 2025 |

##### Resets, Regeneration, and Regularization

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Deep Reinforcement Learning with Plasticity Injection](https://proceedings.neurips.cc/paper_files/paper/2023/hash/75101364dc3aa7772d27528ea504472b-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [PLASTIC: Improving Input and Label Plasticity for Sample Efficient Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2023/hash/c464fc4516aca4e68f2a14e67c6f0402-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Slow and Steady Wins the Race: Maintaining Plasticity with Hare and Tortoise Networks](https://proceedings.mlr.press/v235/lee24d.html) | Conference paper | 2024 | ICML 2024 |
| [DASH: Warm-Starting Neural Network Training in Stationary Settings without Loss of Plasticity](https://proceedings.neurips.cc/paper_files/paper/2024/hash/4c5ce1fc8895076f49935951a630be5c-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Self-Normalized Resets for Plasticity in Continual Learning](https://openreview.net/forum?id=G82uQztzxl) | Conference paper | 2025 | ICLR 2025 Poster |
| [Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn](https://proceedings.mlr.press/v267/tang25g.html) | Conference paper | 2025 | ICML 2025 |
| [Activation by Interval-wise Dropout: A Simple Way to Prevent Neural Networks from Plasticity Loss](https://proceedings.mlr.press/v267/park25b.html) | Conference paper | 2025 | ICML 2025 |
| [Maintaining Plasticity in Continual Learning via Regenerative Regularization](https://proceedings.mlr.press/v274/kumar25a.html) | Workshop / field-conference paper | 2025 | CoLLAs 2024 (proceedings published in 2025) |
| [Stay Hungry, Keep Learning: Sustainable Plasticity for Deep Reinforcement Learning](https://proceedings.mlr.press/v267/zhou25am.html) | Conference paper | 2025 | ICML 2025 |
| [Activation Function Design Sustains Plasticity in Continual Learning](https://openreview.net/forum?id=XZf6wObHX4) | Conference paper | 2026 | ICLR 2026 Poster |
| [Mitigating Plasticity Loss through Architectural Design in Continual Learning](https://openreview.net/forum?id=pAhGjPOlwy) | Conference paper | 2026 | ICML 2026 |

##### Dynamics, Spectral Structure, and Theory

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Barriers for Learning in an Evolving World:  Mathematical Understanding of Loss of Plasticity](https://openreview.net/forum?id=g6kof5fSba) | Conference paper | 2026 | ICLR 2026 Poster |
| [The Rank and Gradient Lost in Non-stationarity: Sample Weight Decay for Mitigating Plasticity Loss in Reinforcement Learning](https://openreview.net/forum?id=5DpzzTPnJZ) | Conference paper | 2026 | ICLR 2026 Poster |
| [Preserving Plasticity in Continual Learning via Dynamical Isometry](https://openreview.net/forum?id=vJCOWSkMuq) | Conference paper | 2026 | ICML 2026 |
| [Spectral Collapse Drives Loss of Plasticity in Deep Continual Learning](https://openreview.net/forum?id=O6rHSkpYJU) | Conference paper | 2026 | ICML 2026 |
| [Local Redundancy: An Information-Theoretic Measure of Plasticity from Synthetic Memorization](https://openreview.net/forum?id=ucbH88BgIk) | Conference paper | 2026 | ICML 2026 Spotlight |
| [Plasticity Activation via Polar Operator: A Plug-in Method for Balancing Stability and Plasticity](https://openreview.net/forum?id=b7P2WegaBY) | Conference paper | 2026 | ICML 2026 |
| [SPHERE: Mitigating the Loss of Spectral Plasticity in Mixture-of-Experts for Deep Reinforcement Learning](https://openreview.net/forum?id=hXyv6xeHkO) | Conference paper | 2026 | ICML 2026 |

#### Neuroscience-Inspired Plasticity

13 items

##### Hebbian, Predictive, and Synaptic Rules

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [The combination of Hebbian and predictive plasticity learns invariant object representations in deep sensory networks](https://www.nature.com/articles/s41593-023-01460-y) | Journal paper | 2023 | Nature Neuroscience |
| [Incorporating neuro-inspired adaptability for continual learning in artificial intelligence](https://www.nature.com/articles/s42256-023-00747-w) | Journal paper | 2023 | Nature Machine Intelligence |
| [Synaptic Weight Distributions Depend on the Geometry of Plasticity](https://openreview.net/forum?id=x5txICnnjC) | Conference paper | 2024 | ICLR 2024 spotlight |
| [Learning the Plasticity: Plasticity-Driven Learning Framework in Spiking Neural Networks](https://openreview.net/forum?id=fllsm01JWS) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Discovering heterogeneous synaptic plasticity rules via large-scale neural evolution](https://openreview.net/forum?id=hJBPMSUNUG) | Conference paper | 2026 | ICLR 2026 Poster |
| [Intrinsic stabilization of synaptic plasticity improves learning and robustness in artificial neural networks](https://www.nature.com/articles/s41467-026-70920-3) | Journal paper | 2026 | Nature Communications |
| [Model Based Inference of Synaptic Plasticity Rules](https://openreview.net/forum?id=rI80PHlnFm) | Conference paper | 2024 | NeurIPS 2024 poster |
| [Spike-timing-dependent Hebbian learning as noisy gradient descent](https://openreview.net/forum?id=YTbLri0siT) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Ubiquity of Emergent Hebbian Dynamics in Regularized Learning](https://openreview.net/forum?id=fSRmJOzMA1) | Conference paper | 2026 | ICML 2026 regular |

##### Local Learning, Credit Assignment, and SNNs

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Hebbian Learning based Orthogonal Projection for Continual Learning of Spiking Neural Networks](https://openreview.net/forum?id=MeB86edZ1P) | Conference paper | 2024 | ICLR 2024 poster |
| [Learning efficient backprojections across cortical hierarchies in real time](https://www.nature.com/articles/s42256-024-00845-3) | Journal paper | 2024 | Nature Machine Intelligence |
| [Learning Successor Features with Distributed Hebbian Temporal Memory](https://openreview.net/forum?id=wYJII5BRYU) | Conference paper | 2025 | ICLR 2025 Poster |
| [Spike-based alignment learning solves the weight transport problem](https://www.nature.com/articles/s41467-026-74460-8) | Journal paper | 2026 | Nature Communications |

#### Language Models, Memory, and Adaptation

11 items

##### Language-Model Plasticity and Post-Training

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Improving Language Plasticity via Pretraining with Active Forgetting](https://proceedings.neurips.cc/paper_files/paper/2023/hash/6450ea28ebbc8437bc38775157818172-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Weight Decay Improves Language Model Plasticity](https://openreview.net/forum?id=zMO9H4hLyR) | Conference paper | 2026 | ICML 2026 |
| [On the Plasticity and Stability for Post-Training Large Language Models](https://openreview.net/forum?id=lOR6zI5peb) | Conference paper | 2026 | ICML 2026 |
| [Can Scale Save Us From Plasticity Loss in Large Language Models?](https://arxiv.org/abs/2606.24752) | Preprint | 2026 | arXiv:2606.24752 |

##### Test-Time Learning and Long-Term Memory

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Learning to (Learn at Test Time): RNNs with Expressive Hidden States](https://openreview.net/forum?id=wXfuOj9C7L) | Conference paper | 2025 | ICML 2025 Spotlight |
| [Memory Mosaics at scale](https://openreview.net/forum?id=IfD2MKTmWv) | Conference paper | 2025 | NeurIPS 2025 Oral |
| [Nested Learning: The Illusion of Deep Learning Architectures](https://openreview.net/forum?id=nbMeRvNb7A) | Conference paper | 2025 | NeurIPS 2025 Poster |
| [It's All Connected: A Journey Through Test-Time Memorization, Attentional Bias, Retention, and Online Optimization](https://openreview.net/forum?id=gZyEJ2kMow) | Conference paper | 2026 | ICLR 2026 Poster |
| [Memory Mosaics](https://openreview.net/forum?id=IiagjrJNwF) | Conference paper | 2025 | ICLR 2025 Poster |
| [Titans: Learning to Memorize at Test Time](https://openreview.net/forum?id=8GjSf9Rh7Z) | Conference paper | 2025 | NeurIPS 2025 Poster |

##### Functional Adaptation and Model Geometry

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Engineering flexible machine learning systems by traversing functionally invariant paths](https://www.nature.com/articles/s42256-024-00902-x) | Journal paper | 2024 | Nature Machine Intelligence |

#### Reviews, Commentary, and Code

6 items

##### Commentary and Podcasts

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Switching between tasks can cause AI to lose the ability to learn](https://www.nature.com/articles/d41586-024-02525-z) | Commentary / podcast | 2024 | Nature News & Views 632, 745–747 |
| [AI can’t learn new things forever — an algorithm can fix that](https://www.nature.com/articles/d41586-024-02756-0) | Commentary / podcast | 2024 | Nature Podcast |
| [Introducing Nested Learning: A new ML paradigm for continual learning](https://research.google/blog/introducing-nested-learning-a-new-ml-paradigm-for-continual-learning/) | Commentary / podcast | 2025 | Google Research Blog |
| [Titans + MIRAS: Helping AI have long-term memory](https://research.google/blog/titans-miras-helping-ai-have-long-term-memory/) | Commentary / podcast | 2025 | Google Research Blog |

##### Official Implementations

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Loss of Plasticity in Deep Continual Learning — official code](https://github.com/shibhansh/loss-of-plasticity) | Code | 2024 | GitHub / Nature 2024 companion code |
| [TTT official PyTorch implementation](https://github.com/test-time-training/ttt-lm-pytorch) | Code | 2024 | GitHub / ICML 2025 companion code |

<!-- END: GENERATED PAPER LISTS -->

### Research notes and data

- [Chinese research review](docs/review.md): concepts, comparisons, limitations, and a suggested reading order.
- [Structured catalog](data/catalog.csv): filterable CSV containing metadata, findings, experimental settings, and limitations.
- [BibTeX](references/plasticity.bib): generated citation entries.
- [One-record-per-paper data](data/records/): the editable source for each paper or resource.
- [Maintenance guide](CONTRIBUTING.md): how to add, update, or remove entries.

The catalog distinguishes formal publication year from preprint-first-posting dates. Each record links to the publisher, conference, OpenReview, arXiv, or official code page when available. The collection is selective rather than an exhaustive systematic review.

## 中文说明

整理与可塑性（plasticity）相关的论文、预印本、解读和代码资源，重点覆盖：

- 神经网络中的可塑性
- 神经科学中的可塑性
- 大模型中的可塑性

文献年份按正式发表场所记录；arXiv 首发日期单独保留。论文结论、发表状态和代码链接应以每条记录中的来源链接为准。欢迎通过 Issue 或 Pull Request 提交补充和勘误。

中文调研全文见 [docs/review.md](docs/review.md)，结构化数据见 [data/catalog.csv](data/catalog.csv)。
