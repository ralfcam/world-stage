# World Stage Monitor — Docs

This repository powers a Perplexity Space that monitors global macro + geopolitics with a **market-impact bias** (rates/FX/credit/equities/energy) while still accounting for conflict tail risk.

## How it works
- **Source of truth:** `watchlist.yml`, `triggers.yml`, `daily_template.md`, `taxonomy.csv`.
- **Daily workflow:** scheduled Tasks produce Markdown briefs into `briefs/`.
- **Continuous improvement:** gaps/noise become Linear issues (or issue drafts).

## Quick start
1) Commit the four source-of-truth files to `main`.
2) Configure your Perplexity Space to always load them first (GitHub truth/RAG rule).
3) Enable MCP connectors (filesystem/git + Linear) if you want automatic writes and issue creation.
4) Create Tasks for: daily brief, CB drivers, energy/shipping, sanctions/policy.

## Repo layout
- `watchlist.yml` — who/what you track.
- `triggers.yml` — what gets promoted and why.
- `daily_template.md` — output contract.
- `taxonomy.csv` — tags/labels.
- `briefs/` — generated outputs.
- `docs/` — methodology and operating procedures.

## Operating principles
- Prefer primary sources for official actions.
- Separate **Confirmed** vs **Reported**.
- Always explain the mechanism: event → channel → assets → time horizon → invalidate conditions.
