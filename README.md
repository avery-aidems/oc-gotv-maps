# Orange County GOTV maps (feedback build)

Static copies of the pages built in the private `orange-county-gotv` project (`map/dist/`).

- `index.html`: precinct turnout map with district layers
- `overlap.html`: district overlap viewer

Do not edit here. Rebuild in `orange-county-gotv` (`python3 scripts/build_map.py`), then copy `map/dist/index.html` and `map/dist/overlap.html` here (adding the noindex tag) and push.
