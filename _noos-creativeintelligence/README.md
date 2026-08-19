# NOOS Creative Intelligence

This repository is the **development environment and master copy** of how NOOS tests and develops creative for paid social. All changes are made HERE first. On explicit request ("pusha senaste versionen till config-repot") the current state is released to `noos-kenny/claude-configs` → `creative-intelligence/` — the released copy that client repos mirror from. `VERSION.md` holds the current version. It answers three questions:

| Folder | Question it answers | Changes how often? |
|---|---|---|
| `method/` | **What do we believe?** The methodology: triggers, hypotheses, funnel logic, Nordic psychology, anti-patterns. | Rarely — deliberate updates only. |
| `testing/` | **How do we test?** The process from hypothesis to decision, naming conventions, templates. | Rarely. |
| `learnings/` | **What have we learned?** Conclusions that hold over time, per trigger. | Continuously — grows with every test. |

`logbook.md` tracks what changed in this repo and when. `VERSION.md` holds the current version and the release workflow.

## How to find your way

- New to the system? Start with `method/00_overview.md`, then `method/01_creative_intelligence_system.md`.
- Writing a hypothesis? `method/04_hypothesis_architecture.md` + `testing/templates/hypothesis_card.md`.
- Choosing triggers for a market or vertical? `method/05_nordic_market_psychology.md` and `method/06_vertical_adaptations.md`.
- Naming an ad? `testing/naming_conventions.md`.

## How client projects use this repo

Each NOOS client has their own knowledge repo. When a client is set up (via the `noos-client-setup` flow), the RELEASED copy (`creative-intelligence/` in `claude-configs`) is mirrored into the client repo under:

```
_noos-creativeintelligence/
```

together with a `MIRROR.md` stating when the copy was taken and from which version. Clients therefore always get the latest RELEASE — not unreleased work in this repo.

**Two rules keep this sane:**

1. **The client copy is read-only.** Nothing is ever edited inside `_noos-creativeintelligence/` in a client repo.
2. **Learnings flow back here.** Insights from client tests are written to `learnings/` in THIS repo — never to the client's copy. One source of truth.

## Rules for this repo

- **No client-specific data.** Client data lives in the client's own repo. This is the shared NOOS brain.
- **Release only on request.** Work happens here continuously, but nothing is pushed to the config repo until explicitly asked. A release = sync to `claude-configs/creative-intelligence/` + version bump in `VERSION.md` + logbook entry.
- **One file = one topic.** A project that needs the hypothesis format fetches `method/04_hypothesis_architecture.md`, nothing else.
- **Language: English.**
- **Every material change** gets a line in `logbook.md` and, where relevant, a note in the file's own `## Changelog`.
