# awesome-plasticity

整理与可塑性（plasticity）相关的论文、预印本、解读和代码资源，重点覆盖：

- 持续学习中的可塑性丧失、诊断与恢复
- Hebbian / STDP、局部学习和脉冲神经网络
- 语言模型的持续适应、测试时记忆和多时间尺度学习

这是一个精选型文献库，不是穷尽式系统综述。每条记录都尽量保留正式发表状态、原文链接、核心发现、实验范围与阅读边界；“可塑性丧失”和“灾难性遗忘”按不同问题记录。

## 从哪里开始

- 文献目录：docs/index.md
- 中文调研：docs/review.md
- 结构化数据：data/catalog.csv
- BibTeX：references/plasticity.bib
- 单篇记录：data/records/
- 维护说明：CONTRIBUTING.md

## 本地构建

仓库只依赖 Python 标准库：

    python scripts/build_catalog.py
    git diff --check

构建脚本会从 data/records/*.json 重新生成总 JSON、CSV、目录和 BibTeX。生成后的文件也纳入版本控制，便于直接在 GitHub 网页浏览和检索。

## 说明

文献年份按正式发表场所记录；arXiv 首发日期单独保留。论文结论、发表状态和代码链接应以记录中的来源链接为准。欢迎通过 Issue 或 Pull Request 提交补充和勘误。
