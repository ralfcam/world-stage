# capsule_schema.md — Rolling Memory Capsule (World Stage)
meta:
  tz: Europe/Zurich  # default in triggers.yml [file:15]
  lookback_hours_default: 24  # default in triggers.yml [file:15]
  updated_at_cet: YYYY-MM-DD HH:MM

## READ ME FIRST (how Tasks use this file)
- Tasks MUST read only:
  - CURRENT STATE (primary)
  - RUN LOG (last 2 entries, optional)
- Tasks MUST update:
  - CURRENT STATE (rewrite)
  - TRIGGER HEALTH (update counters/last_seen)
  - RUN LOG (append 1 new entry; prune by day_count_limit)
- Rule: if an indicator/threshold is triggered but the mechanism is unclear, keep it as a watchpoint (not Top-5) and flag for refinement. [file:4]

---

# CURRENT STATE (read-first; keep compact)
meta:
  as_of_date_cet: YYYY-MM-DD
  horizon: "24–72h"
  scope: "Global Macro + Geopolitics (market-impact-first)"

## Themes (rolling)
- New:
- Escalated:
- De-escalated:
- Unchanged:

## Open watchpoints (max 8; NOT Top-5)
- <Watchpoint> | Why it matters: <1 line> | What would promote it: <mechanism + threshold> | Tags: [Rates][FX]  # tags from taxonomy.csv [file:20]

## Live narrative threads (max 12)
- <Thread> | Mechanism: <...> | Assets: <...> | Invalidate: <...> | Watch(24–72h): <...> | Tags: [X][Y]

## Cross-task pointers (max 10)
- Task 1 (Daily): <what must be checked tomorrow morning>
- Task 2 (CB): <bank + next event + link placeholder>
- Task 3 (Energy/Shipping): <risk premium driver + chokepoint>
- Task 4 (Policy): <sanctions/export-control vector + primary source to check>

---

# TRIGGER HEALTH (rolling counters; used for tuning)
rule:
  noise_refinement_threshold_days: 3  # triggers.yml: false +/- for 3+ days => refine [file:15]

## Trigger scorecard (update each run)
# Format:
# - <trigger_id> | last_seen: YYYY-MM-DD | fired_today: y/n | outcome: TP/FP/FN/UNK | fp_streak: n | fn_streak: n | notes: 1 line
- cb_surprise | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- fx_stress_em | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- chokepoint_disruption | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- producer_guidance_shift | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- major_sanctions_action | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- export_controls_escalation | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- direct_escalation | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]
- regime_stability_shock | last_seen:  | fired_today: n | outcome: UNK | fp_streak: 0 | fn_streak: 0 | notes:  [file:15]

---

# RUN LOG (append-only; prune by day_count_limit)
meta:
  day_count_limit: 14
  entry_line_cap: 30  # total lines per day across all tasks (hard cap)

## YYYY-MM-DD (CET)
### Task 1 — Morning Market-Mover (capsule)
STATE (<=12 lines)
- New:
- Escalated:
- De-escalated:
- Unchanged:
- Open watchpoints (max 5):

TRIGGERS FIRED (ids)
- cb_surprise: yes/no; note 1 line [file:15]
- fx_stress_em: yes/no; note 1 line [file:15]
- chokepoint_disruption: yes/no; note 1 line [file:15]
- major_sanctions_action: yes/no; note 1 line [file:15]
- export_controls_escalation: yes/no; note 1 line [file:15]
- direct_escalation: yes/no; note 1 line [file:15]
- regime_stability_shock: yes/no; note 1 line [file:15]

TOP ITEMS (max 5)
- <Event> | Mechanism: <...> | Assets: <...> | Horizon: <...> | Invalidate: <...> | Watch(24–72h): <...> | Tags: [X][Y]  # tags from taxonomy.csv [file:20]

CONFIRMED vs REPORTED
- Confirmed: <...> (primary link) [Tags]
- Reported: <...> (secondary link) [Tags]

MINDMAP DELTAS
- Nodes+: <...>
- Edges+: <A -> B | label: ...>

LINEAR SEEDS (max 3; optional)
- Title:
  Labels: [X][Y]  # taxonomy tags [file:20]
  Problem:
  Evidence: (links)
  Proposed fix (file + exact change):
  Success criteria:

### Task 2 — Central Banks & Macro Drivers (capsule)
TOP ITEMS (max 5)
- <Bank> | What changed: <...> | Channel: <Rates/FX/Liquidity> | Catalyst flag: repricing/noise | Next event: <...> (primary link) | Tags: [Rates][FX]  # tags from taxonomy.csv [file:20]

### Task 3 — Energy + Shipping Risk Premium (capsule)
TOP ITEMS (max 5)
- <Item> | Mechanism: <...> | Assets: <...> | Watch(24–72h): <...> | Tags: [Energy][Shipping]  # tags from taxonomy.csv [file:20]
CHOKEPOINTS (mandatory)
- Strait of Hormuz: status + what changed | Tags: [Energy][Shipping]
- Red Sea / Suez: status + what changed | Tags: [Shipping][Inflation]
- Taiwan Strait / South China Sea: status + what changed | Tags: [SupplyChains][Volatility]

### Task 4 — Sanctions / Export Controls / Policy Actions (capsule)
OUTPUT RULE: primary-source only. If none, write: "No primary-source policy actions in last 24h." [file:4]
TOP ITEMS (max 5)
- <What changed> | Who/what: <...> | Market channel: <...> | Primary link: <...> | Tags: [Sanctions][ExportControls][Regulation]  # tags from taxonomy.csv [file:20]

---

# ARCHIVE (monthly rollups; optional, prevents long-term amnesia)
## YYYY-MM
- Key narratives that mattered (max 10 bullets)
- Trigger tuning notes (max 10 bullets; include trigger_id + what changed)
- Retired threads (max 10 bullets; include invalidate condition that resolved it)
