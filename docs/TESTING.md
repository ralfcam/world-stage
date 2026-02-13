# docs/TESTING.md — Architecture test plan (MCP-only)

This runbook prepares the repo for testing the architecture without Python/TKG.

## Preconditions
- Canonical configs exist on `main`: `watchlist.yml`, `triggers.yml`, `daily_template.md`, `taxonomy.csv`, `docs/INDICATORS.md`.
- Continuity artifacts exist:
  - `briefs/state/state_pack.md`
  - `briefs/state/continuity_last7d.md`
  - `briefs/state/active_narratives.yml`

## Test 1 — Task 1 continuity enforcement
1) Run Morning Brief once.
2) Verify each Top-5 line contains: `Continuity: New | Ongoing | Reversal (ref: YYYY-MM-DD)`.
3) Verify the ref date corresponds to yesterday/last-week where applicable.

## Test 2 — State overwrite
1) Run Task 1 + Task 5 on different days.
2) Confirm:
   - `briefs/state/state_pack.md` is overwritten daily.
   - `briefs/state/continuity_last7d.md` and `briefs/state/active_narratives.yml` are overwritten daily.
   - `briefs/daily/YYYY-MM-DD.md` remains immutable.

## Test 3 — Linear feedback loop
Trigger a known gap (e.g., missing primary link) and confirm a Linear issue is created with required fields: Problem, Evidence, Proposed fix, Success criteria.

## Expected outputs
- Daily: `briefs/daily/YYYY-MM-DD.md`
- Drivers: `briefs/drivers/YYYY-MM-DD_cb_drivers.md`
- Energy: `briefs/energy/YYYY-MM-DD_energy_shipping.md`
- Policy: `briefs/policy/YYYY-MM-DD_policy_actions.md`
- Optional weekly: `briefs/weekly/YYYY-Www_weekly_mindmap.md`
