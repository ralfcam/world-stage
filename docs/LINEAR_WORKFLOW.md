# Linear workflow

Purpose: close the loop between monitoring output and system improvement.

## Issue types
- **Source gap:** missing primary source, or unreliable link.
- **Trigger tuning:** repeated false positives/negatives.
- **Template fix:** sections that produce noise or omit key fields.
- **Coverage change:** promote/demote actors, add a theater.

## Required fields (standard)
- **Labels** (MANDATORY): Must include at least 1 category tag from `taxonomy.csv` (e.g., Rates, FX, Energy).
- **Problem**: Clear statement of the gap or error.
- **Evidence**: Primary source link + excerpt/summary.
- **Proposed fix**: Specific file path + exact change (or pseudo-code).
- **Success criteria**: verifiable improvement for next week's cycle.

## Weekly cadence
- **Monday (Triage)**:
  - Validate required fields.
  - **Enforcement**: Reject/Close issues missing a Taxonomy Label.
  - Status: Close, Defer, or Schedule.
- **Friday (Build)**: Implement 1–3 small improvements.
- **Sunday (Sync)**: Update weekly mindmap + update changelog.

## Labeling Standards
All issues must carry a valid tag from `taxonomy.csv` to ensure structural alignment:
- **Markets**: `Rates`, `FX`, `Credit`, `Equities`, `Energy`.
- **Geopolitics**: `Sanctions`, `Defense`, `Diplomacy`.
- **Workflow**: `LinearOps`, `SourceGap`, `TriggerTuning`.
