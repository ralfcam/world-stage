# docs/CONTINUITY.md — Narrative continuity (GitHub + Linear only)

Goal: enforce narrative continuity without a Temporal Knowledge Graph.

## Canonical continuity artifacts
- `briefs/state/continuity_last7d.md`: human-readable rolling 7-day summary (overwrite daily).
- `briefs/state/active_narratives.yml`: machine-friendly narrative registry (overwrite daily).
- `briefs/daily/YYYY-MM-DD.md`: immutable daily log.

## How Tasks should use continuity
At BOOTSTRAP time (after loading source-of-truth configs), also retrieve:
- yesterday’s daily brief
- `briefs/state/continuity_last7d.md`
- `briefs/state/active_narratives.yml`

Then enforce:
- Each Top-5 item declares Continuity: New | Ongoing | Reversal (ref: date).
- Scoreboards and chokepoints call out what changed vs prior brief.

## When to create Linear issues
- A narrative persists 3+ days but is still ambiguous (define invalidate conditions).
- Repeated rumor/noise causes false positives (tighten trigger conditions).
- Missing primary sources prevent confirmation.
