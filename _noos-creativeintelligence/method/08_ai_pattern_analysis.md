# 08 — AI Pattern Analysis

How AI is used in the NOOS Creative Intelligence System, where it earns its keep, and where it gives misleading answers if used naively.

The principle from `01_creative_intelligence_system.md` repeated here, because it is load-bearing: **AI is a sense-making layer, not a production shortcut.** Its highest-value use is in pattern recognition across performance results — not in generating creative that no one tested before.

## The five AI workloads

### 1. Trigger pattern attribution

**Question answered:** *Which triggers, formats, and angles are consistently winning for this brand, this audience, this stage?*

**Inputs.** A tagged corpus of past creative (each asset labelled with primary trigger, angle, archetype, audience, stage) and the matched performance results (CTR, CVR, CAC, ROAS, retention).

**Method.**

- Cluster assets by trigger and stage.
- Compare distributions of performance KPIs across clusters.
- Surface trigger × audience × stage combinations that out- and under-perform the account median by a meaningful margin.
- Always control for spend bias — winning creative gets more spend, which inflates the win signal.

**Output.** A short report: "On this account, *Identity Signaling* prospecting in *NO* outperforms account median CTR by 38% but matches median CVR — meaning it lifts attention without lifting conversion, suggesting the MOF→BOF hand-off is the bottleneck."

**Where it goes wrong.**

- Tagging is the bottleneck. If the asset corpus is not consistently tagged, the analysis is noise.
- Confounded variables. A trigger pattern often co-varies with seasonality, audience size, and offer; isolate before concluding.
- Survivorship bias. Killed creative is often missing from the corpus, which inflates winning-trigger signals. Maintain a "killed" archive.

### 2. Creative fatigue detection

**Question answered:** *Which assets are saturating — and how soon?*

**Inputs.** Daily performance metrics per asset, with frequency, audience size, audience refresh rate.

**Method.**

- Track the slope of CTR / CVR / CPM over the asset's life.
- Identify the inflection point where performance breaks against benchmark trajectory.
- Distinguish *creative fatigue* (CTR decay, CVR stable) from *audience saturation* (CPM rise, CTR stable) from *seasonality* (everything moves).

**Output.** Asset-level fatigue scoring with predicted half-life and refresh recommendation.

**Where it goes wrong.**

- Algorithms confuse audience and creative drivers. Look at *new vs returning* impressions before concluding fatigue.
- Small accounts have signal-to-noise problems on per-asset analysis. Pool by archetype where data is thin.
- Refresh recommendations should not be "make this same asset again with a different background." Fatigue is often *trigger* fatigue, not asset fatigue — the audience has heard the message, not just seen the visual.

### 3. Hypothesis generation from objection data

**Question answered:** *What are buyers actually saying — in reviews, support tickets, comments, search queries — and what hypotheses follow?*

**Inputs.** Customer reviews, support tickets, social comments, on-site search queries, post-purchase surveys.

**Method.**

- Cluster verbatims by theme.
- Identify the dominant *objections* (fit, price, quality, identity, regret risk).
- Map each objection to candidate triggers from the taxonomy.
- Generate hypothesis cards for the top 3–5 objections.

**Output.** A backlog of hypothesis candidates rooted in real buyer language. Often the highest-leverage AI work in the system because it directly fixes the upstream of every other workload.

**Where it goes wrong.**

- Sampling. Reviewers self-select; cart-abandoners are silent. Always supplement with active research where possible (post-checkout exit surveys, abandonment surveys).
- Translating verbatim language into trigger language. The buyer says "I'm worried about the fit" — the system says "Risk Reversal hypothesis on cart-abandoners." That translation is judgement, not pattern matching.

### 4. Cross-account / cross-market pattern bank

**Question answered:** *What have we learned across the agency that applies here?*

**Inputs.** The hypothesis ledger across all NOOS accounts, anonymised and aggregated.

**Method.**

- Surface trigger × category × market × stage patterns at the agency level.
- Maintain a confidence rating per pattern (sample size, consistency).
- Make the bank queryable in plain language during briefing.

**Output.** A reference an account team can consult during hypothesis design: "Risk Reversal on cart-abandoners in premium fashion in SE has shown a +20–35% CVR lift across 8 prior tests at p<0.1; high-confidence."

**Where it goes wrong.**

- Treating agency patterns as universal laws. They are priors, not predictions. Tune to the specific brand.
- Letting the bank become a recipe book. The point is to build *better hypotheses faster*, not to rerun winners.

### 5. Production assistance

**Question answered:** *How do we accelerate the variation production within an established hypothesis?*

**Inputs.** A winning asset and a clear creative system around it.

**Method.**

- Generate copy variants under defined constraints (tone, length, trigger, CTA).
- Generate visual variants (color, crop, framing) under defined constraints.
- Use AI to scale *within* a hypothesis, never to generate *across* untested hypotheses.

**Output.** A larger pool of in-pattern assets to test variation within a known winner.

**Where it goes wrong.**

- Most often. Teams use AI to generate volumes of untested ideas, mistaking variety for testing. The result is noise, not learning.
- AI-generated copy without a brand voice document collapses to a generic register. Voice is the constraint AI most needs to be given explicitly.

## The data substrate

None of the above works if the underlying data is messy. The minimum-viable substrate:

- **Asset tagging.** Every paid asset tagged with: archetype, primary trigger, secondary trigger (if any), angle, stage, audience, hypothesis ID.
- **Performance pull.** Daily KPIs by asset (CTR, CVR, CPM, CPC, ROAS, frequency, new-vs-returning).
- **Hypothesis ledger.** Every hypothesis with prediction, result, and learning.
- **Customer voice corpus.** Reviews, tickets, comments, surveys — refreshed monthly.

Without this, AI workloads produce confident-sounding but unreliable output. *The substrate is the work.*

## When AI is the wrong tool

A useful list of cases where reaching for AI is the failure mode:

- **When the problem is brand-strategic.** AI cannot tell you what the brand should stand for, only optimise within the constraint set.
- **When the data corpus is too thin.** Below ~20 well-tagged assets per stage, pattern detection is noise.
- **When the brief is "make this perform better."** That is not a question AI can answer; it is a request for human judgement on what to test next.
- **When the creative is high-stakes (heritage moments, large brand campaigns).** The downside risk of an AI-shaped tonal mistake exceeds the upside of speed.

## A practical AI cadence at the agency

Recommended rhythm:

- **Weekly.** Fatigue detection across active assets. Short report to creative + media.
- **Bi-weekly.** Hypothesis generation pull from customer voice corpus. Three new hypothesis candidates per account.
- **Monthly.** Trigger pattern attribution. Revisit which triggers are working per market and stage.
- **Quarterly.** Cross-account pattern bank refresh. Update the agency-wide priors.

Build the cadence into how the team operates; do not leave AI as an "occasionally we run an analysis" tool. Compounding only happens through rhythm.

## Tooling at NOOS

Without endorsing specific vendors at the time of writing — the stack typically includes:

- An ad analytics platform that exports asset-level data with custom tags (Meta + Google Ads native, plus Triple Whale, Northbeam, Polar Analytics, or similar for cross-channel).
- A Python or SQL layer for cluster analysis and pattern attribution.
- An LLM (Claude, GPT-class) for verbatim clustering, hypothesis drafting, and copy variation under constraint.
- A simple data catalogue (Notion, Airtable) for the hypothesis ledger.

The tooling is replaceable. The discipline of substrate, tagging, and ledger is not.

## Changelog

- 2026-05-10 — v1.0 created.
