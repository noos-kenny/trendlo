# Template — Test Card

One card per launched test. The hypothesis card holds the prediction; this card holds the execution and the result. Together they make one row in the hypothesis ledger.

```
TEST CARD
─────────────────────────────────────
Test ID: T-[YYYY]-[###]
Hypothesis: [H-YYYY-Q-### — link or filename]
Brand: [client]
Launched: [yyyy-mm-dd]   Read date: [yyyy-mm-dd, decided at launch]

ASSETS
  [ad names per naming_conventions.md — one line per asset]

SETUP
  Channel(s): [meta / tt / ...]
  Audience: [as targeted, incl. any deviation from the hypothesis card]
  Budget: [total + daily]
  Control: [what we compare against]
  Dirty factors: [seasonality, promo overlap, anything that muddies the read]

RESULT (filled at read date, not before)
  Primary KPI: [predicted vs actual]
  Secondary KPIs: [predicted vs actual]
  Spend at read: [amount]

DECISION
  [ ] Kill      [ ] Scale      [ ] Iterate → new hypothesis ID: ___

LEARNING (one or two sentences, honest)
  [What we now know that we didn't before. If it generalises beyond
   this client, add it to learnings/ in the master repo.]
```
