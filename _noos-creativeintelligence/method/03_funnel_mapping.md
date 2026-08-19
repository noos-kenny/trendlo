# 03 — Funnel Mapping

How triggers map to funnel stages, why, and what to expect.

The funnel is a simplification — buyer journeys are messier than three boxes — but the simplification is useful because it forces the team to ask one question per asset: *what mental state is this person in when they see this?*

The framework applies across business models. For e-commerce the stages map to purchase. For lead generation they map to qualified lead and sales meeting. For B2B SaaS they map to demo booking and pipeline. The *triggers* per stage are the same — the *KPIs* per stage differ. `06_vertical_adaptations.md` documents the per-vertical KPI mapping.

## The three stages

| Stage | Buyer state | Primary creative job |
|---|---|---|
| **Prospecting** | Unaware or low intent | Win attention, plant desire, qualify identity |
| **MOF** (middle of funnel) | Aware, evaluating, comparing | Build conviction, handle category-level objections |
| **BOF** (bottom of funnel) | Considering this brand specifically | Remove the final friction, make the buy easy |

Each stage favours a distinct subset of triggers because the buyer's question changes.

## Prospecting

**Buyer's question:** *"Is this for me? Why should I care?"*

The buyer is mid-scroll, has not asked for the ad, and will be gone in 1.5 seconds unless the asset earns the next second.

**Primary triggers.**

- **Identity Signaling** — disqualifies mismatches and qualifies fits fast.
- **Aspiration** — sells the future the product fits into.
- **Loss Aversion** — wins attention through stakes.
- **Curiosity / Open Loop** — wins attention through information gaps.
- **Similarity Proof** — establishes "people like me" within seconds.

**Secondary, situational.**

- Volume Social Proof — works when the number is genuinely impressive and quickly readable.
- Contrast & Anchoring — works for clear category-disruption stories (its home is BOF).
- Reciprocity — value-first content (guides, tools, genuinely useful education) earns cold attention without asking for anything yet.

**Triggers to avoid at this stage.**

- Risk Reversal — the buyer is not yet considering risk because they are not yet considering buying.
- Authority Framing — credentials require attention to *land*, and you do not have it yet.
- Transparency — same problem; transparency rewards the engaged.
- Commitment & Consistency — no commitment to leverage yet.
- Scarcity / Urgency — scarcity of a thing nobody wants yet is noise.
- Endowment Effect — nothing is owned yet, so nothing can be protected.

**What good looks like.**

- Hook in the first 1.5s, ideally visual and unfamiliar.
- A clear identity claim or aspirational frame.
- Either a strong human element or a strong product/format anomaly.

**Primary KPIs.** Hook rate (3s view), CTR, CPC, qualified-traffic share (a proxy: % of clickers who view a second page). *Not* CVR or final conversion — those are noisy late-stage signals at prospecting.

For lead-gen and B2B SaaS prospecting, also track *lead quality proxies* — bounce rate after click, time on page, % who reach the form/calendar — because cheap clicks at the top hide expensive disqualification later.

## MOF — Middle of Funnel

**Buyer's question:** *"Is this real? Is it actually different / better?"*

The buyer has clicked, browsed, possibly added to cart or started a form, and is now comparing — often with two or three competitors open in adjacent tabs.

**Primary triggers.**

- **Authority Framing** — third-party credibility shortcuts comparison.
- **Transparency** — earns the engaged buyer's trust.
- **Volume Social Proof** — answers the "is this real?" question with consensus.
- **Transformation Proof** — gives the buyer a forecast of what they will get.

**Secondary, situational.**

- Similarity Proof — when the audience is niche and identity-led.
- Aspiration — to reinforce the lifestyle or career frame after initial interest.

**Triggers to use sparingly.**

- Loss Aversion — works only if there is a *real* time-bounded reason. Manufactured urgency at MOF damages trust.
- Identity Signaling — already done its job at prospecting; redundancy adds little.

**What good looks like.**

