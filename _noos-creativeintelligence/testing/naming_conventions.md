# Naming Conventions

NOOS standard naming for Meta campaigns, ad sets and ads — the **prefixed-attributes model** ("Winberg"), May 2026, corrected and extended **2026-08-13 (v2)**. Names carry the whole test context, so any result in an ad platform can be traced back to persona, barrier, trigger, concept and hook without opening a single document.

**Living source of truth:** the [NOOS Naming Convention sheet](https://docs.google.com/spreadsheets/d/1nL1dQYo-olnOmUXbauKBwzNGwrivQI5nj0V13RZlhSU/edit) — builders with auto-generated names, picklists, BI mapping and per-client custom fields live there. This file documents the model; allowed values are maintained in the sheet's Picklists tab.

## The principle

Every attribute is prefixed with a short code (`m:` for market, `set:` for setting, and so on). The string is **self-describing** — it can be parsed directly without going through the sheet. Because every part carries its own identity:

- **Empty fields are skipped.** No `na` placeholders — if an attribute doesn't apply, leave it out entirely.
- **Position matters less.** Attributes are conventionally written in schema order, but the parser doesn't depend on it.
- **Custom attributes are safe.** A client-specific field is just a new prefix (e.g. `s:ss26` for season). Document new prefixes in the sheet's "Custom fields per client" tab so nothing collides.

## The menu principle

**The schema is a MENU, not an obligation** (Pontus, confirmed by Kenny 2026-08-14). Every slot is standardised — its prefix and its picklist values are fixed — but no case uses every slot. Each client/case picks the subset that fits its strategy and uses that subset **consistently within the case**. Unused slots are omitted entirely — never `na` placeholders. The parser reads per prefix, not per position, so missing slots are expected, not errors.

Slots omitted by default in the standard:

- **`bar:` (barrier) — optional, omitted by default** (decision 2026-08-14). Barrier is derived from `con:` — concept↔barrier is 1:1 in the standard hypothesis architecture, so naming the concept names the barrier. Use `bar:` only in cases where concept↔barrier is NOT 1:1.
- **`hyp:` is not part of the ad name in the standard.** The link from ad to hypothesis goes through the hypothesis ledger's *Ad names* column (see `hypothesis_ledger_and_priors_gate.md`), not through the name. Clients may carry `hyp:` locally as a custom field.

### Value rules

- Lowercase only.
- No `å/ä/ö` — write `har`, not `hår`.
- Spaces become hyphens (the sheet formula substitutes them automatically).
- A colon must **never** appear inside a value — the colon is the prefix delimiter.
- One prefix = one meaning, never reused for a second attribute.

## The three levels

| Level | Pattern | Example |
|---|---|---|
| **Campaign** | `m:{market}-set:{setting}-obj:{objective}-aoo:{ao_oo}-c:{campaign}-d:{YYYY.MM.DD}` | `m:se-set:prosp-obj:purchase-aoo:cbo-c:linne-d:2026.05.07` |
| **Ad Set** | `m:{market}-aud:{audience}-age:{age}-tgt:{target}-res:{result}-pl:{placements}-test:{test}` | `m:se-aud:broad-age:25-55-tgt:broad-res:purchase-pl:auto-test:launch` |
| **Ad** | `fmt:{format}-foc:{focus}-pers:{persona}-bar:{barrier}-trig:{trigger}-con:{concept}-h:{hook}-tmpl:{template}-br:{brand}-p:{product}-lp:{lp}-tech:{technique}-b:{boosted}-cr:{creator}-cp:{copy}-v:{version}-d:{YYMMDD}` | `fmt:img-foc:cat-pers:rutininvest-bar:priset-trig:curiosity-con:k1-h:question-tmpl:tmpl1-br:sailors-p:vit-linne-lp:pdp-tech:static-headliner-cp:copy1-v:1-d:260507` |

The ad level carries the full strategy chain — **persona → barrier → trigger → concept** — so every ad in the platform is traceable to the hypothesis it came from.

## Prefix registry

**Campaign:** `m:` market · `set:` setting · `obj:` objective · `aoo:` ao_oo (budget model) · `c:` campaign (free text) · `d:` date `YYYY.MM.DD`

**Ad Set:** `m:` market · `aud:` audience · `age:` age as `{min}-{max}` (e.g. `25-55`; Meta doesn't accept `+` — write `18-65`) · `tgt:` target · `res:` result · `pl:` placements · `test:` test (free text allowed)

**Ad:** `fmt:` format · `foc:` focus · `pers:` persona · `bar:` barrier (optional — omitted by default, see the menu principle) · `trig:` trigger (one of the 15 canonical triggers — see picklist below) · `con:` concept · `h:` hook (how the ad opens, first 3 seconds — e.g. `question`, `stat`, `confession`, `before-after`) · `tmpl:` template · `br:` brand · `p:` product (free text) · `lp:` landing page · `tech:` technique · `b:` boosted · `cr:` creator · `cp:` copy variant · `v:` version · `d:` date `YYMMDD`

**Collision warning — these are the v1 bugs, don't repeat them:**

| Prefix | Means | NOT |
|---|---|---|
| `p:` | product | persona → use `pers:` |
| `b:` | boosted | barrier → use `bar:` · brand → use `br:` |
| `trig:` | trigger | v1 used `ang:` for angle — retired |

Persona, barrier, concept and template values are **per case**: replace the placeholder slugs in the sheet's Picklists tab with the case's real names (lowercase, hyphens, no spaces, no `å/ä/ö`).

## Picklists

Allowed values for all dropdown attributes live in the sheet's **Picklists / Master Dictionary** tab. **Never free-text a dropdown attribute** — if a value is missing, add it to the Picklists tab first. Free-text fields are only `c:` (campaign), `test:`, `br:` (brand), `p:` (product) and the per-case values (persona / barrier / concept / template).

Key examples (see sheet for the full, current lists): markets `se/no/dk/fi/de/nl/us/gb/fr/es/it/int/keymarkets`; settings `prosp/retarg/winback/brand`; objectives `purchase/traffic/engagement/awareness/leads/app`; budget `abo/cbo/asc/aon`; placements `auto/feed/reels/stories/reels-stories/feed-reels-stories`; formats `vid/img/carousel/dpa-img/dpa-vid/collection`; focus `prod/prob/testim/demo/brand/offer/cat`; triggers are exactly the 15 canonical triggers (decision 2026-08-14, derived from `method/02_psychological_trigger_taxonomy.md`): `riskreversal, authority, transparency, identity, aspiration, commitment, socialproof, similarity, transformation, lossaversion, curiosity, anchoring, scarcity, reciprocity, endowment` — the sheet's current 18-value list must be corrected to derive from these 15; `mirror`, `objection` and `listicle` are not triggers (they are hook/technique territory) and leave the trig picklist; hooks include `question, stat, story, claim, controversy, demo, comparison, before-after, confession, mistake, result-led, tutorial, trend, pov, meme, voiceover, text-only, shock, relatable, educational, asmr`.

## Workflow

1. Copy the sheet (File → Make a copy) per campaign batch or per month.
2. Fill one row per campaign / ad set / ad in the matching Builder tab. Green columns are input cells (dropdown where a picklist exists). The "Generated name" column auto-fills.
3. Leave fields empty when they don't apply — they're skipped in the string automatically.
4. Copy the generated name → paste into Ads Manager. **Never hand-edit the string.**
5. Replace the persona / barrier / concept / template placeholder slugs in Picklists with the case's real names before the first build.
6. Missing a picklist value? Add it to the Picklists tab — never free-text a dropdown column.
7. For BI: parse the string (see below) or point straight at the builder tabs.

## Parsing (BI / Looker / Supermetrics)

1. **Never split naively on `-`** — hyphens are legal inside values (`p:vit-linne`).
2. Read token by token: match the prefix up to `:`, then read the value onward until the next `prefix:` starts.
3. Unknown prefixes must not crash the parser — they're client-specific custom fields. Report them separately.
4. Missing slots are normal, not an error. Empty fields are skipped in the string.
5. The same prefix on several levels (`m:` on both campaign and ad set) is fine — each belongs to its own level.
6. **Backwards compatibility:** old ad names carry `ang:` — map `ang:` → trigger at analysis so old and new names cluster together. Some client names from Aug 2026 carry `mall:` — map `mall:` → `tmpl:`.
7. **Flag legacy names:** an `na` value, or an aspect ratio inside `fmt:` (`fmt:9x16` / `4x5` / `1x1`), marks a pre-v2 name — in v2 `fmt:` carries the format only and a crop lives in a custom `ratio:` field.

### Schema per level

| Level | Attributes in order |
|---|---|
| Campaign | `m, set, obj, aoo, c, d` |
| Ad Set | `m, aud, age, tgt, res, pl, test` |
| Ad (v2, Aug 2026 →) | `fmt, foc, pers, bar, trig, con, h, tmpl, br, p, lp, tech, b, cr, cp, v, d` (+ any client custom fields) — `bar:` optional, omitted by default |
| Ad (legacy, before Aug 2026) | `fmt, foc, ang, h, p, lp, tech, b, cr, cp, v, d` |

Alternatively, if everything is built via the sheet, BI can read the builder tabs directly and skip string parsing — the string is then a human-readable backup.

## Deprecations (formal)

| Deprecated | Replaced by | Rule at analysis |
|---|---|---|
| `ang:` (angle) | `trig:` (trigger) | Map `ang:` → `trig:` so old and new names cluster together. Never write `ang:` in a new name. |
| `mall:` (Gents legacy) | `tmpl:` | Map `mall:` → `tmpl:` at analysis. |
| `na` placeholder values | omit the slot | An `na` value marks a pre-v2 name. Parsers flag it as legacy; new names never contain `na`. |
| Aspect ratio inside `fmt:` (`fmt:9x16` etc.) | custom `ratio:` field | Marks a pre-v2 name. In v2 `fmt:` carries format only. |

## Campaign & ad set naming — where else it lives

The campaign and ad set levels documented above are also documented in the skill `meta-creative-execution` (reference `05_winberg_naming_convention.md`) and in the Naming Convention sheet's **Campaign Builder** / **Ad Set Builder** tabs. All three state the same formats:

- Campaign: `m:{market}-set:{setting}-obj:{objective}-aoo:{ao_oo}-c:{campaign}-d:{YYYY.MM.DD}`
- Ad Set: `m:{market}-aud:{audience}-age:{age}-tgt:{target}-res:{result}-pl:{placements}-test:{test}`

## Migration examples

| Old / draft | Winberg v2 | Level | Note |
|---|---|---|---|
| `noos-se-prosp-engagement-aon-fritext-2026.05.07` | `m:se-set:prosp-obj:engagement-aoo:aon-c:linne-d:2026.05.07` | Campaign | `noos-` dropped; generic free text replaced by the actual campaign theme. |
| `noos-keymarkets-prosp-purchase-denim program-2026.03.25` | `m:keymarkets-set:prosp-obj:purchase-aoo:asc-c:denim-program-d:2026.03.25` | Campaign | Space → hyphen. |
| `se-u-18+-broad-reach-story-Test A` | `m:se-aud:u-age:18-65-tgt:broad-res:reach-pl:stories-test:test-a` | Ad Set | `18+` → `18-65` (Meta doesn't accept `+`). |
| `keymarkets-u-18-64-broad-lpv-ugc` | `m:keymarkets-aud:u-age:18-64-tgt:broad-res:lpv-test:ugc` | Ad Set | Missing placements → omitted (empty fields are skipped). |
| `img-prod-asmr-fritext-pdp-igc-bc-@name-1` | `fmt:img-foc:prod-trig:curiosity-h:asmr-br:sailors-p:vit-linne-lp:pdp-tech:igc-b:bc-cr:@anna-cp:copy1-v:1-d:260507` | Ad | Old `ang:` replaced by `trig:`. Brand goes on `br:`, never `b:`. |
| `fmt:img-foc:cat-p:namn 1-b:barrier 1-trig:curiosity-con:concept 1-…` | `fmt:img-foc:cat-pers:rutininvest-bar:priset-trig:curiosity-con:k1-h:question-tmpl:tmpl1-br:sailors-p:vit-linne-lp:pdp-tech:static-headliner-cp:copy1-v:1-d:260507` | Ad | The v1 bug: persona on `p:` and barrier/brand on `b:` collided with product/boosted. v2 uses `pers:` / `bar:` / `br:` and slugs without spaces. |
| `br:sailors-lang:sv-fmt:img-ratio:4x5-pers:…-mall:m1-…` | `fmt:img-pers:rutininvest-trig:identity-h:claim-tmpl:m1-br:sailors-p:skaggolja-serie-lp:clp-tech:static-headliner-cp:copy1-v:1-d:260810-lang:sv-ratio:4x5` | Ad | `mall:` is `tmpl:` in the standard. `lang:` / `ratio:` are client custom fields and may stay in the string — position doesn't matter. |

## If the client has their own naming convention

Use theirs if documented. If they have none: use the NOOS standard above. Client-specific extra attributes get their own prefix, documented in the sheet's "Custom fields per client" tab (with owner and date) so prefixes never collide.

**Not standard attributes** (decision 2026-08-13): `lang:`, `ratio:` and `hyp:` stay client-specific custom fields rather than standard columns — market is already visible from the ad set, and crops of the same creative sit in the same ad in Ads Manager.

## Changelog

- **2026-08-13 (v2)** — Corrected the prefix collisions from v1 and extended the ad level with the full strategy chain, per the updated NOOS Naming Convention sheet: persona moved from `p:` to `pers:`; barrier moved from `b:` to `bar:`; brand moved from `b:` to `br:`; `ang:` (angle) replaced by `trig:` (trigger); `tmpl:` added for template (client legacy `mall:` maps to it). Added explicit value rules (lowercase, no `å/ä/ö`, spaces → hyphens, no colon inside values), token-by-token parser logic replacing naive `-` splitting, per-level schemas including legacy variants, and the `lang:` / `ratio:` / `hyp:` custom-field decision. Persona/barrier/concept picklists are now slugs without spaces (`rutininvest`, not `namn 1`).
- 2026-08-04 — Replaced the fixed-slot model (fixed order, `na` for empty, no hyphens in values) with the prefixed-attributes model per the NOOS Naming Convention sheet (May 2026): three levels, empty fields skipped, multi-word values allowed, picklists in the sheet as source of truth.
