# 贡献与维护

## 新增文章

1. 复制 data/records/_template.json（或参考现有记录），使用新的稳定编号。
2. 填写标题、作者、年份、来源、原文链接、主题、核心发现、实验设置和阅读边界。
3. 运行 python scripts/build_catalog.py。
4. 检查 data/catalog.csv 和 docs/index.md，再提交改动。

## 更新文章

直接编辑对应的 data/records/<编号>.json，保留 review_id 不变；更新 accessed 日期，并重新运行构建脚本。

## 删除文章

删除对应的 JSON 文件，重新运行构建脚本。若只是暂时不推荐阅读，可以保留记录并在 status 或 limitations 中说明，而不是删除历史。

## 提交前检查

    python scripts/build_catalog.py
    git diff --check
    git status

提交信息建议使用 add: ...、update: ...、remove: ... 等前缀。
