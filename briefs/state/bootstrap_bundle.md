# briefs/state/bootstrap_bundle.md — BOOTSTRAP bundle (template)

> Purpose: single-file BOOTSTRAP payload so Tasks can minimize GitHub READ tool calls.
> Update policy: overwrite daily **after** Tasks 1–4 complete (see Task 5).
> Timezone: Europe/Zurich (CET/CEST)

Last updated (CET): {{YYYY-MM-DD}}
Bundle version: 1

## How Tasks use this
- Preferred BOOTSTRAP: fetch **this file only**.
- Treat the embedded snapshots below as the authoritative input for that run.
- Do not modify embedded canonical configs from within Tasks 1–4; raise a Linear issue instead.

---

## A) Continuity state (embedded)

### A1) Yesterday anchor
- Yesterday brief date (CET): {{YYYY-MM-DD}}
- Yesterday brief path: `briefs/daily/{{YYYY-MM-DD}}.md`

### A2) Continuity last 7d (summary)
- Active narratives (carry):
  - {{Narrative}} — Since {{YYYY-MM-DD}}; Last seen {{YYYY-MM-DD}}; Status Ongoing; Ref `briefs/daily/{{YYYY-MM-DD}}.md` {{tags}}
- Reversals / inflections:
  - {{Narrative}} — What flipped {{1 line}}; Ref `briefs/daily/{{YYYY-MM-DD}}.md` {{tags}}
- New themes:
  - {{Narrative}} — Why new {{1 line}}; Ref `briefs/daily/{{YYYY-MM-DD}}.md` {{tags}}

### A3) Active narratives registry (YAML)
```yaml
meta:
  last_updated_cet: "{{YYYY-MM-DD}}"
  lookback_days: 7

narratives: []
```

---

## B) Canonical configs (snapshots)

### B1) watchlist.yml (snapshot)
```yaml
# Paste current watchlist.yml here (verbatim)
```

### B2) triggers.yml (snapshot)
```yaml
# Paste current triggers.yml here (verbatim)
```

### B3) daily_template.md (snapshot)
```markdown
# Paste current daily_template.md here (verbatim)
```

### B4) taxonomy.csv (snapshot)
```csv
# Paste current taxonomy.csv here (verbatim)
```

---

## C) Canonical docs (snapshots)

### C1) docs/INDICATORS.md (snapshot)
```markdown
# Paste current docs/INDICATORS.md here (verbatim)
```

### C2) docs/CONTINUITY.md (snapshot)
```markdown
# Paste current docs/CONTINUITY.md here (verbatim)
```
