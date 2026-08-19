# NOOS Creative Intelligence — Version

**Current version: 1.1**
Released: 2026-08-17

## Roles

- **This repo (`noos-creativeintellience`) is the development environment.** All changes to the Creative Intelligence system are made here first.
- **`noos-kenny/claude-configs` → `creative-intelligence/` is the released copy.** Client repos mirror from there (via `noos-client-setup`), never from this repo directly.

## How versioning works

- The version number is bumped **at release time**, in this file, and the release is copied to the config repo.
- **Minor bump (1.0 → 1.1):** content additions and refinements — new learnings, expanded modules, updated picklists or examples.
- **Major bump (1.0 → 2.0):** changes to the method itself — trigger taxonomy, hypothesis format, test process, or folder structure.
- Every release gets a line in `logbook.md` describing what changed.

## Release workflow

1. Work is committed to THIS repo continuously as it happens.
2. **Nothing is released automatically.** Only when explicitly asked — e.g. "pusha senaste versionen till config-repot" — is a release made.
3. A release means: bump the version in this file → commit here → copy the full current state of this repo into `claude-configs/creative-intelligence/` (one commit there) → logbook entries in both places.

## Version history

| Version | Date | Summary |
|---|---|---|
| 1.1 | 2026-08-17 | 15-trigger taxonomy as canon (Cluster 5: Scarcity/Urgency, Reciprocity, Endowment; funnel homes LA=TOF, C&A=BOF, C&C=RT/BOF). Naming: menu principle, `bar:` optional by default, trig picklist = the 15 canonical slugs, formal deprecations. New: Canva four-folder state machine, hypothesis ledger + priors gate (+ template), image briefing principle, production runbook template, Reports convention. Released to `claude-configs/creative-intelligence/`. |
| 1.0 | 2026-08-05 | First versioned release: method modules 00–10, testing framework (process, Winberg naming conventions, templates), learnings structure. Released to `claude-configs/creative-intelligence/`. |
