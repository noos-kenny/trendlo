# Working Instructions — NOOS Knowledge Tree

Rules for all skills and agents working in this knowledge tree. Read this file before making any changes. This file is self-contained — everything an agent needs to work correctly in this repository is here.

## Language
- All content in the knowledge tree is written in **English**.
- Communication with the user happens in Swedish, but files are always English.

## Where the tree lives
The knowledge tree is this GitHub repository — the structure lives in the **repository root**. All files are `.md` files committed via git with clear English commit messages. Empty folders are kept with a `.gitkeep` file.

## File conventions

### Knowledge files — fixed names, updated in place
`client-info.md`, `brand.md`, `customer-voice.md`, `marketing-strategy.md`, `creative-strategy.md`, `measurement.md`, `client-data-overview.md`, `logbook.md`, `tree-version.md` and this file keep their names. To update one, **commit changes to the same file** — git history is the version history. Never create dated copies of knowledge files.

### Snapshots — dated, immutable
Files in `Audits/`, `Scrapes/`, `Reports/`, `Upload/`, `Client-feedback/` and `_internal-feedback/` are snapshots tied to a date (`YYMMDD`, no time). They are read from, never edited — new ones are added instead.

| Folder | Format | Example |
|---|---|---|
| `Audits/` | `brand-audit-YYMMDD.md` | `brand-audit-260729.md` |
| `Audits/` | `creative-audit-YYMMDD.md` | `creative-audit-260730.md` |
| `Reports/` | `YYMMDD-creative-report-BRANDNAME.md` | `260817-creative-report-gents.md` |
| `Scrapes/` | `YYMMDD-ad-scrape-BRANDNAME.md` | `260729-ad-scrape-gents.md` |
| `Upload/` | `YYMMDD-description.md` | `260729-brandguidelines.md` |
| `Client-feedback/` | `YYMMDD-description.md` | `260805-q3-review-call.md` |
| `_internal-feedback/` | `YYMMDD-description.md` | `260731-overview-drift-note.md` |

Same-day clashes: append a sequence number, e.g. `brand-audit-260729-2.md`.

Uploads are source material (brand guidelines, meeting notes, briefs etc). Knowledge extracted from uploads is written into the knowledge files.

## The hypothesis ledger — Strategy/hypothesis-ledger.md
One row per creative hypothesis: what was predicted, what happened, the verdict and the learning. The **Ad names** column is the join key between the ledger and Meta — `hyp:` is not part of the standard ad name. Rules (the priors gate, cold combinations, write rights) live in the mirror: `_noos-creativeintelligence/testing/hypothesis_ledger_and_priors_gate.md`. Three rules every agent must know:

1. **Only `noos-client-evaluation` writes verdicts and cold markings.** Other flows append hypothesis rows, never judge.
2. **The brief flow must read the ledger and historical performance before generating concepts** — and cold combinations are never proposed without an explicit written justification.
3. **Rejections are training data.** Every design moved to Canva folder 4 (Ej godkända) is logged with the reason; the client's refusal list feeds the next brief's image instruction as negative constraints. The Canva four-folder state machine is specified in `_noos-creativeintelligence/testing/canva_creative_system.md`.

## The production runbook — _claude-data/production-runbook.md
The client's fact sheet for production flows: repo, page_id, ad account, Canva folder IDs, client-specific naming fields, and where the thresholds live. **Facts live in the runbook; rules live in the specification and are always read fresh.** It is a knowledge file (fixed name, updated via commits), not a snapshot.

## The _noos-creativeintelligence folder
`_noos-creativeintelligence/` is a **read-only mirror** of the NOOS Creative Intelligence system (master copy: `creative-intelligence/` in the NOOS config repo) — the shared NOOS methodology for creative testing (triggers, hypothesis architecture, funnel logic, test process, learnings). Use it as reference material when working on strategy, hypotheses and creative.

