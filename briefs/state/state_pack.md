# briefs/state/state_pack.md — continuity pack (template)

> Purpose: small continuity payload (GitHub-only; no TKG).
> Update policy: overwrite daily **after** Tasks 1–4 complete (see Task 5).
> Timezone: Europe/Zurich (CET/CEST)

Last updated (CET): {{YYYY-MM-DD}}
Lookback: last 7 daily briefs

## 1) Yesterday anchor
- Yesterday brief date (CET): {{YYYY-MM-DD}}
- Yesterday brief path: `briefs/daily/{{YYYY-MM-DD}}.md`

## 2) Continuity last 7d (human-readable)
### Active narratives (carry)
- {{Narrative title}} — Since: {{YYYY-MM-DD}}; Last seen: {{YYYY-MM-DD}}; Status: Ongoing; Ref: `briefs/daily/{{YYYY-MM-DD}}.md` {{tags like [Rates][FX]}}

### Reversals / inflections
- {{Narrative title}} — What flipped: {{1 line}}; Ref: `briefs/daily/{{YYYY-MM-DD}}.md` {{tags}}

### New themes (emerged)
- {{Narrative title}} — Why it’s new: {{1 line}}; Ref: `briefs/daily/{{YYYY-MM-DD}}.md` {{tags}}

### Retired themes (no longer active)
- {{Narrative title}} — Why retired: {{1 line}}; Last seen: {{YYYY-MM-DD}} {{tags}}

## 3) Active narratives registry (YAML)
```yaml
meta:
  last_updated_cet: "{{YYYY-MM-DD}}"
  lookback_days: 7

narratives: []

# Example narrative (copy/paste, then remove comments):
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
