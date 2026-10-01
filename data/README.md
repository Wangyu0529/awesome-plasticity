# 数据格式

每篇文章或资源对应 data/records/<内部键>.json。`review_id` 只是用于版本控制的稳定内部键；README 和目录不向读者展示这些编号。

常用字段：

- review_id：稳定内部键，不能重复；删除记录时随提交移除。
- title、authors、year、venue、url：基本书目信息。
- entry_type：期刊论文、主会论文、领域会议论文、预印本、解读/播客或代码。
- priority：重点、扩展或解读/代码。
- classifications：面向读者的主题分类列表，每项包含一个 major 和 minor。当前大类是 Problem Definition、Research Methods、Application Scenarios、Reviews、Community and Tools；同一条记录可以出现在多个角度下。
- major_category、minor_category：该记录的主分类，保留用于筛选和兼容旧脚本；README 的 Paper Lists 以 classifications 生成。
- category、key_findings、tasks、limitations：主题、摘要式笔记、实验设置和阅读边界。
- doi、arxiv、code_url：可选的外部链接。
- accessed：最近核验日期。

编辑单篇 JSON 后，在仓库根目录执行：

    python scripts/build_catalog.py

脚本会重新生成 README 的 Contents 和 Paper Lists、data/records.json、data/catalog.csv、docs/index.md 和 references/plasticity.bib。这些文件应一并提交。由于同一篇论文可以属于多个角度，README 中可能出现重复链接，这是有意的交叉索引。
