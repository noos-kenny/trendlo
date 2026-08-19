# 04 — Hypothesis Architecture

How we write a creative hypothesis at NOOS, and what makes one good.

## What a hypothesis is

A creative hypothesis is a **testable prediction** about how a piece of creative will affect a specific KPI for a specific audience at a specific funnel stage.

It is not:

- A creative idea ("a video of the founder explaining the product").
- A brief ("we need three carousel ads for the spring drop").
- A goal ("increase sales").

It is a sentence of the form:

> *Among [audience] at [funnel stage], creative built around [trigger] expressed as [angle] supported by [proof] will move [KPI] by [magnitude] because [psychological mechanism].*

If any element is missing, you do not have a hypothesis — you have something fuzzier, and the result will not teach you anything.

The KPI in the slot above depends on the business model. E-commerce hypotheses target CVR, AOV, ROAS. Lead generation hypotheses target CPL, form completion rate, lead quality. B2B SaaS hypotheses target demo booking rate, MQL→SQL conversion, sales cycle length. See `06_vertical_adaptations.md` for vertical-specific KPI definitions.

## The seven required fields

| Field | What it is | Why it matters |
|---|---|---|
| **Hypothesis ID** | A short, persistent identifier (e.g. `H-2026-Q2-014`) | Lets us cluster results across campaigns and learn over time. |
| **Audience** | The targeted segment, narrowly defined | Triggers work differently per audience; without this the test is uninterpretable. |
| **Funnel stage** | Prospecting / MOF / BOF | Determines which triggers are valid candidates. |
| **Trigger** | The primary psychological mechanism (one of the 12) | Forces clarity. If you cannot name it, the asset is muddled. |
| **Objection** | The specific mental hindrance being addressed | Triggers select themselves once the objection is named. |
| **Angle** | How the trigger is expressed | The bridge from psychology to creative. |
| **Proof** | The evidence used to make the trigger credible | A trigger without proof is a claim. |
| **Expected impact** | Predicted KPI movement, with magnitude and direction | Without a number, you cannot tell if the test "worked." |

Some teams add an eighth field — *risk* — flagging what could go wrong (e.g. "may suppress AOV"). Optional but useful.

## Hypothesis card template

```
HYPOTHESIS CARD
─────────────────────────────────────
ID: H-2026-Q2-014
Brand: [client]
Vertical: [e-com / D2C / B2B leads / B2C leads / B2B SaaS]
Author: [strategist] / Date: [yyyy-mm-dd]

AUDIENCE
  Segment: [behaviourally defined where possible]
  Approx size: [signal of statistical viability]

FUNNEL STAGE
  [Prospecting / MOF / BOF, with any cohort qualifiers]

OBJECTION
  [In the buyer's own language — what's stopping them?]

TRIGGER (primary)
  [One of the 12]
TRIGGER (secondary, optional)
  [If a natural pairing]

ANGLE
  [How the trigger is rendered creatively]

PROOF
  [The supporting evidence — credentials, numbers, named sources]

EXPECTED IMPACT
  Primary KPI: [movement vs control, with magnitude]
  Secondary KPIs: [supporting metrics with directional prediction]

WHY (mechanism)
  [The because… sentence: why this trigger should move this KPI for this audience]

RISK
  [What could go wrong — flagged before launch]

KILL CRITERIA
  [The threshold and spend at which the test is killed if not working]

LEARNINGS GENERATED
  (filled in post-test — see Hypothesis Ledger)
```

## What makes a hypothesis good

Five tests we apply before approving a hypothesis for production.

### 1. It is falsifiable

A hypothesis that cannot be wrong is not a hypothesis. If the predicted impact is "*may improve performance*," there is no result that disconfirms it. Force directional prediction with magnitude.

### 2. The mechanism is named

You must be able to write the *because* sentence. "Because cart-abandoners in our category are blocked by fit risk, and risk-reversal directly cancels that objection" is a mechanism. "Because we think this will work" is not.

### 3. The audience is narrow enough to be coherent

A hypothesis served to "all women 25–45" or "all marketing professionals" tests nothing useful — the segment is too heterogeneous. Narrow until the segment shares an objection. Often this means defining audiences by *behaviour* (cart-abandoners, repeat buyers, lookalikes of churned customers, recent demo-page visitors, lookalikes of closed-won customers) rather than demographics or job titles alone.

### 4. The trigger fits the stage

Cross-reference against `03_funnel_mapping.md`. Risk Reversal at prospecting is almost always wrong. Curiosity at BOF is almost always wrong. The mismatch alone predicts a flat result.

### 5. The expected impact is calibrated against priors

Wild predictions ("+200% CVR" or "+10x CPL improvement") indicate the team has not consulted historical results. Sensible ranges from NOOS experience, by business model:

**E-commerce / D2C (paid social):**

| Move | Conservative | Plausible | Aggressive |
|---|---|---|---|
| CTR (prospecting, new hook) | +5–15% | +20–40% | +50%+ |
| CVR (BOF, new offer construct) | +5–10% | +15–25% | +30%+ |
| CAC (full-funnel restructure) | -5–10% | -15–25% | -30%+ |
| AOV (positioning shift) | flat | +5–10% | +15%+ |

