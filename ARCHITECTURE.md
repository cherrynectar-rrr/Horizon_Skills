# Project Horizon — Skills Architecture

Last Updated: 2026-09-04
Owner: Horizon Core
Status: Active Architecture — Conservative Expansion

## Purpose

A **Horizon Skill** is a reusable, versioned operating procedure for a recurring task pattern that is stable enough to execute consistently.

> Thread = who owns the work.  
> Skill = how a recurring type of work is performed.  
> Status = what is currently true.  
> Strategy = what may be worth doing.  
> Evidence = what actually happened.

Skills compress mature methods. They do **not** create new execution lines.

## Governance

All Skills remain subordinate to:

1. `cherrynectar-rrr/Project_Horizon/00_Project_Charter/Project_Horizon_Charter_v4.0.md`
2. `cherrynectar-rrr/Project_Horizon/00_Project_Control/THREAD_PROTOCOL.md`
3. `cherrynectar-rrr/Project_Horizon/00_Project_Control/MASTER_STATUS.md`
4. role-specific authority and evidence

A Skill never grants authority the invoking role does not already possess.

## Design Principles

A useful Skill should:

- read the minimum sufficient context;
- distinguish verified state, user evidence, external facts and inference;
- produce a predictable result without unnecessary ceremony;
- preserve Specialist / Core boundaries;
- reuse fresh state when safe;
- verify mutable external facts when material;
- reduce total effort rather than create maintenance for its own sake.

A Skill is not a new thread, governance layer, hidden memory store, generic prompt collection, or excuse to automate a process before it is understood.

## Lifecycle

- **Draft** — proposed procedure, no shared-use claim.
- **Candidate / Trial** — exercised on real tasks; record only meaningful value, failure or friction.
- **Adopted** — explicitly approved by Horizon Core as the preferred shared procedure for the task pattern.
- **Deprecated** — superseded by a newer adopted version or governance change.

Adoption is version-pinned. Editing a working file does not silently replace an adopted version.

## Current Skills

### Adopted — Active

- `horizon-context-sync` — HZN-001 v0.5
- `horizon-learning-loop` — v0.2

### Candidate — Trial

- `status-update` — HZN-002 v0.1
- `engineering-debug-loop` — v0.1
- `behavior-first-testing` — v0.1
- `design-grill` — v0.1

### Frozen numbered backlog

- HZN-003 — evidence-intake
- HZN-004 — strategic-route-audit
- HZN-005 — opportunity-filter

The 2026-09-04 engineering micro-skill trials do not consume or unfreeze those numbered IDs.

## Physical Location

`Horizon_Skills` is now the **canonical active home** for Horizon Skills.

The old path `Project_Horizon/00_Strategy/Voyage_Room/skills/` is a migration-era historical copy only. It must not be edited as a second live Skills library after cutover.

## Success Test

The Skills layer is useful only if it measurably reduces one or more of:

- repeated setup instructions;
- unnecessary repository reads;
- unauthorized writes;
- stale-state decisions;
- meaningless STATUS churn;
- debugging guesswork;
- avoidable implementation rework;
- user coordination burden.

If a Skill adds more maintenance than it removes, simplify, merge or remove it.
