# state_pack.md — continuity state pack (template)

> Purpose: reduce tool calls by bundling continuity inputs into one GitHub fetch.
> Update policy: overwrite daily **after** Task 1 runs.
> Timezone: Europe/Zurich (CET/CEST)

Last updated: {{YYYY-MM-DD}} (CET)
Lookback: last 7 daily briefs
Latest daily brief (expected): `briefs/daily/{{YYYY-MM-DD}}.md`

## How Tasks should use this
- Prefer fetching this file instead of fetching `continuity_last7d.md` + `active_narratives.yml` separately.
- Enforce in Top-5 lines: `Continuity: New | Ongoing | Reversal (ref: YYYY-MM-DD)`.
- Use the “Active narratives” list below to keep naming consistent.

---

## continuity_last7d.md (embedded)

<!-- Task 5 overwrites everything between BEGIN/END with the current contents of briefs/state/continuity_last7d.md -->
<!-- BEGIN_CONTINUITY_LAST7D -->

(embedded content pending)

<!-- END_CONTINUITY_LAST7D -->

---

## active_narratives.yml (embedded)

<!-- Task 5 overwrites everything between BEGIN/END with the current contents of briefs/state/active_narratives.yml -->
<!-- BEGIN_ACTIVE_NARRATIVES_YML -->

```yaml
meta:
  last_updated_cet: "{{YYYY-MM-DD}}"
  lookback_days: 7

narratives: []
```

<!-- END_ACTIVE_NARRATIVES_YML -->
