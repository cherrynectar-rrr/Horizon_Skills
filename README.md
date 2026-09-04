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

- `adaptive-guided-learning` — v0.1 — high-efficiency guided learning with dynamic step size and anti-fragmentation rules
- `status-update` — HZN-002 v0.1 — meaningful-change gate for formal state
- `engineering-debug-loop` — v0.2 — evidence-first root-cause debugging
- `behavior-first-testing` — v0.1 — observable behavior before implementation detail
- `design-grill` — v0.2 — scope decomposition, material decisions and YAGNI check
- `completion-verification` — v0.1 — fresh evidence before success claims
- `change-review` — v0.1 — behavior/spec + engineering/risk review
- `codebase-orientation` — v0.1 — lightweight onboarding into unfamiliar repositories
- `source-grounded-research` — v0.1 — primary-source, contradiction-aware research
- `experiment-design` — v0.1 — baseline/control, measurement and reproducible experiment design
- `nutrition-planning` — v0.1 — low-friction campus / budget / everyday nutrition planning with a strict medical boundary
- `habit-change` — v0.1 — small behavior-change experiments using environment, action / coping plans and minimal monitoring

Candidate Skills consume no scheduled study time. They are exercised only when a natural Horizon task matches.

## Portable Format

New or materially revised Skills prefer the open Agent Skills structure:

- YAML frontmatter with `name` and trigger-oriented `description`;
- compact `SKILL.md` core workflow;
- optional `references/`, `scripts/` and `assets/` only when they reduce context or repeated work.

Older Skills migrate opportunistically on their next material revision; no cosmetic rewrite campaign is required.

## External Intake

External skill ecosystems are searched as **method sources**, not bulk-installed.

Current intake records:

- [`EXTERNAL_SKILL_SCAN_2026-09-04.md`](./EXTERNAL_SKILL_SCAN_2026-09-04.md) — broad engineering / research intake;
- [`LIFE_HEALTH_SKILL_INTAKE_2026-09-05.md`](./LIFE_HEALTH_SKILL_INTAKE_2026-09-05.md) — selective life / health intake.

The life / health intake deliberately keeps community workflow ideas separate from health authority. Quantitative or mutable health guidance must be verified from reliable current sources when it matters.

Full lifecycle, evaluation and external-intake rules live in [`ARCHITECTURE.md`](./ARCHITECTURE.md).
