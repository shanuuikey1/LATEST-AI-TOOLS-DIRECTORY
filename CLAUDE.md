# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## AI Tools Directory

- `index.html` — the live static site.
- `tools_config.json` — tool definitions with version-check regexes.
- `tools_monitor.py` — daily monitoring script: checks all tool URLs for 404s/redirects/errors, auto-fixes permanent redirects (301/308) directly in `index.html`, flags version drift, generates `check_report.md`.
- `.github/workflows/daily-check.yml` — runs `tools_monitor.py` daily at 06:00 UTC (and on manual dispatch) and commits changes back to the repo.
- `requirements.txt` — Python deps for `tools_monitor.py`.

Run the monitor locally with:
```bash
pip install -r requirements.txt
python tools_monitor.py
```
