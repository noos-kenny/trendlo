# Test Process — from hypothesis to decision

How a creative test runs at NOOS, step by step. The psychology behind each step lives in `method/` — this file is only the process.

## The loop

```
1. OBJECTION   →  2. HYPOTHESIS  →  3. PRODUCTION  →  4. LAUNCH  →  5. READ  →  6. DECIDE  →  7. LOG
   (what stops        (testable         (assets per       (clean        (against      (kill /       (ledger +
    the buyer?)        prediction)       brief)            test setup)   pre-set KPI)   scale /       learnings/)
                                                                                        iterate)
```

## Step by step

**1. Start from an objection, not an idea.** Every test answers a named mental hindrance in the buyer. If you cannot name the objection, you are not ready to test. (See `method/04_hypothesis_architecture.md`.)

**2. Write the hypothesis before production — behind the priors gate.** The brief flow MUST read the client's hypothesis ledger and historical performance first; cold combinations are not proposed without explicit justification (see `hypothesis_ledger_and_priors_gate.md`).  Use `templates/hypothesis_card.md`. Format: *"We believe X will lead to Y because Z. We know it's true when we see W."* All seven required fields filled, including expected impact and kill criteria — decided **before** launch, never after.

**3. Brief production.** One hypothesis → one or more assets. Name every asset per `naming_conventions.md` so results can be traced back to the hypothesis.

**4. Launch clean.** One variable at a time where possible. Same audience and budget conditions for test and control. Note anything dirty (seasonality, promo overlap) on the hypothesis card.

**5. Read against what you predicted.** The test is judged on the primary KPI and threshold written in the card — not on whichever metric happens to look good afterwards.

**6. Decide.** Three outcomes only: **kill** (kill criteria hit), **scale** (prediction confirmed at meaningful spend), **iterate** (signal but unclear — form a sharper follow-up hypothesis).

**7. Log.** Update the hypothesis ledger — `Strategy/hypothesis-ledger.md` in the client tree; verdicts and cold markings are written only by `noos-client-evaluation` (see `hypothesis_ledger_and_priors_gate.md`). If the learning holds beyond this one client/campaign, write it to `learnings/` in the master repo.

**Client-facing reports** are snapshots in the client tree's `Reports/` folder: `YYMMDD-creative-report-BRANDNAME.md`, snapshot rules apply (dated, immutable). Written by `noos-client-report`, built on the tree's historical performance & learnings.

## Rules of thumb

- A test without kill criteria is not a test — it is spend.
- Confirmed hypotheses are as valuable as failed ones only if both are logged.
- Never let one winning ad rewrite the method. Patterns need repetition across tests (see `method/08_ai_pattern_analysis.md`).