- Long-form formats: 30s+ video, multi-card carousels, founder explainers.
- Density of information without density of clutter.
- One credible source per asset (don't stack four authority claims).

**Primary KPIs.** Add-to-cart rate (e-com), demo booking rate (B2B), MQL form completion rate (lead gen). Plus view-content-to-ATC, time on PDP or landing page, return rate (good MOF creative *reduces* returns by setting realistic expectations).

## BOF — Bottom of Funnel

**Buyer's question:** *"Why now? Why this one over the alternative?"*

The buyer is on the decision threshold. Often retargeted, often within a defined window since first interaction, often with a specific product or specific solution in mind.

**Primary triggers.**

- **Risk Reversal** — directly removes the "what if I'm wrong?" objection.
- **Contrast & Anchoring** — closes by making the choice obvious.
- **Commitment & Consistency** — references the buyer's earlier engagement (the wishlist, the quiz result, the abandoned cart, the abandoned form). Its home stage is retargeting/BOF.
- **Endowment Effect** — the buyer already holds something (cart, trial, quiz result, configured product); not buying now means giving it up.
- **Scarcity / Urgency** — a real constraint, stated plainly, answers "why now?". Manufactured scarcity damages trust — same rule as under Loss Aversion.
- **Volume Social Proof** — reaffirms consensus at the moment of choice.

**Secondary, situational.**

- Loss Aversion — when the urgency is real (last sizes, drop closing, contract deadline). Its home stage is TOF — at BOF it is the situational guest, not the host.

**Triggers to avoid at this stage.**

- Curiosity / Open Loop — withholding information annoys the engaged buyer.
- Aspiration — the dream has been bought; now they need permission to commit.
- Identity Signaling — they have already self-identified.

**What good looks like.**

- Short, dense formats: dynamic product carousels with risk-reversal overlays, abandoned-cart reminders with named items, B2B retargeting with named demo-time slots.
- Personalisation where possible (the *specific* product the user viewed; the *specific* problem they read about).
- Direct CTAs without flourish.

**Primary KPIs.** CVR, ROAS, cost per purchase (e-com). CPL and MQL→SQL conversion rate (lead gen). Cost per demo booked, demo-to-SQL rate (B2B SaaS). Contribution margin per impression across all.

## Why this matters: the trigger/stage mismatch

The single most common cause of underperforming paid creative is *trigger/stage mismatch*. Examples observed in audits:

| Symptom | Likely cause |
|---|---|
| High CTR, dismal CVR/CPL on prospecting | Curiosity hook with no follow-through; or hook-and-bait over-promising. |
| Solid impressions, poor CTR on prospecting | Authority or Transparency at the top of funnel; the credentials never get read. |
| Add-to-cart or form-start strong, completions weak | Missing risk-reversal at BOF. |
| BOF retargeting with cold-style creative | Same Identity Signaling ad served everywhere; familiarity fatigue. |
| Returns spiking after CVR campaign | Transformation Proof staged unrealistically at MOF; expectations not met. |
| Lots of cheap leads, none convert to sales | Prospecting hook attracts the wrong audience; identity disqualification too weak. |

Audit creative by walking each asset to a stage and asking: *does this trigger fit the buyer's question at this stage?*

## Cross-stage hand-off design

The funnel works when adjacent stages reinforce each other. Three patterns we use:

### 1. Identity → Authority hand-off

Prospecting establishes "this brand is for people like you." MOF lands "and here's why it's actually better." Buyer connects emotionally first, intellectually second. Order matters — reverse it and the authority feels disconnected.

### 2. Aspiration → Transformation hand-off

Prospecting: "imagine the home / team / future you want." MOF: "here is the customer who got there." The aspiration is rendered concrete by the transformation, making the buyer believe it is reachable for them too.

### 3. Curiosity → Risk Reversal hand-off

Top: open the loop. BOF: close it with risk-free trial or guarantee. The buyer's curiosity becomes engagement becomes commitment, with the guarantee removing the last friction.

## Working examples

### Example A — A Nordic D2C food subscription

**Audience:** households in SE/NO/DK, dual-income, kids at home, currently using a grocery delivery service.

**Prospecting.** Curiosity + Identity Signaling: documentary-style mini-portrait of a real family at the dinner table, talking about how their week changed. Voiceover: *"We stopped arguing about Tuesday."*  
*Hypothesis: identity-aligned hook will increase qualified click rate among target segment by 25%, with hook-rate lift indicating attention not just clicks.*

**MOF.** Transparency + Authority: founder explaining sourcing, named nutritionist on nutritional load, named producers. Cost breakdown overlay.  
*Hypothesis: long-form transparency will lift trial-signup rate by 18% on engaged-traffic audiences.*

**BOF.** Risk Reversal + Commitment & Consistency: dynamic ad referencing the specific menu the user browsed, with "pause anytime, skip a delivery" overlay and "12,000 Nordic families chose this."  
*Hypothesis: explicit risk reversal and Nordic-localised social proof will lift trial-start rate from cart-abandoners by 30%.*

### Example B — A Nordic B2B SaaS for marketing teams

**Audience:** heads of marketing at SE/NO/DK SaaS companies (50–500 FTE) currently using a competitor product.

**Prospecting.** Curiosity + Identity Signaling: short founder video calling out a category convention. Hook: *"We stopped sending you weekly newsletter benchmarks. Here's what we do instead."*  
*Hypothesis: provocative reframing will lift 3-second view rate by 40% on target ICP audiences, with qualified click rate maintained.*

**MOF.** Authority + Transparency: customer-led case study with named CMOs from credible Nordic SaaS peers. Public pricing on the landing page.  
*Hypothesis: peer authority will lift demo-booking rate by 20% on engaged audiences.*

**BOF.** Risk Reversal + Contrast & Anchoring: "30-min meeting, no commitment" + side-by-side feature comparison against the named competitor.  
*Hypothesis: explicit risk reversal + anchored comparison will lift demo-booked rate by 25% on retargeting audiences.*

### Example C — A B2C lead gen — Nordic home services

**Audience:** homeowners 35–55 in SE/NO planning a renovation in next 12 months.

**Prospecting.** Aspiration + Curiosity: before/after of a real renovation with the homeowner narrating. Hook: *"I didn't think we could afford to redo this."*  
*Hypothesis: relatable aspiration will lift CTR by 30% on home-improvement-intent audiences.*

**MOF.** Authority + Transparency: named contractor with credentials; honest price ranges per project type.  
*Hypothesis: transparency on cost ranges will reduce form drop-off by 25%.*

**BOF.** Risk Reversal + Volume Proof: "Free, no-obligation quote — 8,000 homeowners served in 2025."  
*Hypothesis: explicit no-obligation framing + volume proof will lift form-completion rate by 20% on retargeted audiences.*

These are what mapping looks like in practice — three different psychological jobs, three different creative expressions, one coherent buyer journey, regardless of vertical.

## Changelog

- 2026-05-10 — v1.0 created.
- 2026-05-11 — v1.1 generalised across business models (e-com, D2C, B2B leads, B2C leads, B2B SaaS); replaced fashion-specific example with three multi-vertical examples.
