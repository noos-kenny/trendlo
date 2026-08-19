# Canva Creative System — four folders as a state machine

How NOOS produces, reviews and releases static creative in Canva. The client's Canva project holds four folders, and **a design's folder IS its status** — there is no separate status list, no spreadsheet column, no naming suffix for state. Moving a design is the state transition.

## The four folders

| # | Folder | State | Rules |
|---|---|---|---|
| 1 | **Mallar** (Templates) | Source | The client's template library. **Never touched.** Production always starts by copying from here — never by editing here. |
| 2 | **Utkast** (Drafts) | Awaiting review | Assembled copies land here. Nothing leaves except by human review. |
| 3 | **Godkända** (Approved) | Released | A move into this folder is the **trigger** for export and Meta upload (see `noos-client-adsetup`). |
| 4 | **Ej godkända** (Not approved) | Training data | Rejected designs. **Never deleted.** Every move here is logged with the reason. |

State = place. If you cannot tell a design's status from its folder, the system is being misused.

## Assembly rules (folder 1 → folder 2)

1. **`copy-design` from folder 1.** Always copy — **never generate**. `generate-design` is unreliable with the brand kit and produces off-brand output.
2. **`edit-design` on the copy only:** `replace_text` for copy, `update_fill` for photo swaps.
3. **Never add new text elements to a production copy.** `add_text` produces non-brand fonts. If a template lacks a text slot the concept needs, that is a template problem — raise it, don't patch it.
4. **Never touch the logo in a copy.**
5. **Brand templates (Canva's feature) are not used.** Written off — publish has corrupted designs. The template library in folder 1 is the only template source.
6. **Set the design title to the Winberg name** (per `naming_conventions.md`). The name sits **in the design's title**, not only in the folder. The title is what `noos-client-adsetup` validates and carries into Meta as the ad name.
7. **`move-item-to-folder` to folder 2 (Utkast).** Assembly ends here. Approval is human.

## Folder 4 is training data

Every design moved to **Ej godkända** is logged with the reason for rejection. The rejections accumulate into the client's **refusal list** — recurring reasons a client says no. That list is fed into the next brief's image instruction as **negative constraints**, so the same rejection never has to happen twice.

- The mechanism (log reason → refusal list → negative constraints in next brief) is standard and lives here.
- The **content** of the refusal list is client-specific and lives in the client's knowledge tree — never in this repo.
- Folder 4 is never emptied. Deleted rejections are deleted learnings.

## What lives where

| Standard (this repo) | Client-specific (client's knowledge tree) |
|---|---|
| The four-folder state machine | The client's actual Canva project & folder IDs |
| Assembly rules and tool constraints | Template anatomies (which slots each template has) |
| The refusal-list mechanism | The refusal list itself |
| Winberg-name-in-title rule | The case's picklist values |
