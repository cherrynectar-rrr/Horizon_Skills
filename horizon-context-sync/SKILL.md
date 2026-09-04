# HZN-001 — horizon-context-sync

Version: 0.6
Status: Adopted — Active
Owner: Horizon Core
Last Updated: 2026-09-04

## Purpose

Establish the **minimum authoritative Project Horizon context** required before important work in the multi-repository ecosystem.

The Skill exists to prevent:

- planning from stale chat memory;
- reading more repositories than the task requires;
- opening the wrong canonical state after the multi-repo split;
- role / write-boundary leakage;
- duplicated status truth;
- treating old strategy as current execution state;
- presenting mutable external facts as current without verification.

## Core Rule

**Route first, read local state first, expand context only when the task requires it.**

Default flow:

`task → owner → canonical repo → local STATUS → execute`

Escalate context only when needed:

`local STATUS → MASTER_STATUS → strategy / protocol / charter / external sources`

Do not invert this order by loading the whole Horizon control stack before routine specialist work.

## Operating Model

- **Horizon Core = Explore + Decide & Coordinate**
- **Specialist Threads = Execute**

`cherrynectar-rrr/Project_Horizon` is the control plane.

Canonical repository routing is defined by:

`Project_Horizon/00_Project_Control/REPOSITORIES.md`

Repository location does not grant authority. Authority remains defined by the Charter and Thread Protocol.

## Common Task Routing

| Task / owner | Canonical state |
| --- | --- |
| Horizon-wide decision | `Project_Horizon/00_Project_Control/MASTER_STATUS.md` |
| Python | `Horizon_Learning/Python/STATUS.md` |
| C++ | `Horizon_Learning/CPP/STATUS.md` |
| Linux | `Horizon_Learning/Linux/STATUS.md` |
| Algorithm | `Horizon_Learning/Algorithm/STATUS.md` |
| Embedded | `Horizon_Learning/Embedded/STATUS.md` |
| Qingdao competition | `Horizon_projects/2026_Qingdao_Agri_Data_Competition/STATUS.md` |
| Academic Operations | `Horizon_Academic/Academic_Operations/STATUS.md` |
| Finance | `Horizon_Life/Finance/STATUS.md` |
| Nutrition & Recovery | `Horizon_Life/Nutrition_Recovery/README.md` until STATUS initialization |
| Career / Internship | `Project_Horizon/09_Career/STATUS.md` until later migration decision |
| Earth Flywheel | `Earth_Flywheel/` project-local state / evidence |
| Skills | `Horizon_Skills/` |

If a task does not match this table cleanly, consult the Repository Registry rather than guessing.

## Triggers

Use HZN-001 before:

- important Horizon planning / decisions;
- cross-thread coordination;
- route, priority, competition, research, study-abroad or career decisions;
- governance-sensitive repository writes;
- specialist work where current state materially affects execution;
- tasks where chat context may be stale or conflicting.

## Do Not Trigger a Full Sync When

Do not expand into a full control-plane sync for:

- casual conversation;
- tiny isolated exercises;
- routine specialist work whose local STATUS is sufficient;
- work already operating from freshly fetched authoritative state in the same conversation;
- tasks with no state, priority or authority dependency.

## Required Reads by Role

### Specialist Thread — default local-first path

1. Read the specialist's canonical local `STATUS.md`.
2. Execute the task.

Read `MASTER_STATUS.md` only if the task involves:

- priority or capacity;
- another thread;
- activation / pause / promotion;
- project scope or competition route;
- a Core dependency;
- a conflict between local and Horizon-wide state.

Read README / course architecture only when the task needs durable scope or learning structure.

Read `THREAD_PROTOCOL.md` / Charter only when authority, write ownership or governance is unclear.

Write only the specialist's own authorized state/workspace.

### Horizon Core

1. Read `MASTER_STATUS.md`.
2. Read only the canonical Specialist / project state that can materially change the decision.
3. Read strategy only when prior route research, alternatives or unresolved hypotheses matter.
4. Read Protocol / Charter only when governance, authority or shared infrastructure matters.
5. Verify mutable external facts when material.

