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
- improve evidence quality or execution reliability;
- reduce total effort rather than create maintenance for its own sake.

A Skill is not a new thread, governance layer, hidden memory store, generic prompt collection, or excuse to automate a process before it is understood.

## Portable Skill Format

For **new or materially revised Skills**, prefer the open Agent Skills shape:

```text
skill-name/
├── SKILL.md
├── references/   # optional, loaded only when needed
├── scripts/      # optional deterministic helpers
└── assets/       # optional templates / output assets
```

`SKILL.md` should normally begin with YAML frontmatter containing at least:

- `name` — stable identifier;
- `description` — what the Skill does **and when it should trigger**.

Optional metadata may record version, lifecycle state, owner or compatibility.

Use **progressive disclosure**:

1. routing metadata stays small;
2. `SKILL.md` contains the core workflow;
3. large references, scripts and templates are loaded only when a triggered task needs them.

Do not create `references/`, `scripts/` or `assets/` merely to imitate a format. A one-file Skill is preferred when one file is enough.

Older Horizon Skills without frontmatter are migrated opportunistically on their next material revision; no cosmetic rewrite campaign is required.

## External Skill Intake

External Skill repositories are **idea and implementation sources, not packages to install blindly**.

Use this trust order when importing ideas:

1. open specification / official platform documentation;
2. first-party platform repositories and maintained public examples;
3. strong engineering repositories with inspectable methods and compatible licenses;
4. community collections as idea sources only, with important claims independently checked.

Before absorbing an external Skill, ask:

- Does it solve a recurring Horizon problem?
- Is it distinct from an existing Horizon Skill?
- What failure or repeated cost does it prevent?
- Does it depend on unavailable agents, tools or editor-specific behavior?
- Are scripts / commands safe and necessary?
- Is provenance / license understood for non-trivial adaptation?
- Can Horizon test the method on a natural real task?

Never import executable scripts, commands or tool permissions merely because an upstream Skill includes them. Inspect dependencies, side effects and capability first.

The latest broad intake record is:

`EXTERNAL_SKILL_SCAN_2026-09-04.md`

## Lifecycle

- **Draft** — proposed procedure, no shared-use claim.
- **Candidate / Trial** — exercised on natural real tasks; record only meaningful value, failure or friction.
- **Adopted** — explicitly approved by Horizon Core as the preferred shared procedure for the task pattern.
- **Deprecated** — superseded by a newer adopted version or governance change.

Adoption is version-pinned. Editing a working file does not silently replace an adopted version.

Popularity of the source repository is not adoption evidence.

## Evaluation Rule

Prefer **real-task trials** over manufactured bureaucracy.

A Candidate should show at least one of:

- a failure / false claim / rework cycle it prevented;
- a measurable reduction in repeated setup or context cost;
- stronger test, debug, review, research or experiment evidence;
- a safer or clearer decision boundary;
- a meaningful improvement over the same workflow without the Skill.

When comparison is practical, compare **with-Skill vs without-Skill** or previous-version behavior. Consider quality, reliability and overhead together; a method that improves output slightly while doubling ceremony may still be a bad Horizon Skill.

Do not create artificial milestones merely to finish a Trial.

## Current Skills

### Adopted — Active

- `horizon-context-sync` — HZN-001 v0.6
- `horizon-learning-loop` — v0.2

### Candidate — Trial

- `status-update` — HZN-002 v0.1
- `engineering-debug-loop` — v0.2
- `behavior-first-testing` — v0.1
- `design-grill` — v0.2
- `completion-verification` — v0.1
- `change-review` — v0.1
- `codebase-orientation` — v0.1
- `source-grounded-research` — v0.1
- `experiment-design` — v0.1

### Frozen numbered backlog

- HZN-003 — evidence-intake
- HZN-004 — strategic-route-audit
- HZN-005 — opportunity-filter

The engineering / research micro-skill trials do not consume or unfreeze those numbered IDs.

## Deliberately Deferred Patterns

Potentially useful later, but not standing Horizon Skills today:

- security review for real network / auth / trust-boundary projects;
- performance profiling for demonstrated bottlenecks;
- user-facing documentation architecture when projects gain real external users;
- worktree / merge / release workflows when collaboration creates the need;
- full systematic-literature-review machinery when an actual research question justifies that rigor;
- large multi-agent councils, project-management stacks or universal quality playbooks.

A future need should activate the smallest useful method, not the largest available framework.

## Physical Location

`Horizon_Skills` is the **canonical active home** for Horizon Skills.

The old path `Project_Horizon/00_Strategy/Voyage_Room/skills/` is migration-era history only and must not be edited as a second live Skills library.

## Success Test

The Skills layer is useful only if it measurably reduces or improves one or more of:

- repeated setup instructions;
- unnecessary repository reads;
- unauthorized writes;
- stale-state decisions;
- meaningless STATUS churn;
- debugging guesswork;
- unsupported completion claims;
- avoidable implementation rework;
- unsafe codebase onboarding;
- weak source grounding;
- uninterpretable experiments;
- user coordination burden.

If a Skill adds more maintenance than it removes, simplify, merge, defer or remove it.
