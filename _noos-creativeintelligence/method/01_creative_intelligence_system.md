# 01 — The NOOS Creative Intelligence System

## What we are replacing

Most creative production today is organised around aesthetics, brand guidelines, and the agency's monthly content calendar. Performance is treated as a separate, downstream function — measured after the fact, optimised through media settings rather than creative substance.

This produces three pathologies:

1. **Creative is briefed against feelings, not hypotheses.** "Make it feel modern" or "make it feel trustworthy" cannot be falsified, so nothing is learned regardless of result.
2. **Performance signals never reach the creative team.** When CTR, CVR, CPL, and CAC live in a dashboard nobody on the creative side reads, the loop is broken.
3. **Volume substitutes for variance.** Teams ship 30 versions of the same idea, mistaking iteration for testing.

The Creative Intelligence System replaces this with a structured, hypothesis-driven loop where every asset is an experiment with a falsifiable prediction tied to a commercial KPI.

## The operating model

```
┌─────────────────────────┐
│ 1. Market & Psychology  │  Who is the audience, what do they believe,
│    Mapping              │  what objections do they hold?
└──────────┬──────────────┘
           ▼
┌─────────────────────────┐
│ 2. Hypothesis           │  What testable predictions follow from
│    Architecture         │  the mapping?
└──────────┬──────────────┘
           ▼
┌─────────────────────────┐
│ 3. Structured Creative  │  Production briefed by hypothesis, not aesthetics.
│    Production           │  Every asset has a trigger, an angle, and a proof.
└──────────┬──────────────┘
           ▼
┌─────────────────────────┐
│ 4. AI Pattern Analysis  │  Cluster winners and losers by trigger, format,
│                         │  audience, and stage.
└──────────┬──────────────┘
           ▼
┌─────────────────────────┐
│ 5. Commercial Impact    │  Connect to the KPI that matters for this model
│    Tracking             │  (CAC, CVR, CPL, MQL→SQL, contribution margin).
│                         │  Update beliefs. Loop.
└─────────────────────────┘
```

The loop is the unit of work — not the campaign, the brief, or the asset. A team that runs four full loops per quarter is operating at Creative Intelligence; one that ships fifty assets without closing the loop is just doing production.

The framework is **vertical-agnostic at the core**. It applies whether the business model is e-commerce (B2C or D2C), subscription, B2B lead generation, B2C lead generation, or B2B SaaS. The KPI definitions and trigger weightings vary by vertical — `06_vertical_adaptations.md` documents those differences. The five-stage loop is constant.

## The five principles

### 1. Psychology over aesthetics

Aesthetics are how a hypothesis is *expressed*. Psychology is what is being *tested*. The same trigger (e.g. Loss Aversion) can be expressed as a stark black card with white type or a sun-drenched lifestyle photo — both are valid, and both can be tested.

What is *not* valid is briefing creative purely on aesthetic terms ("make it feel like Acne in 2018"), because the resulting asset has no falsifiable prediction.

### 2. Every asset is a hypothesis

If you cannot complete the sentence *"This will outperform the control because…"*, you are not running creative — you are running content.

A hypothesis is required for paid creative, optional for organic, and prohibited for nothing. Even brand films can carry a hypothesis ("emotional pre-exposure to the brand will lift conversion on retargeting audiences within 14 days").

### 3. Objections are the leverage point

Most creative tries to *add* desire. Better creative *removes* friction. Behavioural economics is consistent on this: the marginal customer is rarely held back by insufficient appeal — they are held back by an unresolved objection. The shape of the objection varies by vertical:

- **E-commerce.** Price, fit, quality, regret risk, identity match.
- **Subscription / D2C.** Lock-in risk, value over time, churn fatigue from past subscriptions.
- **B2B lead gen / SaaS.** Implementation cost, internal alignment, vendor risk, "another tool" fatigue.
- **B2C lead gen.** Trust in the provider, complexity of the offering, fear of being upsold.

Map the objections, and the triggers select themselves.

### 4. Paid media and creative share the same structure

Audiences, funnel stages, and triggers are the joint vocabulary of media planners and creative strategists. A hypothesis owned only by creatives is a creative idea; a hypothesis owned jointly is a test.

In practice: every paid brief at NOOS has a single document with audience, stage, hypothesis, trigger, angle, proof, and predicted KPI movement.

### 5. AI is a sense-making layer, not a production shortcut

AI's highest-leverage use in this system is *pattern recognition across results* — what triggers, formats, and angles consistently win for which audiences. Production assistance is secondary. Treat AI as the analyst that never sleeps, not as a junior copywriter.

## What the system is not

- It is not a brand strategy framework. Brand positioning sits *upstream* and is an input to mapping.
- It is not a substitute for taste. The framework decides *what to test*. The team's taste decides *how it looks*. Both are required.
- It is not a media-buying playbook. Bidding, audiences, and budget allocation are adjacent disciplines and require their own methodology.
- It is not vertical-specific. Vertical adaptation is documented separately in `06_vertical_adaptations.md`.

## Core academic grounding

The system rests on a small number of robust findings from behavioural science and consumer psychology. They are referenced throughout the rest of the base.

- **Prospect Theory** (Kahneman & Tversky, 1979) — losses loom roughly twice as large as equivalent gains; this is the foundation of Loss Aversion.
- **Influence: The Psychology of Persuasion** (Cialdini, 1984; updated 2021) — the canonical inventory of social influence mechanisms (reciprocity, commitment, social proof, authority, liking, scarcity, unity).
- **Predictably Irrational** (Ariely, 2008) — anchoring, decoy effects, the cost of zero cost.
- **Contagious** (Berger, 2013) — STEPPS model for what gets shared; useful for organic and earned-amplified paid.
- **Thinking, Fast and Slow** (Kahneman, 2011) — System 1 / System 2 and the implications for ad reading speed (most ads are processed in System 1).
- **Alchemy** (Sutherland, 2019) — the case for non-linear, psychological-logic solutions over rationalist optimisation.
- **Self-Determination Theory** (Deci & Ryan, 1985) — autonomy, competence, relatedness as universal human motivators; the spine of Identity Signaling and Aspiration triggers.

These are explored where relevant in the trigger taxonomy.

## Changelog

- 2026-05-10 — v1.0 created.
- 2026-05-11 — v1.1 generalised from premium/fashion focus to multi-vertical scope (e-com, D2C, B2B leads, B2C leads, B2B SaaS).