Core must not scan every repository by default.

## Task Classification

Internally classify the request as one or more of:

- routine execution;
- cross-thread coordination;
- Explore;
- Decide & Coordinate;
- evidence intake;
- external-current-fact question;
- repository write.

Then resolve:

- owner;
- canonical repository;
- minimum required state;
- write boundary;
- whether external freshness is needed;
- whether a Core decision is needed.

## Conflict Resolution

If chat memory, user recollection and GitHub disagree:

- user-provided new information may be treated as evidence;
- do not silently rewrite formal state;
- use current canonical GitHub state for governance / execution truth;
- route a material discrepancy through the correct owner.

If two repository copies disagree during migration, use the repository designated canonical in `REPOSITORIES.md`. Legacy `Project_Horizon` execution folders are not a second live source after cutover.

## External Freshness Check

Ask:

> Does the answer depend on information that can change?

Examples: admissions, APS, visa rules, funding, competition dates, software versions, named labs / professors, jobs, salaries, employment policy and market conditions.

If yes, verify current reliable sources before presenting the claim as current.

## Repository Write Rule

Before writing:

1. confirm the canonical owner;
2. fetch the latest target and SHA;
3. make the minimum evidence-justified change;
4. do not record a plan as completion;
5. do not create duplicate canonical state;
6. fail closed if ownership is unclear.

For STATUS / MASTER writes, apply the meaningful-change rule from `THREAD_PROTOCOL.md` and HZN-002 where applicable.

## Human-Only Boundary

Personal showcase/profile repositories maintained by the user are outside Horizon's AI execution surface.

Do not read, edit, review, synchronize or write to them unless the user explicitly revokes that boundary.

## Compact Internal Context Packet

Use only when the task is complex enough to benefit:

```text
Role:
Task Type:
Canonical Owner / Repo:
Authoritative State:
Relevant Priority / Constraints:
Allowed Writes:
External Freshness Needed: Yes/No
Needs Core Decision: Yes/No
Unknowns That Matter:
```

Do not show this packet unless it improves the user's understanding.

## Success Test

HZN-001 succeeds when:

- the correct canonical state is reached quickly;
- unnecessary repositories are not read;
- local specialist work usually begins from one STATUS read;
- MASTER is loaded only when Horizon-wide context matters;
- write ownership remains clear;
- mutable facts are verified when needed;
- legacy copies do not become competing truth.

## Anti-Patterns

Do not:

- recite the Charter every session;
- open MASTER for every tiny specialist question;
- scan all Horizon repositories "just in case";
- treat legacy monorepo execution copies as live state;
- create status updates merely because a conversation occurred;
- let Explore ideas silently become execution decisions;
- build a routing dashboard or message bus before real evidence requires it;
- fabricate missing state to keep moving.

## Version Status

- **Current adopted version:** v0.6 — Multi-Repository Local-First Edition.
- **Previous adopted version:** v0.5 — Horizon Core Edition, preserved in Git history.
- v0.6 is an operating-architecture compatibility update authorized by the user's 2026-09-04 Horizon Efficiency Pass. It changes repository routing and default read depth, not Horizon authority boundaries.

## Change Log

### v0.6 — 2026-09-04 — Adopted

- added multi-repository canonical routing;
- made Specialist startup explicitly local-STATUS-first;
- made MASTER conditional rather than default for routine specialist work;
- added task → owner → repo routing;
- added legacy-copy conflict rule after control-plane cutover;
- added human-only showcase boundary;
- reduced unnecessary Charter / Protocol reads;
- retained external freshness and write-boundary protections.

### v0.5 — 2026-08-29 — Adopted historical version

- migrated governance from Voyage Room + Main Control to Horizon Core + Specialist Threads;
- removed live Voyage–Control bridge routing;
- established role-based minimum reads and fresh-state reuse.

Earlier versions and trial evidence remain preserved in Git history and historical Project Horizon records.
