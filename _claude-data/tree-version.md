# Knowledge Tree Version — Trendlo

State of this knowledge tree relative to the NOOS config repo. The update flow reads the two machine-readable lines below — keep them in exactly this format, one per line, no extra words.

Config version: 2.1.0
Last checked: 2026-08-19

`Config version` = the config version this tree is known to satisfy.
`Last checked` = the last time the tree was compared against the config repo, whether or not anything was applied.

## History

Newest entries first. One row per applied update (or per check that found nothing to do).

| Version | Applied | By | What happened |
|---|---|---|---|
| 2.1.0 | 2026-08-19 | noos-client-setup | Tree created from this config version. |

## Notes

- This file is a ledger: rows are appended, never edited or removed.
- If a row says `skipped` or `manual pending`, the work is not done — it is waiting for a human. Do not stamp a higher version until it is closed.
- Never raise `Config version` by hand. It is set by the update flow after the actions for that version have actually been applied.
