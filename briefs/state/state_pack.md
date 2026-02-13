# state_pack.md — single-file continuity + bootstrap pack (template)

> Goal: minimize tool calls for daily Tasks by consolidating continuity + canonical rules into one GitHub-fetched file.
> Update policy: overwrite daily **after Tasks 1–4 have run**.
> Timezone: Europe/Zurich (CET/CEST)

Last updated (CET): {{YYYY-MM-DD}}
Built from repo: ralfcam/world-stage (branch: main)

## A) Continuity (last 7d)

### Active narratives (carry)
- {{Narrative title}} — Continuity: Ongoing (ref: {{YYYY-MM-DD}}) — Since: {{YYYY-MM-DD}}; Last seen: {{YYYY-MM-DD}} {{tags like [Rates][FX]}}

### Reversals / inflections
- {{Narrative title}} — Continuity: Reversal (ref: {{YYYY-MM-DD}}) — What flipped: {{1 line}} {{tags}}

### New themes (emerged)
- {{Narrative title}} — Continuity: New (ref: {{YYYY-MM-DD}}) — Why it’s new: {{1 line}} {{tags}}

### Retired themes
- {{Narrative title}} — Why retired: {{1 line}} — Last seen: {{YYYY-MM-DD}} {{tags}}

## B) Active narrative registry (YAML)

```yaml
meta:
  last_updated_cet: "{{YYYY-MM-DD}}"
  lookback_days: 7

narratives: []

# Example:
# - id: usd_funding_stress
#   title: "USD funding stress / liquidity premium"
#   tags: [Liquidity, FX, Credit]
#   status: active   # active | monitoring | retired
#   since: "{{YYYY-MM-DD}}"
#   last_seen: "{{YYYY-MM-DD}}"
#   continuity_ref: "briefs/daily/{{YYYY-MM-DD}}.md"
#   invalidate_conditions:
#     - "Clear easing in funding-stress commentary; no follow-through in risk-off narratives"
#   primary_sources:
#     - "https://www.federalreserve.gov/"
#   notes: "Keep phrasing consistent across briefs; avoid inventing numbers."
```

## C) Yesterday anchor (for Tasks)

Yesterday brief (expected): `briefs/daily/{{YYYY-MM-DD minus 1}}.md`

Yesterday Top-5 (copy/paste from brief to avoid extra tool calls):
1. {{Top-5 line}}
2. {{Top-5 line}}
3. {{Top-5 line}}
4. {{Top-5 line}}
5. {{Top-5 line}}

## D) Canonical rules snapshot (GitHub truth)

> This section is intended to include the latest canonical files so daily Tasks can bootstrap from this *single* file.
> Update Task must refresh these blocks from `main` each day.

### D1) watchlist.yml (snapshot)
```yaml
{{PASTE_LATEST_watchlist.yml}}
```

### D2) triggers.yml (snapshot)
```yaml
{{PASTE_LATEST_triggers.yml}}
```

### D3) daily_template.md (snapshot)
```markdown
{{PASTE_LATEST_daily_template.md}}
```

### D4) taxonomy.csv (snapshot)
```csv
{{PASTE_LATEST_taxonomy.csv}}
```

### D5) docs/INDICATORS.md (snapshot)
```markdown
{{PASTE_LATEST_docs/INDICATORS.md}}
```

### D6) docs/CONTINUITY.md (snapshot)
```markdown
{{PASTE_LATEST_docs/CONTINUITY.md}}
```
