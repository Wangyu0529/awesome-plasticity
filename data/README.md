# 数据格式

每篇文章或资源对应 data/records/<编号>.json。编号沿用调研中的 A01、B01、C01、E01、RB1、RC1 等编号。

常用字段：

- review_id：稳定编号，不能重复；删除记录时随提交移除。
- title、authors、year、venue、url：基本书目信息。
- entry_type：期刊论文、主会论文、领域会议论文、预印本、解读/播客或代码。
- priority：重点、扩展或解读/代码。
- category、key_findings、tasks、limitations：主题、摘要式笔记、实验设置和阅读边界。
- doi、arxiv、code_url：可选的外部链接。
- accessed：最近核验日期。

编辑单篇 JSON 后，在仓库根目录执行：

    python scripts/build_catalog.py

脚本会重新生成 data/records.json、data/catalog.csv、docs/index.md 和 references/plasticity.bib。这些文件应一并提交。
