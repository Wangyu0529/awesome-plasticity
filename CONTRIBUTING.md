# Contribution and maintenance

The repository homepage is `README.md`. Its manually maintained `News` section and Chinese/English introduction can be edited directly. The `Contents` and `Paper Lists` blocks are generated from the records so that the homepage, `docs/index.md`, CSV catalog, and BibTeX stay synchronized.

## Add a paper or resource

1. Copy `data/records/_template.json` to a new unique internal key such as `P057`.
2. Assign one meaningful `major_category` and `minor_category` from the existing taxonomy, then fill in the title, authors, year, venue, source URL, findings, experimental setting, and limitations.
3. Run:

       python scripts/build_catalog.py

4. Review the updated `README.md`, `docs/index.md`, `data/catalog.csv`, and `references/plasticity.bib`.
5. Commit and push the generated changes.

## Update an entry

Edit the corresponding `data/records/<ID>.json`, keep `review_id` unchanged, update `accessed`, and run the build command. The Paper Lists section in `README.md` will update automatically.

## Remove an entry

Delete the corresponding record and rebuild the catalog:

       git rm data/records/P057.json
       python scripts/build_catalog.py

If an item is temporarily less relevant, keep its record and explain the status or limitation instead of deleting its history.

## Update the homepage

- Add the newest short announcements at the top of `README.md` under `News`.
- Edit the English or Chinese introduction directly when the scope changes.
- Do not hand-edit the content between `BEGIN: GENERATED ...` and `END: GENERATED ...`; rebuild it from `data/records/`.
- To change the grouping or table columns, edit `scripts/build_catalog.py`, run it, and commit the generated output.

## Before pushing

       python scripts/build_catalog.py
       git diff --check
       git status

Use commit prefixes such as `add:`, `update:`, `remove:`, or `docs:`.
