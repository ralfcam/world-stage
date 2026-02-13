# docs/INDICATORS.md — Market-impact dashboard (source-of-truth)

Purpose: define the minimal indicator set and **attention thresholds** used by Tasks to decide what is market-moving.

Contract:
- Tasks must reference this file when writing Top-5 items and when deciding whether to activate Tier-3 nodes.
- Thresholds are heuristics (not hard rules). When in doubt, explain the mechanism and uncertainty.

## 0) Daily decision rules
1) Prefer indicators with fast transmission to pricing engines (Rates/FX/Energy/Credit).
2) Promote to Top-5 when you can articulate a credible mechanism to reprice within 1–3 sessions.
3) If a threshold is triggered but the mechanism is unclear, write it as a watchpoint (not Top-5) and open a Linear issue to refine.

## 1) Rates (core)
### US
- UST curve: 2Y, 10Y, 2s10s slope.
  - Attention: large daily yield move (e.g., ~10bp+ in 2Y or 10Y) or clear curve regime shift.
- Real rates vs breakevens (if referenced by sources).
- Policy path: Fed guidance, dot plot narratives, emergency ops.

### Euro area
- Bund yields + periphery spread narrative (BTP-Bund).
  - Attention: spread widening episode tied to policy/fiscal headlines.

### Japan
- JGB volatility + explicit BoJ operations.
  - Attention: signs of impaired market functioning or major guidance shift.

## 2) FX
- Broad USD tone (DXY narrative or USD funding stress proxies).
  - Attention: synchronized USD strength with risk-off and EM stress.
- JPY (carry unwind risk): rapid JPY appreciation + global vol.
- CNH/CNY: fixing narrative, policy easing/tightening signals.
- EM stress (Tier-3 activations): abrupt moves + controls/intervention.

## 3) Credit & liquidity
- IG/HY spread narrative (risk-on/off, refinancing stress).
  - Attention: spread widening with liquidity headlines.
- Funding stress: repo/T-bill dislocations mentioned by credible sources.
- Banking stress: CDS widening, emergency facilities, deposit outflows (if confirmed).

## 4) Equities & volatility
- Global equities: index-level shock vs sector rotation.
  - Attention: broad-based selloff with macro catalyst.
- Volatility: VIX/FX vol regime shifts.
  - Attention: vol spike paired with USD strength and credit widening.

## 5) Energy & inflation impulse
- Oil: Brent/WTI narrative + risk premium.
  - Attention: large daily move or supply shock; explicit producer guidance shift.
- Gas (EU focus): supply disruptions, storage narratives.
- Inflation pass-through: energy move + shipping/freight disruption + policy reaction discussion.

## 6) Shipping / chokepoints
Always track theaters:
- Strait of Hormuz
- Red Sea / Bab el-Mandeb / Suez
- Taiwan Strait / South China Sea

Attention:
- Confirmed kinetic incidents, sustained rerouting, meaningful insurance premium changes (as reported by credible sources), or official advisories.

## 7) Sanctions / export controls
- Sanctions: binding legal actions + enforcement posture.
  - Attention: measures affecting energy, banking, shipping, or strategic tech.
- Export controls: compute/semis/cloud access/critical minerals.
  - Attention: restrictions with immediate supply-chain or capex implications.

## 8) Domestic politics (only when it transmits)
- Elections, emergency fiscal events, capital controls, regime instability.
  - Attention: when policy continuity or flows are plausibly affected.

## 9) Trigger → action mapping (for Tasks)
When an indicator threshold is hit:
- Write: mechanism → assets → horizon → invalidate conditions.
- If repeated noise: create Linear issue proposing a refinement in triggers.yml or sources.

## 10) Notes
- Prefer primary sources; keep “Reported” separate.
- Never invent numbers; only reference moves/levels if supported by sources.
