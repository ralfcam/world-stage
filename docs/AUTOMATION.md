# Automation (MCP) policy

This repo is intended to be updated by Perplexity Tasks with MCP-enabled automation.

## Allowed automated actions
- Write Markdown outputs into `briefs/` using the naming convention.
- Create branches like `auto/*`.
- Commit with a clear message prefix, e.g., `brief(daily): YYYY-MM-DD`.
- Open PRs to `main`.
- Create Linear issues when improvements are detected.

## Forbidden automated actions
- Force-push to `main`.
- Rewrite git history.
- Delete existing briefs or docs.
- Modify `watchlist.yml`, `triggers.yml`, `daily_template.md`, `taxonomy.csv` without a PR (or explicit human approval).

## Human-in-the-loop
Even with MCP, prefer PR-based changes so diffs are reviewable.