**B2B lead gen / B2B SaaS:**

| Move | Conservative | Plausible | Aggressive |
|---|---|---|---|
| CTR (prospecting, new hook) | +5–15% | +20–40% | +50%+ |
| CPL (BOF, retargeting) | -5–10% | -15–25% | -30%+ |
| MQL→SQL conversion rate | flat to +5% | +10–20% | +25%+ |
| Demo→close rate (indirect via creative) | flat | +5–10% | +15%+ |

**B2C lead gen (services, financial, insurance):**

| Move | Conservative | Plausible | Aggressive |
|---|---|---|---|
| CTR (prospecting, new hook) | +5–15% | +20–40% | +50%+ |
| Form completion rate | +5–10% | +10–20% | +25%+ |
| Lead quality score (closed-loop) | flat | +10–15% | +20%+ |
| CPL | -5–10% | -15–25% | -30%+ |

If a hypothesis predicts an "aggressive" move, it should be paired with a strong directional reason — not optimism.

## The Hypothesis Ledger

Every hypothesis lives in a ledger after it ships, with the result and the *learning* — what the result tells us about audiences, triggers, and our priors. Two patterns to look for:

- **Trigger-level patterns.** "Volume Proof outperforms Similarity Proof for our cold prospecting in SE, but not in DK." That is a strategic asset, not just a one-off result.
- **Objection-level patterns.** "In B2B SaaS, vendor-risk objections dominate cart abandonment; in D2C subscription, lock-in objections dominate." Drives next-cycle hypothesis design.

A hypothesis that does not generate a learning is wasted spend, regardless of its result.

## Hypothesis density: how many to run

For an active mid-sized account (~€100k/month paid spend, including paid social, paid search, programmatic where relevant):

- **6–10 active hypotheses per stage** (prospecting / MOF / BOF) at any time.
- **2–3 new hypotheses introduced per fortnight** at each stage; equal number retired or paused.
- **Variance over volume.** Better to have 6 sharply distinct hypotheses than 30 minor variants.

For smaller accounts, drop density proportionally but maintain stage coverage. Three hypotheses across one stage is not a creative system, it is a creative gamble.

For lead gen and B2B SaaS, hypothesis density should be lower at first because the closed-loop signal (lead quality, SQL conversion) takes longer to mature. Better to run fewer hypotheses, each with proper read-time, than to drown the team in tests with no statistically meaningful answers.

## Failure modes

The most common ways hypothesis architecture breaks down in practice:

1. **The hypothesis is rewritten after the result.** "We always thought it would underperform." Use a written ledger; require the prediction to be timestamped before launch.
2. **Multiple variables change between control and test.** A new hook *and* a new offer *and* a new audience — you cannot attribute a result. One variable per hypothesis.
3. **The audience floods.** Prospecting audiences refresh fast in Meta; what looks like creative fatigue is sometimes audience saturation. Track *new vs returning impressions* alongside CTR.
4. **The KPI is too narrow.** A hypothesis that lifts CTR but suppresses CVR or lead quality lifts cost per outcome. Always pair attention KPIs with conviction KPIs.
5. **The team treats the loop as optional.** Hypothesis architecture only compounds if every test feeds the ledger. Without that, the system is performative.
6. **Lead gen and B2B SaaS optimise on the click, not the deal.** Cheap MQLs that never close are a worse outcome than fewer expensive MQLs that do. Always close the loop to revenue.

## A small worked example

**Brand:** Nordic B2C subscription service, ~25k active subscribers.  
**Observation:** prospecting CTR is healthy (~2.2%) but trial-start rate from cold is poor (~0.4%, vs 1.0% benchmark).

**Diagnostic question:** what objection are cold prospects hitting between click and trial start?

**Plausible hypotheses** (we would run 2–3 in parallel):

- **H1.** *Cold prospects are blocked by lock-in concerns.* Test: BOF Risk Reversal creative ("pause anytime, no card required"). Expected: +25% trial-start rate on cart-abandoners.
- **H2.** *Cold prospects are blocked by value-uncertainty over the first month.* Test: MOF Transparency creative (real customers walking through what arrives, weeks 1–4). Expected: +18% landing-page-to-form rate on warm audiences.
- **H3.** *Cold prospects are aesthetically aligned but identity-uncertain.* Test: Identity Signaling prospecting creative shifting from product hero to documentary portrait of a target-segment customer. Expected: -15% CTR, +35% trial-start rate (segmentation, not maximisation).

The three hypotheses are not competing — they are diagnostic. The pattern in their results tells us what is actually wrong, which is more valuable than any single winner.

## Changelog

- 2026-05-10 — v1.0 created.
- 2026-05-11 — v1.1 generalised benchmark ranges across e-com, D2C, B2B leads, B2C leads, B2B SaaS; replaced fashion-specific example with subscription example.