- **Never edit anything inside this folder.** It is refreshed as a whole by the setup skill; `MIRROR.md` states when the copy was taken and from which version (`VERSION.md` is the system's own version file).
- Learnings from client tests are written to the master copy in the NOOS config repo by the flows that have access to it — never to this local copy.

## The version stamp — _claude-data/tree-version.md
This tree was built from the NOOS knowledge-tree specification as it looked on a particular day. That specification keeps developing, so `_claude-data/tree-version.md` records which version this tree satisfies, plus a history of every update applied to it.

- **Never raise `Config version:` by hand**, and never edit or delete a history row. Only the update flow sets it, and only after the work for that version has actually been done. A version number that says the tree is current when it is not is worse than no number at all.
- **If you notice something missing** — a field you have information for that does not exist here, or a file the rules mention but the tree lacks — that is normal template drift on an older tree. Add the field or file using the current wording, note it in the logbook, and tell the user the tree may be behind. Never rewrite or reorder existing content to match a newer template.
- **Bringing the tree up to date** is `noos-client-configupdate`'s job: it compares this file against the config repo, shows a plan, and applies it after the user confirms. It is the only flow allowed to touch the version stamp.

## Client feedback — Client-feedback/
`Client-feedback/` is the dated record of feedback **from the client** — what they said about the work, the creative, the strategy or the results. One file per occasion: `YYMMDD-description.md` (e.g. `260805-q3-review-call.md`). Snapshots: read, never edited.

Write each entry with these headings, in this order:

- **Date & channel** — when it came in, and how (call, meeting, email, Slack, comment in a shared document).
- **Who** — the named people who gave the feedback, with their roles.
- **What it concerns** — creative, strategy, reporting, process, results, or several.
- **What was said** — the feedback in the client's own words. Verbatim quotes wherever possible; mark anything paraphrased as paraphrased.
- **Our reading** — what we take it to mean. Kept separate from the quotes so the raw record stays raw.
- **Action** — what changes as a result, or `none`.

After writing an entry, check whether it changes the *Client feedback patterns & standing directives* field in `Info/client-info.md`. A repeated theme or a new standing directive belongs there; a one-off remark usually does not. Never summarise away a quote — the entry stays as written.

## Internal feedback — _internal-feedback/
`_internal-feedback/` collects **internal** feedback on this system — the tree, the skills, the processes, the way the work is done. Any skill, agent or user working in this project can submit it by adding a dated markdown file there: `YYMMDD-description.md`. State the source in the file (who or what it came from, and when). Snapshots: read, never edited.

For both folders: logbook entries are required as usual. `Client-feedback/` may change a field status in the overview via `Info/client-info.md`; `_internal-feedback/` never affects the overview.

## Content rules
- Never invent or assume client information. Only record what has actually been collected and verified with a source (client, documents, tools, or user input).
- Fields without collected information keep the placeholder *Not yet collected*. Never delete a field — the field structure defines what information NOOS wants. Do not add new fields on your own.

## After every change
1. Update `client-data-overview.md` so every field's status is current (`[ ]` missing / `[~]` partial / `[x]` collected) and set its `Last updated:` date.
2. Add an entry at the top of `logbook.md`. Entry format: `YYYY-MM-DD · [skill/agent] · files changed · short description`.

## Folder structure
```
<client repo root>/
├── _claude-data/
│   ├── client-data-overview.md
│   ├── logbook.md
│   ├── production-runbook.md
│   ├── tree-version.md
│   └── workinginstructions.md
├── Info/
│   ├── client-info.md
│   ├── brand.md
│   └── customer-voice.md
├── Strategy/
│   ├── marketing-strategy.md
│   ├── creative-strategy.md
│   ├── measurement.md
│   └── hypothesis-ledger.md
├── Audits/
├── Scrapes/
├── Reports/
├── Upload/
├── Client-feedback/
└── _internal-feedback/
```
