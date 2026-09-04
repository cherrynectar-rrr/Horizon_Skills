# HZN-001 — horizon-context-sync

Version: 0.5
Status: Adopted — Active
Owner: Horizon Core
Last Updated: 2026-08-29

## Purpose

Establish the **minimum authoritative Project Horizon context** needed before important work, while preserving role boundaries and avoiding unnecessary repository reads.

This Skill exists to prevent:

- planning from stale chat memory;
- reading more of the repository than the task requires;
- role / write-boundary leakage;
- treating hypotheses or old strategic material as current approved state;
- presenting mutable external facts as current without verification;
- creating governance ceremony that costs more than it saves.

## Version Status

- **Current adopted version:** HZN-001 v0.5 — Horizon Core Edition.
- **Historical adopted baseline:** HZN-001 v0.4, pinned at adoption-time blob SHA `ff2d8af44fd346e20ed6d9e255be4ff9a48e8f78` under `CTV-20260828-04`.
- v0.5 supersedes v0.4 for current operation under Charter v4.0 / `THREAD_PROTOCOL.md` v2.0.
- Later material edits are candidate changes only until Horizon Core explicitly adopts a new version.

## Triggers

Use this Skill before:

- important Horizon planning or decisions;
- cross-thread coordination;
- route / priority / competition / research / study-abroad / career decisions;
- governance-sensitive repository writes;
- specialist work where current Horizon state materially affects execution;
- tasks where chat context may be stale or conflicting.

## Do Not Trigger When

Do not run a full sync for:

- casual conversation;
- a tiny isolated exercise unrelated to Horizon state;
- simple explanations with no priority / authority / state dependency;
- work already operating from freshly fetched authoritative state in the same conversation, unless a material update may have occurred.

## Roles

Horizon now has two operating layers:

1. **Horizon Core / 核心舱 = Explore + Decide & Coordinate**
2. **Specialist Threads = Execute**

The former Voyage Room / Main Control split and the Voyage–Control bridge are historical. Do not use the frozen bridge files for new top-level communication.

## Authority Order

Resolve conflicts in this order:

1. `00_Project_Charter/Project_Horizon_Charter_v4.0.md`
2. `00_Project_Control/THREAD_PROTOCOL.md`
3. `00_Project_Control/MASTER_STATUS.md`
4. relevant Core strategic analyses / formal Core decisions
5. relevant specialist `STATUS.md`
6. evidence / artifacts
7. chat memory as supporting context only

A lower layer must not silently override a higher layer.

## Required Reads by Role

### Horizon Core

For important Core work, read:

1. `00_Project_Control/MASTER_STATUS.md`;
2. only the specialist `STATUS.md` files that can materially affect the task;
3. relevant strategic analyses when prior research, unresolved hypotheses or route history matter;
4. Charter / `THREAD_PROTOCOL.md` only when governance, authority, write ownership or shared infrastructure is material;
5. current external sources when the decision depends on mutable real-world facts.

Do **not** read every thread or the frozen Voyage–Control bridges by default.

Write boundary:

- Core-owned control / governance files;
- `MASTER_STATUS.md`;
- Core-owned strategic analyses, including preserved strategy material under `00_Strategy/Voyage_Room/` except frozen historical bridge files;
- other files explicitly assigned to Core.

Never write a specialist's `STATUS.md` on that specialist's behalf.

### Specialist Thread

For important specialist work, read:

1. that specialist's own `STATUS.md`;
2. `MASTER_STATUS.md` only when the task involves priority, another thread, capacity conflict, activation state, competition / project route or a Core dependency;
3. strategic analyses only when the specialist's approved scope genuinely depends on long-term route context;
4. current external sources when mutable facts are material.

Write boundary:

- the specialist's own `STATUS.md`;
- operational workspaces / files explicitly authorized for that specialist.

A specialist must not change long-term route, cross-thread priority or another thread's state. Material conflicts escalate as **Needs Core Decision**.

## External Freshness Check

After repository sync, ask:

> Does the answer depend on information that can change?

Examples include admissions rules, APS / visa / immigration procedures, scholarships, programme fees, competition dates, software versions, named labs / professors, job openings, salaries, employment policy and market conditions.

If yes, verify current reliable external sources before presenting the fact as current.

Old strategic documents may preserve useful reasoning, but they do not substitute for fresh verification.

## Procedure

### Step 1 — Classify the task

Classify as one or more of:

- routine execution;
- cross-thread coordination;
- Explore;
- Decide & Coordinate;
- evidence intake;
- external-current-fact question;
- repository write.

