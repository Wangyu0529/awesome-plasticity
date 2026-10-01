# 数据格式

每篇文章或资源对应 data/records/<内部键>.json。`review_id` 只是用于版本控制的稳定内部键；README 和目录不向读者展示这些编号。

常用字段：

- review_id：稳定内部键，不能重复；删除记录时随提交移除。
- title、authors、year、venue、url：基本书目信息。
- entry_type：期刊论文、主会论文、领域会议论文、预印本、解读/播客或代码。
- priority：重点、扩展或解读/代码。
- major_category、minor_category：面向读者的主题大类和小类；README 的 Paper Lists 按这两个字段分组。
- category、key_findings、tasks、limitations：主题、摘要式笔记、实验设置和阅读边界。
- doi、arxiv、code_url：可选的外部链接。
- accessed：最近核验日期。

编辑单篇 JSON 后，在仓库根目录执行：

    python scripts/build_catalog.py

脚本会重新生成 README 的 Contents 和 Paper Lists、data/records.json、data/catalog.csv、docs/index.md 和 references/plasticity.bib。这些文件应一并提交。
