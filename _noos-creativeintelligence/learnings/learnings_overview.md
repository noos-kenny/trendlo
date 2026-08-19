# Learnings — Overview

This folder is the part of the system that **grows**. `method/` says what we believe; this folder records what testing has actually shown.

## What belongs here

A learning earns its place when it:

1. **Generalises.** It held for more than one client, or there is a clear reason to expect it to.
2. **Is grounded in tests.** It traces back to logged hypotheses and test cards, not to a hunch.
3. **Would change a decision.** Someone reading it would brief, weight or test differently.

Client-specific results stay in the client's repo. Only the generalised conclusion moves here — anonymised if needed.

## Structure

- `learnings_overview.md` (this file) — cross-cutting conclusions that don't belong to a single trigger.
- `by_trigger/` — one file per trigger. What works, what doesn't, under which conditions.

## Format for a learning

Keep each learning short and honest:

```
### [One-line conclusion]
- Evidence: [which tests / how many clients / period]
- Conditions: [market, vertical, funnel stage where it held]
- Confidence: [emerging / repeated / established]
- Added: [yyyy-mm-dd]
```

Start every learning at **emerging**. Promote to **repeated** after independent confirmation, **established** when it has survived several clients and quarters. Demote or delete when contradicted — a learnings file that only grows is a learnings file nobody trusts.

## Cross-cutting learnings

*(None logged yet — this section starts empty on purpose.)*
