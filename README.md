# GOTV maps (feedback builds)

Static copies of the pages built in the private `orange-county-gotv` project (`map/dist/`).

- `index.html`: **the combined map** (current, published 11/02/2026). Precinct turnout map with district layers and two-district overlaps: overlay a second district type, select an overlap (e.g. HD 42 & CC 3), and everything outside it is grayed out, with its turnout, "not yet voted" and precinct list. TQV data as of Mon 11/02 1:50 PM EST.
- `overlap.html`: district overlap viewer, **obsolete as of 11/02/2026** (folded into the combined map). Kept only so old links work; it carries an "Obsolete" banner and is no longer updated.

Do not edit here. Rebuild in `orange-county-gotv` (`python3 scripts/build_map.py`), then copy `map/dist/index.html` here (adding the noindex tag) and push. `overlap.html` no longer needs copying.

## Senate District 10 (`sd10/`), version 1

Static copies of the pages built in the private `sd-10-gotv` project (`map/dist/`), Florida State Senate District 10 (all of Seminole + part of Orange). Tag `sd10-v1`.

- `sd10/index.html`: precinct turnout map with district layers
- `sd10/overlap.html`: district overlap viewer

Same rule: don't edit here. Rebuild in `sd-10-gotv`, copy `map/dist/index.html` and `map/dist/overlap.html` into `sd10/` (adding the noindex tag) and push.
