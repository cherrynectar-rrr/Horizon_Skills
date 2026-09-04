# Horizon Skills

Reusable, versioned operating procedures for Project Horizon.

This repository improves how Horizon work is executed across repositories. Skills do not create new authority, projects or learning lines; they remain subordinate to the Charter and Thread Protocol in `cherrynectar-rrr/Project_Horizon`.

## Source of Truth

This repository is the **canonical home for active Horizon Skills** after the 2026-09-04 multi-repository cutover.

Historical Skill copies and trial records preserved in `Project_Horizon` are history, not a second live source.

## Operating Rule

Use Skills only when they reduce repeated work, strengthen evidence or improve reliability. Skill maintenance must not become a separate standing workload.

Current routing begins with `horizon-context-sync` v0.6:

`task → owner → canonical repo → local state → execute`

## Current Skill Set

### Adopted — Active

- `horizon-context-sync` — HZN-001 v0.6 — local-first repository/context routing
- `horizon-learning-loop` — v0.2 — Self-Study + Assessment learning loop

### Candidate — Trial

- `status-update` — HZN-002 v0.1 — meaningful-change gate for formal state
- `engineering-debug-loop` — v0.2 — evidence-first root-cause debugging
- `behavior-first-testing` — v0.1 — observable behavior before implementation detail
- `design-grill` — v0.2 — scope decomposition, material decisions and YAGNI check
- `completion-verification` — v0.1 — fresh evidence before success claims
- `change-review` — v0.1 — behavior/spec + engineering/risk review
- `codebase-orientation` — v0.1 — lightweight onboarding into unfamiliar repositories
- `source-grounded-research` — v0.1 — primary-source, contradiction-aware research
- `experiment-design` — v0.1 — baseline/control, measurement and reproducible experiment design

Candidate Skills consume no scheduled study time. They are exercised only when a natural Horizon task matches.

## Portable Format

New or materially revised Skills prefer the open Agent Skills structure:

- YAML frontmatter with `name` and trigger-oriented `description`;
- compact `SKILL.md` core workflow;
- optional `references/`, `scripts/` and `assets/` only when they reduce context or repeated work.

Older Skills migrate opportunistically on their next material revision; no cosmetic rewrite campaign is required.

## External Intake

External skill ecosystems are searched as **method sources**, not bulk-installed.

The latest broad research / intake decision is:

- [`EXTERNAL_SKILL_SCAN_2026-09-04.md`](./EXTERNAL_SKILL_SCAN_2026-09-04.md)

It records what was absorbed, strengthened, deferred and rejected, with provenance.

Full lifecycle, evaluation and external-intake rules live in [`ARCHITECTURE.md`](./ARCHITECTURE.md).
