# GOTV maps: 2026 General Election (archived)

## Live deployments (GitHub Pages)

| Page | URL | Final data |
|---|---|---|
| Orange County precinct turnout map (combined map, with district layers, overlaps and the Election Day layer) | https://avery-aidems.github.io/oc-gotv-maps/ | Tue 11/03/2026, 7:10 PM EST |
| Orange County district overlap viewer (**obsolete since 11/02**, folded into the combined map) | https://avery-aidems.github.io/oc-gotv-maps/overlap.html | Mon 11/02/2026 |
| Senate District 10 precinct turnout map (with the Election Day layer and D vs R section) | https://avery-aidems.github.io/oc-gotv-maps/sd10/ | Tue 11/03/2026, Seminole 7:01 PM / Orange 7:10 PM EST |
| Senate District 10 district overlap viewer | https://avery-aidems.github.io/oc-gotv-maps/sd10/overlap.html | Mon 11/02/2026, 11:40 AM EST |

All pages carry a `noindex` tag, so search engines skip them, but anyone with a link can open them.

## Status: archived (11/06/2026)

Election Day is over. These pages are frozen snapshots and are **no longer refreshed**.

- The two turnout maps carry an "Archived" banner. Their live freshness badge ("Updated n min ago", turning amber and then red "Stale") is replaced with a fixed "Archived snapshot" label. Everything else (data, views, notes) is as published on the evening of 11/03.
- Counts are turnout from the Supervisor of Elections' Turnout Quick View (TQV), not official results.
- Git tag `2026-general-archive` marks this final state. `sd10-v1` marks SD 10 version 1 (11/02).
- Leave these files in place so existing links keep working.

## Reusing for a future cycle

The pages here are build outputs. Nothing in this repo is edited by hand except the archive banner and badge above. The source lives in private local projects:

| Project | What it holds |
|---|---|
| `orange-county-gotv` | Orange County map: `map/template.html`, `map/districts_lib.*`, `scripts/build_map.py`, `scripts/districts.py` (district layer list), `scripts/eday.py` (Election Day layer and 2022-based model) |
| `sd-10-gotv` | SD 10 map: same layout, plus results, party and D vs R scripts. `UPDATE.md` documents the 2026 refresh procedure. |
| `state-election-data` | TQV turnout pulls (`scripts/update.py`), with dated snapshots |

**Commit the source projects first.** As of 11/06 the Election Day work in both projects (the `eday.py`, results and party scripts, `docs/eday/`, template and build changes) is still uncommitted. Until it is committed, these built pages are the only copy of that version.

What is tied to 2026 and needs changing for a new cycle:

- **Election and data:** the TQV election ID (`301` = 2026 General, e.g. `data/tqv/ORA/301.data.json`), the mail and early-vote start dates (10/6 and 10/20), the election date and poll-close time (`polls_close_utc`), and the OC Dems sheet extract.
- **Election Day model:** the 2022 baseline (`data/eday2022/sheet_2022_d_mev.csv`) and the fitted coefficients in `eday.py`. Refit on the new cycle's data, or swap in the most recent comparable election.
- **Geography:** precinct and district boundaries (`fetch_boundaries.py`, `fetch_subprecincts.py`, Seminole geometry for SD 10). Recheck after redistricting or precinct changes.
- **Labels:** the "2026 General Election" eyebrow text and page titles.
- **Live features:** the freshness badge and its 30-second timer live in the source templates (`updateFresh` in `map/template.html`) and were only frozen in the copies here. A new Election Day build gets them back automatically.

To publish a new cycle, use a new folder (for example `2028/` or `2028/sd10/`) or a new repo. Don't overwrite the 2026 files. Add `<meta name="robots" content="noindex">` right after `<head>` in each copied page. GitHub Pages serves this repo from the root of `main` (`.nojekyll` is present).
