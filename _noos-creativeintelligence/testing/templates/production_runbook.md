# Production Runbook — {CLIENT_NAME}

One source, no parallel truths. This file holds everything a session needs to run production flows for this client. It is created by `noos-client-setup` and updated when the facts change — it is a knowledge file (fixed name, updated via commits), not a snapshot.

## Rule zero

**Skills read the specification fresh.** Nothing in this runbook overrides the NOOS spec (`_claude-data/workinginstructions.md`, the CI mirror in `_noos-creativeintelligence/`). The runbook holds the client's FACTS; the spec holds the RULES.

## Project

| Field | Value |
|---|---|
| Client | {CLIENT_NAME} |
| GitHub repo | {GITHUB_REPO} |
| Chat language | Swedish · Tree content: English |

## Meta

| Field | Value |
|---|---|
| page_id | {PAGE_ID} — **verify against a live ad before first publish** (mandatory first step in `noos-client-adsetup`) |
| Ad account | {AD_ACCOUNT_ID} |
| Meta Ads Library | {ADS_LIBRARY_LINK} |

## Canva

Four-folder state machine per `_noos-creativeintelligence/testing/canva_creative_system.md`.

| Folder | ID |
|---|---|
| 1 Mallar | {CANVA_FOLDER_TEMPLATES} |
| 2 Utkast | {CANVA_FOLDER_DRAFTS} |
| 3 Godkända | {CANVA_FOLDER_APPROVED} |
| 4 Ej godkända | {CANVA_FOLDER_REJECTED} |

## Client-specific naming

Custom fields beyond the standard schema (documented in the Naming Convention sheet's Custom fields tab):

| Prefix | Meaning | Owner | Date |
|---|---|---|---|
| *Not yet collected* | | | |

## Thresholds & references

| Field | Where it lives |
|---|---|
| Spend threshold (cold markings) | `Strategy/measurement.md` |
| Refusal list (negative constraints) | client knowledge tree |
| Template anatomies & negative space | client knowledge tree |
| Hypothesis ledger | `Strategy/hypothesis-ledger.md` |
