# Triggers playbook

This document explains the intent behind `triggers.yml` and how to tune it.

## How triggers are used
A trigger is a *promotion rule* that elevates an actor/theater into the brief’s Top 5 and forces specific fields (mechanism, asset channels, invalidation) to be written.

## Trigger tuning
- False positive: promoted item rarely moved markets or was mostly rumor.
- False negative: missed a re-pricing that was obvious in hindsight.

## Common triggers (examples)
- Central bank surprise: emergency operation, clear guidance pivot.
- Chokepoint disruption: sustained disruption that changes freight/insurance/oil risk premium.
- Major sanctions action: binding new measures with enforcement posture.
- Export controls escalation: compute/semis/critical minerals restrictions.

## Refinement pattern
When noise persists for 3+ days:
1) Narrow the condition (require primary confirmation).
2) Add a “market channel test” (must plausibly hit rates/FX/oil/credit).
3) Add a de-escalation clause (what would quickly reverse it?).

## Logging
Every change should be explained in a Linear issue and documented in `docs/CHANGELOG.md`.
