# awesome-plasticity

[English](#english) · [中文说明](#中文说明)

## English

A curated, structured bibliography on **plasticity** across artificial neural networks, neuroscience, continual learning, and large language models. The collection currently includes **50 papers**, **4 commentary resources**, and **2 code resources**.

### News

- **2026-10-01** — Public release of `awesome-plasticity`.
- **2026-10-01** — Initial collection organized into plasticity loss and recovery, neuroscience-inspired learning, language-model plasticity, and related resources.
- **2026-10-01** — Paper Lists reorganized into a two-level, multi-angle taxonomy; opaque internal record keys are hidden from the reader-facing index.

### Contents

<!-- BEGIN: GENERATED CONTENTS -->

- [Paper Lists](#paper-lists): 50 papers and 6 related resources.
  - [Problem Definition](#problem-definition) (23)
    - [Definitions and Distinctions](#definitions-and-distinctions) (5)
    - [Metrics and Evaluation](#metrics-and-evaluation) (5)
    - [Mechanistic and Mathematical Accounts](#mechanistic-and-mathematical-accounts) (6)
    - [Biological Concepts of Plasticity](#biological-concepts-of-plasticity) (4)
    - [Stability, Forgetting, and Memory](#stability-forgetting-and-memory) (3)
  - [Research Methods](#research-methods) (36)
    - [Resets, Regeneration, and Active Forgetting](#resets-regeneration-and-active-forgetting) (7)
    - [Regularization and Optimization](#regularization-and-optimization) (8)
    - [Local Learning and Credit Assignment](#local-learning-and-credit-assignment) (6)
    - [Synaptic Rule Discovery](#synaptic-rule-discovery) (3)
    - [Memory Architectures and Test-Time Learning](#memory-architectures-and-test-time-learning) (6)
    - [Functional Geometry and Stabilization](#functional-geometry-and-stabilization) (6)
  - [Application Scenarios](#application-scenarios) (50)
    - [Continual Reinforcement Learning](#continual-reinforcement-learning) (14)
    - [Continual Vision and Supervised Learning](#continual-vision-and-supervised-learning) (12)
    - [Spiking and Biological Systems](#spiking-and-biological-systems) (13)
    - [Language Models and Post-Training](#language-models-and-post-training) (5)
    - [Long-Context and Sequence Memory](#long-context-and-sequence-memory) (6)
    - [Multi-Agent and Embodied Learning](#multi-agent-and-embodied-learning) (2)
  - [Reviews](#reviews) (4)
    - [Research Commentary and Podcasts](#research-commentary-and-podcasts) (2)
    - [Author Explanations and Blog Posts](#author-explanations-and-blog-posts) (2)
  - [Community and Tools](#community-and-tools) (2)
    - [Continual-Learning Implementations](#continual-learning-implementations) (1)
    - [Test-Time Learning Implementations](#test-time-learning-implementations) (1)
- [Research notes](docs/review.md): concepts, comparisons, limitations, and a suggested reading order.
- [Structured catalog](data/catalog.csv): filterable metadata for all records.
- [BibTeX](references/plasticity.bib): generated citation entries.
- [One-record-per-paper data](data/records/): editable source records.
- [Maintenance guide](CONTRIBUTING.md): add, update, and remove entries.

<!-- END: GENERATED CONTENTS -->

### Paper Lists

<!-- BEGIN: GENERATED PAPER LISTS -->

The lists below are generated from `data/records/*.json`. Cross-indexed papers may appear in more than one section.

#### Problem Definition

23 unique records

##### Definitions and Distinctions

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Loss of plasticity in deep continual learning](https://www.nature.com/articles/s41586-024-07711-7) | Journal paper | 2024 | Nature |
| [A Study of Plasticity Loss in On-Policy Deep Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2024/hash/ce7984e36d58659211a8dc7d5457cd6f-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Disentangling the Causes of Plasticity Loss in Neural Networks](https://proceedings.mlr.press/v274/lyle25a.html) | Workshop / field-conference paper | 2025 | CoLLAs 2024 (proceedings published in 2025) |
| [Plasticity as the Mirror of Empowerment](https://openreview.net/forum?id=eOZFqyE9Ok) | Conference paper | 2025 | NeurIPS 2025 Spotlight |
| [The Dual Nature of Plasticity Loss in Deep Continual Learning: Dissection and Mitigation](https://openreview.net/forum?id=vvD0Bre3Dk) | Conference paper | 2025 | NeurIPS 2025 |

##### Metrics and Evaluation

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn](https://proceedings.mlr.press/v267/tang25g.html) | Conference paper | 2025 | ICML 2025 |
| [Local Redundancy: An Information-Theoretic Measure of Plasticity from Synthetic Memorization](https://openreview.net/forum?id=ucbH88BgIk) | Conference paper | 2026 | ICML 2026 Spotlight |
| [Overestimation, Overfitting, and Plasticity in Actor-Critic: the Bitter Lesson of Reinforcement Learning](https://proceedings.mlr.press/v235/nauman24a.html) | Conference paper | 2024 | ICML 2024 |
| [Revisiting Plasticity in Visual Reinforcement Learning: Data, Modules and Training Stages](https://openreview.net/forum?id=0aR1s9YxoL) | Conference paper | 2024 | ICLR 2024 poster |
| [The Dormant Neuron Phenomenon in Multi-Agent Reinforcement Learning Value Factorization](https://proceedings.neurips.cc/paper_files/paper/2024/hash/3eec5006051d9544e717067de3220198-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |

##### Mechanistic and Mathematical Accounts

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Barriers for Learning in an Evolving World:  Mathematical Understanding of Loss of Plasticity](https://openreview.net/forum?id=g6kof5fSba) | Conference paper | 2026 | ICLR 2026 Poster |
| [The Rank and Gradient Lost in Non-stationarity: Sample Weight Decay for Mitigating Plasticity Loss in Reinforcement Learning](https://openreview.net/forum?id=5DpzzTPnJZ) | Conference paper | 2026 | ICLR 2026 Poster |
| [Preserving Plasticity in Continual Learning via Dynamical Isometry](https://openreview.net/forum?id=vJCOWSkMuq) | Conference paper | 2026 | ICML 2026 |
| [Spectral Collapse Drives Loss of Plasticity in Deep Continual Learning](https://openreview.net/forum?id=O6rHSkpYJU) | Conference paper | 2026 | ICML 2026 |
| [Plasticity Activation via Polar Operator: A Plug-in Method for Balancing Stability and Plasticity](https://openreview.net/forum?id=b7P2WegaBY) | Conference paper | 2026 | ICML 2026 |
| [SPHERE: Mitigating the Loss of Spectral Plasticity in Mixture-of-Experts for Deep Reinforcement Learning](https://openreview.net/forum?id=hXyv6xeHkO) | Conference paper | 2026 | ICML 2026 |

##### Biological Concepts of Plasticity

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [The combination of Hebbian and predictive plasticity learns invariant object representations in deep sensory networks](https://www.nature.com/articles/s41593-023-01460-y) | Journal paper | 2023 | Nature Neuroscience |
| [Synaptic Weight Distributions Depend on the Geometry of Plasticity](https://openreview.net/forum?id=x5txICnnjC) | Conference paper | 2024 | ICLR 2024 spotlight |
| [Spike-timing-dependent Hebbian learning as noisy gradient descent](https://openreview.net/forum?id=YTbLri0siT) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Ubiquity of Emergent Hebbian Dynamics in Regularized Learning](https://openreview.net/forum?id=fSRmJOzMA1) | Conference paper | 2026 | ICML 2026 regular |

##### Stability, Forgetting, and Memory

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Weight Decay Improves Language Model Plasticity](https://openreview.net/forum?id=zMO9H4hLyR) | Conference paper | 2026 | ICML 2026 |
| [On the Plasticity and Stability for Post-Training Large Language Models](https://openreview.net/forum?id=lOR6zI5peb) | Conference paper | 2026 | ICML 2026 |
| [Can Scale Save Us From Plasticity Loss in Large Language Models?](https://arxiv.org/abs/2606.24752) | Preprint | 2026 | arXiv:2606.24752 |

#### Research Methods

36 unique records

##### Resets, Regeneration, and Active Forgetting

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Deep Reinforcement Learning with Plasticity Injection](https://proceedings.neurips.cc/paper_files/paper/2023/hash/75101364dc3aa7772d27528ea504472b-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Self-Normalized Resets for Plasticity in Continual Learning](https://openreview.net/forum?id=G82uQztzxl) | Conference paper | 2025 | ICLR 2025 Poster |
| [Incorporating neuro-inspired adaptability for continual learning in artificial intelligence](https://www.nature.com/articles/s42256-023-00747-w) | Journal paper | 2023 | Nature Machine Intelligence |
| [Improving Language Plasticity via Pretraining with Active Forgetting](https://proceedings.neurips.cc/paper_files/paper/2023/hash/6450ea28ebbc8437bc38775157818172-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Activation by Interval-wise Dropout: A Simple Way to Prevent Neural Networks from Plasticity Loss](https://proceedings.mlr.press/v267/park25b.html) | Conference paper | 2025 | ICML 2025 |
| [Maintaining Plasticity in Continual Learning via Regenerative Regularization](https://proceedings.mlr.press/v274/kumar25a.html) | Workshop / field-conference paper | 2025 | CoLLAs 2024 (proceedings published in 2025) |
| [Stay Hungry, Keep Learning: Sustainable Plasticity for Deep Reinforcement Learning](https://proceedings.mlr.press/v267/zhou25am.html) | Conference paper | 2025 | ICML 2025 |

##### Regularization and Optimization

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [PLASTIC: Improving Input and Label Plasticity for Sample Efficient Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2023/hash/c464fc4516aca4e68f2a14e67c6f0402-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Slow and Steady Wins the Race: Maintaining Plasticity with Hare and Tortoise Networks](https://proceedings.mlr.press/v235/lee24d.html) | Conference paper | 2024 | ICML 2024 |
| [DASH: Warm-Starting Neural Network Training in Stationary Settings without Loss of Plasticity](https://proceedings.neurips.cc/paper_files/paper/2024/hash/4c5ce1fc8895076f49935951a630be5c-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn](https://proceedings.mlr.press/v267/tang25g.html) | Conference paper | 2025 | ICML 2025 |
| [The Rank and Gradient Lost in Non-stationarity: Sample Weight Decay for Mitigating Plasticity Loss in Reinforcement Learning](https://openreview.net/forum?id=5DpzzTPnJZ) | Conference paper | 2026 | ICLR 2026 Poster |
| [On the Plasticity and Stability for Post-Training Large Language Models](https://openreview.net/forum?id=lOR6zI5peb) | Conference paper | 2026 | ICML 2026 |
| [Activation Function Design Sustains Plasticity in Continual Learning](https://openreview.net/forum?id=XZf6wObHX4) | Conference paper | 2026 | ICLR 2026 Poster |
| [Mitigating Plasticity Loss through Architectural Design in Continual Learning](https://openreview.net/forum?id=pAhGjPOlwy) | Conference paper | 2026 | ICML 2026 |

##### Local Learning and Credit Assignment

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [The combination of Hebbian and predictive plasticity learns invariant object representations in deep sensory networks](https://www.nature.com/articles/s41593-023-01460-y) | Journal paper | 2023 | Nature Neuroscience |
| [Hebbian Learning based Orthogonal Projection for Continual Learning of Spiking Neural Networks](https://openreview.net/forum?id=MeB86edZ1P) | Conference paper | 2024 | ICLR 2024 poster |
| [Learning efficient backprojections across cortical hierarchies in real time](https://www.nature.com/articles/s42256-024-00845-3) | Journal paper | 2024 | Nature Machine Intelligence |
| [Learning Successor Features with Distributed Hebbian Temporal Memory](https://openreview.net/forum?id=wYJII5BRYU) | Conference paper | 2025 | ICLR 2025 Poster |
| [Spike-timing-dependent Hebbian learning as noisy gradient descent](https://openreview.net/forum?id=YTbLri0siT) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Spike-based alignment learning solves the weight transport problem](https://www.nature.com/articles/s41467-026-74460-8) | Journal paper | 2026 | Nature Communications |

##### Synaptic Rule Discovery

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Learning the Plasticity: Plasticity-Driven Learning Framework in Spiking Neural Networks](https://openreview.net/forum?id=fllsm01JWS) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Discovering heterogeneous synaptic plasticity rules via large-scale neural evolution](https://openreview.net/forum?id=hJBPMSUNUG) | Conference paper | 2026 | ICLR 2026 Poster |
| [Model Based Inference of Synaptic Plasticity Rules](https://openreview.net/forum?id=rI80PHlnFm) | Conference paper | 2024 | NeurIPS 2024 poster |

##### Memory Architectures and Test-Time Learning

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Learning to (Learn at Test Time): RNNs with Expressive Hidden States](https://openreview.net/forum?id=wXfuOj9C7L) | Conference paper | 2025 | ICML 2025 Spotlight |
| [Memory Mosaics at scale](https://openreview.net/forum?id=IfD2MKTmWv) | Conference paper | 2025 | NeurIPS 2025 Oral |
| [Nested Learning: The Illusion of Deep Learning Architectures](https://openreview.net/forum?id=nbMeRvNb7A) | Conference paper | 2025 | NeurIPS 2025 Poster |
| [It's All Connected: A Journey Through Test-Time Memorization, Attentional Bias, Retention, and Online Optimization](https://openreview.net/forum?id=gZyEJ2kMow) | Conference paper | 2026 | ICLR 2026 Poster |
| [Memory Mosaics](https://openreview.net/forum?id=IiagjrJNwF) | Conference paper | 2025 | ICLR 2025 Poster |
| [Titans: Learning to Memorize at Test Time](https://openreview.net/forum?id=8GjSf9Rh7Z) | Conference paper | 2025 | NeurIPS 2025 Poster |

##### Functional Geometry and Stabilization

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Preserving Plasticity in Continual Learning via Dynamical Isometry](https://openreview.net/forum?id=vJCOWSkMuq) | Conference paper | 2026 | ICML 2026 |
| [Synaptic Weight Distributions Depend on the Geometry of Plasticity](https://openreview.net/forum?id=x5txICnnjC) | Conference paper | 2024 | ICLR 2024 spotlight |
| [Intrinsic stabilization of synaptic plasticity improves learning and robustness in artificial neural networks](https://www.nature.com/articles/s41467-026-70920-3) | Journal paper | 2026 | Nature Communications |
| [Engineering flexible machine learning systems by traversing functionally invariant paths](https://www.nature.com/articles/s42256-024-00902-x) | Journal paper | 2024 | Nature Machine Intelligence |
| [Plasticity Activation via Polar Operator: A Plug-in Method for Balancing Stability and Plasticity](https://openreview.net/forum?id=b7P2WegaBY) | Conference paper | 2026 | ICML 2026 |
| [SPHERE: Mitigating the Loss of Spectral Plasticity in Mixture-of-Experts for Deep Reinforcement Learning](https://openreview.net/forum?id=hXyv6xeHkO) | Conference paper | 2026 | ICML 2026 |

#### Application Scenarios

50 unique records

##### Continual Reinforcement Learning

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Deep Reinforcement Learning with Plasticity Injection](https://proceedings.neurips.cc/paper_files/paper/2023/hash/75101364dc3aa7772d27528ea504472b-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [PLASTIC: Improving Input and Label Plasticity for Sample Efficient Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2023/hash/c464fc4516aca4e68f2a14e67c6f0402-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Slow and Steady Wins the Race: Maintaining Plasticity with Hare and Tortoise Networks](https://proceedings.mlr.press/v235/lee24d.html) | Conference paper | 2024 | ICML 2024 |
| [A Study of Plasticity Loss in On-Policy Deep Reinforcement Learning](https://proceedings.neurips.cc/paper_files/paper/2024/hash/ce7984e36d58659211a8dc7d5457cd6f-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn](https://proceedings.mlr.press/v267/tang25g.html) | Conference paper | 2025 | ICML 2025 |
| [The Rank and Gradient Lost in Non-stationarity: Sample Weight Decay for Mitigating Plasticity Loss in Reinforcement Learning](https://openreview.net/forum?id=5DpzzTPnJZ) | Conference paper | 2026 | ICLR 2026 Poster |
| [Overestimation, Overfitting, and Plasticity in Actor-Critic: the Bitter Lesson of Reinforcement Learning](https://proceedings.mlr.press/v235/nauman24a.html) | Conference paper | 2024 | ICML 2024 |
| [Revisiting Plasticity in Visual Reinforcement Learning: Data, Modules and Training Stages](https://openreview.net/forum?id=0aR1s9YxoL) | Conference paper | 2024 | ICLR 2024 poster |
| [The Dormant Neuron Phenomenon in Multi-Agent Reinforcement Learning Value Factorization](https://proceedings.neurips.cc/paper_files/paper/2024/hash/3eec5006051d9544e717067de3220198-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Activation by Interval-wise Dropout: A Simple Way to Prevent Neural Networks from Plasticity Loss](https://proceedings.mlr.press/v267/park25b.html) | Conference paper | 2025 | ICML 2025 |
| [Stay Hungry, Keep Learning: Sustainable Plasticity for Deep Reinforcement Learning](https://proceedings.mlr.press/v267/zhou25am.html) | Conference paper | 2025 | ICML 2025 |
| [Mitigating Plasticity Loss through Architectural Design in Continual Learning](https://openreview.net/forum?id=pAhGjPOlwy) | Conference paper | 2026 | ICML 2026 |
| [Plasticity Activation via Polar Operator: A Plug-in Method for Balancing Stability and Plasticity](https://openreview.net/forum?id=b7P2WegaBY) | Conference paper | 2026 | ICML 2026 |
| [SPHERE: Mitigating the Loss of Spectral Plasticity in Mixture-of-Experts for Deep Reinforcement Learning](https://openreview.net/forum?id=hXyv6xeHkO) | Conference paper | 2026 | ICML 2026 |

##### Continual Vision and Supervised Learning

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Loss of plasticity in deep continual learning](https://www.nature.com/articles/s41586-024-07711-7) | Journal paper | 2024 | Nature |
| [DASH: Warm-Starting Neural Network Training in Stationary Settings without Loss of Plasticity](https://proceedings.neurips.cc/paper_files/paper/2024/hash/4c5ce1fc8895076f49935951a630be5c-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Self-Normalized Resets for Plasticity in Continual Learning](https://openreview.net/forum?id=G82uQztzxl) | Conference paper | 2025 | ICLR 2025 Poster |
| [Barriers for Learning in an Evolving World:  Mathematical Understanding of Loss of Plasticity](https://openreview.net/forum?id=g6kof5fSba) | Conference paper | 2026 | ICLR 2026 Poster |
| [Preserving Plasticity in Continual Learning via Dynamical Isometry](https://openreview.net/forum?id=vJCOWSkMuq) | Conference paper | 2026 | ICML 2026 |
| [Spectral Collapse Drives Loss of Plasticity in Deep Continual Learning](https://openreview.net/forum?id=O6rHSkpYJU) | Conference paper | 2026 | ICML 2026 |
| [Local Redundancy: An Information-Theoretic Measure of Plasticity from Synthetic Memorization](https://openreview.net/forum?id=ucbH88BgIk) | Conference paper | 2026 | ICML 2026 Spotlight |
| [Incorporating neuro-inspired adaptability for continual learning in artificial intelligence](https://www.nature.com/articles/s42256-023-00747-w) | Journal paper | 2023 | Nature Machine Intelligence |
| [Disentangling the Causes of Plasticity Loss in Neural Networks](https://proceedings.mlr.press/v274/lyle25a.html) | Workshop / field-conference paper | 2025 | CoLLAs 2024 (proceedings published in 2025) |
| [Maintaining Plasticity in Continual Learning via Regenerative Regularization](https://proceedings.mlr.press/v274/kumar25a.html) | Workshop / field-conference paper | 2025 | CoLLAs 2024 (proceedings published in 2025) |
| [The Dual Nature of Plasticity Loss in Deep Continual Learning: Dissection and Mitigation](https://openreview.net/forum?id=vvD0Bre3Dk) | Conference paper | 2025 | NeurIPS 2025 |
| [Activation Function Design Sustains Plasticity in Continual Learning](https://openreview.net/forum?id=XZf6wObHX4) | Conference paper | 2026 | ICLR 2026 Poster |

##### Spiking and Biological Systems

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [The combination of Hebbian and predictive plasticity learns invariant object representations in deep sensory networks](https://www.nature.com/articles/s41593-023-01460-y) | Journal paper | 2023 | Nature Neuroscience |
| [Incorporating neuro-inspired adaptability for continual learning in artificial intelligence](https://www.nature.com/articles/s42256-023-00747-w) | Journal paper | 2023 | Nature Machine Intelligence |
| [Hebbian Learning based Orthogonal Projection for Continual Learning of Spiking Neural Networks](https://openreview.net/forum?id=MeB86edZ1P) | Conference paper | 2024 | ICLR 2024 poster |
| [Learning efficient backprojections across cortical hierarchies in real time](https://www.nature.com/articles/s42256-024-00845-3) | Journal paper | 2024 | Nature Machine Intelligence |
| [Synaptic Weight Distributions Depend on the Geometry of Plasticity](https://openreview.net/forum?id=x5txICnnjC) | Conference paper | 2024 | ICLR 2024 spotlight |
| [Learning the Plasticity: Plasticity-Driven Learning Framework in Spiking Neural Networks](https://openreview.net/forum?id=fllsm01JWS) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Discovering heterogeneous synaptic plasticity rules via large-scale neural evolution](https://openreview.net/forum?id=hJBPMSUNUG) | Conference paper | 2026 | ICLR 2026 Poster |
| [Intrinsic stabilization of synaptic plasticity improves learning and robustness in artificial neural networks](https://www.nature.com/articles/s41467-026-70920-3) | Journal paper | 2026 | Nature Communications |
| [Model Based Inference of Synaptic Plasticity Rules](https://openreview.net/forum?id=rI80PHlnFm) | Conference paper | 2024 | NeurIPS 2024 poster |
| [Learning Successor Features with Distributed Hebbian Temporal Memory](https://openreview.net/forum?id=wYJII5BRYU) | Conference paper | 2025 | ICLR 2025 Poster |
| [Spike-timing-dependent Hebbian learning as noisy gradient descent](https://openreview.net/forum?id=YTbLri0siT) | Conference paper | 2025 | NeurIPS 2025 poster |
| [Spike-based alignment learning solves the weight transport problem](https://www.nature.com/articles/s41467-026-74460-8) | Journal paper | 2026 | Nature Communications |
| [Ubiquity of Emergent Hebbian Dynamics in Regularized Learning](https://openreview.net/forum?id=fSRmJOzMA1) | Conference paper | 2026 | ICML 2026 regular |

##### Language Models and Post-Training

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Improving Language Plasticity via Pretraining with Active Forgetting](https://proceedings.neurips.cc/paper_files/paper/2023/hash/6450ea28ebbc8437bc38775157818172-Abstract-Conference.html) | Conference paper | 2023 | NeurIPS 2023 |
| [Weight Decay Improves Language Model Plasticity](https://openreview.net/forum?id=zMO9H4hLyR) | Conference paper | 2026 | ICML 2026 |
| [On the Plasticity and Stability for Post-Training Large Language Models](https://openreview.net/forum?id=lOR6zI5peb) | Conference paper | 2026 | ICML 2026 |
| [Engineering flexible machine learning systems by traversing functionally invariant paths](https://www.nature.com/articles/s42256-024-00902-x) | Journal paper | 2024 | Nature Machine Intelligence |
| [Can Scale Save Us From Plasticity Loss in Large Language Models?](https://arxiv.org/abs/2606.24752) | Preprint | 2026 | arXiv:2606.24752 |

##### Long-Context and Sequence Memory

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Learning to (Learn at Test Time): RNNs with Expressive Hidden States](https://openreview.net/forum?id=wXfuOj9C7L) | Conference paper | 2025 | ICML 2025 Spotlight |
| [Memory Mosaics at scale](https://openreview.net/forum?id=IfD2MKTmWv) | Conference paper | 2025 | NeurIPS 2025 Oral |
| [Nested Learning: The Illusion of Deep Learning Architectures](https://openreview.net/forum?id=nbMeRvNb7A) | Conference paper | 2025 | NeurIPS 2025 Poster |
| [It's All Connected: A Journey Through Test-Time Memorization, Attentional Bias, Retention, and Online Optimization](https://openreview.net/forum?id=gZyEJ2kMow) | Conference paper | 2026 | ICLR 2026 Poster |
| [Memory Mosaics](https://openreview.net/forum?id=IiagjrJNwF) | Conference paper | 2025 | ICLR 2025 Poster |
| [Titans: Learning to Memorize at Test Time](https://openreview.net/forum?id=8GjSf9Rh7Z) | Conference paper | 2025 | NeurIPS 2025 Poster |

##### Multi-Agent and Embodied Learning

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [The Dormant Neuron Phenomenon in Multi-Agent Reinforcement Learning Value Factorization](https://proceedings.neurips.cc/paper_files/paper/2024/hash/3eec5006051d9544e717067de3220198-Abstract-Conference.html) | Conference paper | 2024 | NeurIPS 2024 |
| [Plasticity as the Mirror of Empowerment](https://openreview.net/forum?id=eOZFqyE9Ok) | Conference paper | 2025 | NeurIPS 2025 Spotlight |

#### Reviews

4 unique records

##### Research Commentary and Podcasts

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Switching between tasks can cause AI to lose the ability to learn](https://www.nature.com/articles/d41586-024-02525-z) | Commentary / podcast | 2024 | Nature News & Views 632, 745–747 |
| [AI can’t learn new things forever — an algorithm can fix that](https://www.nature.com/articles/d41586-024-02756-0) | Commentary / podcast | 2024 | Nature Podcast |

##### Author Explanations and Blog Posts

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Introducing Nested Learning: A new ML paradigm for continual learning](https://research.google/blog/introducing-nested-learning-a-new-ml-paradigm-for-continual-learning/) | Commentary / podcast | 2025 | Google Research Blog |
| [Titans + MIRAS: Helping AI have long-term memory](https://research.google/blog/titans-miras-helping-ai-have-long-term-memory/) | Commentary / podcast | 2025 | Google Research Blog |

#### Community and Tools

2 unique records

##### Continual-Learning Implementations

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
| [Loss of Plasticity in Deep Continual Learning — official code](https://github.com/shibhansh/loss-of-plasticity) | Code | 2024 | GitHub / Nature 2024 companion code |

##### Test-Time Learning Implementations

| Paper or resource | Type | Year | Venue / source |
|---|---|---:|---|
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