### Step 2 — Determine authority

Internally identify:

- current role;
- allowed decision scope;
- allowed write scope;
- whether a Core decision or governance check is required.

If authority or write ownership is unclear, stop before writing and consult the Charter / `THREAD_PROTOCOL.md`.

### Step 3 — Fetch minimum authoritative state

Use the role rules above.

Read only files that can materially change the answer or write boundary.

### Step 4 — Resolve conflicts

If chat memory, user recollection and GitHub disagree:

- preserve new user evidence as evidence;
- do not silently rewrite official state;
- use the latest formal GitHub state for current governance / execution state;
- route material discrepancies through the proper owner.

### Step 5 — Check external freshness

If mutable external facts matter, verify them before high-impact conclusions.

### Step 6 — Build a compact internal Context Packet

```text
Role:
Task Type:
Authoritative State:
Relevant Priorities / Constraints:
Affected Threads:
Allowed Writes:
External Freshness Needed: Yes/No
Needs Core Decision: Yes/No
Unknowns That Matter:
```

Do not show this packet unless it helps explain a decision or limitation.

### Step 7 — Execute the user's actual task

The Skill is a preflight, not the deliverable.

The visible response should answer the real task rather than narrating governance machinery.

## Output Contract

Success means the invoking workflow has:

- fresh role-correct Horizon context;
- only the necessary authoritative state;
- clear priority / constraint context;
- a clear write boundary;
- identified external facts requiring fresh verification;
- identified unresolved conflicts or Core decisions.

## Verification Checklist

Before proceeding, verify:

- [ ] Correct current role identified
- [ ] Correct current Charter / Protocol model used
- [ ] Minimum sufficient authoritative files read
- [ ] Frozen Voyage–Control bridges not used as live state
- [ ] No unnecessary full-repository scan
- [ ] Hypotheses / old recommendations not mistaken for approved state
- [ ] Write ownership respected
- [ ] Mutable external facts marked for verification
- [ ] Material conflicts surfaced rather than overwritten

## Stop / Escalation Conditions

Stop or escalate when:

- a requested write violates ownership;
- a specialist is being asked to change long-term route or cross-thread priority;
- specialist state conflicts materially with `MASTER_STATUS.md`;
- current evidence is insufficient for a high-impact decision;
- external rules are time-sensitive but cannot be verified;
- required repository / tool access fails and missing state is essential;
- a Skill change would silently expand authority or activate new work.

## Trial Evidence

Historical v0.1–v0.4 evidence remains in:

`00_Strategy/Voyage_Room/skills/horizon-context-sync/TRIAL_LOG.md`

v0.5 adoption evidence is preserved in:

`00_Strategy/Voyage_Room/skills/horizon-context-sync/TRIAL_LOG_V0.5.md`

Trial 005 validated Horizon Core behavior under the two-layer governance model. Trial 006 validated Specialist-side clean-state behavior without artificial STATUS churn. GitHub does not expose chat-side read telemetry; that limitation is explicitly preserved in the Trial 006 record rather than inferred away.

## Anti-patterns

Do not:

- recite the Charter every time;
- treat memory as source of truth;
- read all threads "just in case";
- use frozen bridge files as live mailboxes;
- write a STATUS update merely because a conversation happened;
- let Explore ideas automatically become execution decisions;
- let Skill maintenance become a new standing workload;
- fabricate missing state to keep the workflow moving.

## Change Log

### v0.5 — 2026-08-29 — Adopted

- Migrated from the retired Voyage Room + Main Control model to **Horizon Core + Specialist Threads**.
- Updated authority root from Charter v3.0 to Charter v4.0.
- Removed live Voyage–Control bridge reads and old cross-role Trial Log routing machinery.
- Simplified the Context Packet and role-based minimum-read rules.
- Replaced `Needs Master Decision` language with `Needs Core Decision`.
- Split historical v0.1–v0.4 Trial evidence from v0.5 adoption evidence.
- Validated one real Horizon Core use and one real Algorithm Specialist invocation under the two-layer model.
- Preserved the evidence limitation that chat-side read telemetry is not independently visible in GitHub.

### v0.4 — 2026-08-28 — Adopted historical baseline

- First version adopted across Horizon under `CTV-20260828-04`.
- Proven across Voyage Room, Main Control and Algorithm Specialist use.
- Historical adopted artifact pinned by blob SHA.

Earlier v0.1–v0.3 changes remain preserved in Git history and the historical `TRIAL_LOG.md`.
