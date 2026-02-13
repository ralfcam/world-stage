# docs/AGENTS.md — Multi-agent roles and collaboration

## Agent taxonomy

### Morning Brief Agent (Task 1)
Scope: Tier 1+2 watchlist (all channels).
Cadence: Every weekday 07:20 CET.
Output: `briefs/daily/YYYY-MM-DD.md`

### CB Driver Agent (Task 2)
Scope: Fed/ECB/BoJ/BoE/PBoC only.
Cadence: Daily 12:30 CET.
Output: `briefs/drivers/YYYY-MM-DD_cb_drivers.md`

### Energy/Shipping Agent (Task 3)
Scope: oil/gas + chokepoints (Hormuz, Red Sea/Suez, Taiwan Strait).
Cadence: Daily 16:00 CET.
Output: `briefs/energy/YYYY-MM-DD_energy_shipping.md`

### Sanctions Agent (Task 4)
Scope: primary-source policy actions (sanctions, export controls, regulations).
Cadence: Every weekday 18:10 CET.
Output: `briefs/policy/YYYY-MM-DD_policy_actions.md`

## Agent capabilities (universal)
- Planning: decompose complex queries into sub-queries.
- Reflection: self-critique for weak mechanisms, missing citations, Confirmed vs Reported violations.
- Tool use: GitHub truth retrieval, web/official sources, Linear issue creation.
- Collaboration: parallel runs + (optional) synthesis step.
