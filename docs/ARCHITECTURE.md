# docs/ARCHITECTURE.md — Agentic-RAG System Design (testing-oriented)

## Overview
World Stage Monitor is a market-impact-first macro + geopolitics monitoring system built on agentic RAG.

Daily output is written to GitHub (`briefs/`) and system improvements are tracked in Linear.

## Source-of-truth (GitHub)
Canonical configuration:
- `watchlist.yml`
- `triggers.yml`
- `daily_template.md`
- `taxonomy.csv`
- `docs/INDICATORS.md`

Tasks must load these first.

## Narrative continuity (no TKG)
For testing (and for MCP-only operation), narrative continuity comes from GitHub state artifacts rather than a Temporal Knowledge Graph:
- `briefs/state/continuity_last7d.md` (human-readable rolling summary)
- `briefs/state/active_narratives.yml` (machine-friendly registry)
- last N daily briefs in `briefs/daily/`

## Correctness gates
- Market-first: Top-5 only if plausible repricing in 1–3 sessions.
- Evidence standard: Confirmed vs Reported separation.
- Mechanism always required: event → channel → assets → horizon → invalidation.

## CI-by-Linear
Recurring ambiguity/noise must become Linear issues (source gaps, trigger tuning, template fixes, coverage changes).
