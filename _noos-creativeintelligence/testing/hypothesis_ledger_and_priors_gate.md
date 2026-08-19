# Hypothesis Ledger & the Priors Gate

The ledger is the data; the gate is the rule. Together they make the test loop (see `test_process.md`) cumulative: nothing is proposed without reading what has already been tried, and nothing already falsified is re-proposed without a reason.

## The ledger — one file per client

Path in the client's knowledge tree: `Strategy/hypothesis-ledger.md`. Created empty at setup from `templates/hypothesis_ledger.md`. One row per hypothesis:

`| Hypothesis ID | Date launched | Audience | Stage | Trigger | Objection | Expected | Actual | Verdict | Learning | Ad names |`

- **Ad names** is the join key. The ad↔hypothesis link goes through this column — filled by the setup step (`noos-client-adsetup`) — not through the ad name. `hyp:` is NOT part of the standard ad name; clients may use it locally as a custom field.
- **Stage** answers the funnel question at the hypothesis level — the ledger's Stage column, not the campaign's `set:` slot alone, is where a hypothesis' funnel placement is read.
- **Verdict** is one of: `confirmed`, `falsified`, `uninterpretable` — always with the why in Learning.

### Write rights

**Only `noos-client-evaluation` writes verdicts and cold markings.** Other flows append rows (a new hypothesis with its ad names) but never judge. One writer of judgments means no contradictory verdicts.

## The priors gate

### (a) The read rule

The brief flow (`nooscreativebrief`) **MUST read the ledger and the client's historical performance before generating concepts.** If either cannot be read — abort. A brief written blind to priors is not a brief, it is a guess with production costs.

### (b) Cold combinations

A dimension or combination (hook type, template, trigger×stage, persona×concept) is marked **cold** in the ledger when all three hold:

1. **≥ 3 falsified tests** on it,
2. **0 winners**,
3. **total spend above the client's threshold** — the threshold is client-specific and lives in the client's `Strategy/measurement.md`.

Cold combinations **may not be proposed in new briefs without explicit justification** — a written answer to *"what is different this time?"*. No answer, no proposal.

### (c) Uninterpretable verdicts are not evidence

A verdict of `uninterpretable` — too little spend, several variables changed at once, audience saturation, trigger/stage mismatch — **never counts toward a cold marking.** Only clean falsifications count. Every cold marking carries its evidence in the ledger: number of tests, total spend, period.

### (d) Evaluate template×trigger, not template alone

Before a template is marked cold, check whether the failures share a trigger. A template that failed three times *with the same trigger* has proven nothing about the template — mark the combination, not the template.

## What lives where

| Standard (this repo) | Client-specific (client's knowledge tree) |
|---|---|
| Ledger row format | The ledger itself (`Strategy/hypothesis-ledger.md`) |
| The gate rules (a)–(d) | The spend threshold (`Strategy/measurement.md`) |
| Write-rights rule | The verdicts and cold markings |
