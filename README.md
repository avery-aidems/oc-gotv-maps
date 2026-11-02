# GOTV maps (feedback builds)

Static copies of the pages built in the private `orange-county-gotv` project (`map/dist/`).

- `index.html`: precinct turnout map with district layers
- `overlap.html`: district overlap viewer

Do not edit here. Rebuild in `orange-county-gotv` (`python3 scripts/build_map.py`), then copy `map/dist/index.html` and `map/dist/overlap.html` here (adding the noindex tag) and push.

## Senate District 10 (`sd10/`), version 1

Static copies of the pages built in the private `sd-10-gotv` project (`map/dist/`), Florida State Senate District 10 (all of Seminole + part of Orange). Tag `sd10-v1`.

- `sd10/index.html`: precinct turnout map with district layers
- `sd10/overlap.html`: district overlap viewer

Same rule: don't edit here. Rebuild in `sd-10-gotv`, copy `map/dist/index.html` and `map/dist/overlap.html` into `sd10/` (adding the noindex tag) and push.
