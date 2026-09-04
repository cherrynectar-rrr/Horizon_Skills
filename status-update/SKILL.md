# HZN-002 — status-update

Version: 0.1
Status: Candidate — Trial
Owner: Horizon Core
Last Updated: 2026-08-29

## Purpose

Standardize **when and how Project Horizon formal state is updated** so STATUS / MASTER_STATUS remain concise, factual, evidence-based and role-correct.

This Skill exists to prevent:

- writing formal state for ordinary conversation or tiny exercises;
- turning plans or intentions into completed work;
- overwriting useful prior state when only one section changed;
- using the wrong owner / target file;
- creating STATUS churn for communication-only events;
- losing evidence links for real milestones;
- letting terminology drift silently after governance changes.

The Skill is an **update gate and procedure**. It does not create new write authority.

## Triggers

Use this Skill when a Horizon event may justify a formal state change, including:

- milestone completion;
- blocker appearance / change / resolution;
- learning or project route change;
- competition / application / project result;
- materially changed next milestone;
- activation / pause / priority change;
- a meaningful Specialist issue requiring Horizon Core judgment;
- a Core decision that changes approved project state.

## Do Not Trigger When

Do not update formal state for:

- ordinary conversation;
- tiny exercises that do not change the milestone state;
- speculative ideas or plans;
- Skill tests whose only result is that the Skill ran;
- communication-only events that do not independently meet the meaningful-update threshold;
- cosmetic wording cleanup with no state value, unless bundled into the next meaningful update.

## Authority Order

1. `Project_Horizon/00_Project_Charter/Project_Horizon_Charter_v4.0.md`
2. `Project_Horizon/00_Project_Control/THREAD_PROTOCOL.md`
3. `Project_Horizon/00_Project_Control/MASTER_STATUS.md`
4. target Specialist `STATUS.md` in its canonical repository
5. evidence / artifacts
6. user report
7. inference

If authority or write ownership is unclear, fail closed.

## Ownership / Target Rules

### Specialist Thread

A Specialist may update **only its own STATUS.md** and explicitly authorized operational workspaces.

A Specialist must not update:

- `MASTER_STATUS.md`;
- another Specialist's STATUS;
- Core strategy / governance state.

If the event requires cross-thread judgment, the Specialist may set:

`Needs Core Decision: Yes`

only when the underlying Specialist state itself has meaningfully changed or the decision request is materially relevant to that thread.

### Horizon Core

Horizon Core may update:

- `Project_Horizon/00_Project_Control/MASTER_STATUS.md`;
- Core-owned governance / strategy files when relevant.

Horizon Core must **not** write a Specialist STATUS on that Specialist's behalf.

If a Core decision depends on unrecorded Specialist execution state, use the latest Specialist STATUS plus available evidence / user report without inventing a Specialist completion.

## Meaningful-Change Gate

Before any write, ask:

> Has something materially changed in formal Horizon state?

A write is justified only if at least one is true:

1. **Milestone:** a meaningful milestone is completed.
2. **Blocker:** a blocker appears, materially changes, or resolves.
3. **Route:** the current learning / project route materially changes.
4. **Result:** a competition, application, project or other formal result arrives.
5. **Next Gate:** the next milestone materially changes.
6. **Activation / Priority:** Core changes active state, priority or resource allocation.
7. **Decision Need:** a Specialist has a meaningful issue requiring Core judgment.

If none apply: **No formal write.** Continue the user's actual task.

## Evidence Classification

Classify each new claim as one of:

- **Verified GitHub / Artifact** — supported by repository state, code, commit, file, report or other verifiable artifact.
- **User-Reported** — stated by the user but not independently verified in current tools.
- **External Verified** — verified from current reliable external sources.
- **Inference / Recommendation** — interpretation, not execution fact.

Rules:

- A plan is never recorded as completed work.
- User-reported facts may be recorded when appropriate, but must not silently become repository-verified evidence.
- Inference belongs in reasoning / decision text, not as completed execution evidence.
- Link paths, commits or artifacts when useful and available.

## Procedure

### Step 1 — Run context preflight if needed

Use HZN-001 when current role, ownership, project state or external freshness is not already fresh and clear.

Do not rerun HZN-001 by ritual when authoritative state is already fresh in the same conversation.

### Step 2 — Identify the event

Summarize internally:

- what changed;
- when it changed;
- which thread / Core state it belongs to;
- what evidence exists;
- whether the change is verified, user-reported or inferred.

### Step 3 — Apply the Meaningful-Change Gate

If the event does not cross the threshold, stop the status workflow.

Output internally:

`Formal update: No`

Do not create a commit just to record that no update was needed.

### Step 4 — Resolve the single owner and target

Choose the file based on ownership, not convenience.

Typical cases:

- Specialist execution milestone → that Specialist's own `STATUS.md` in its canonical repository.
- Specialist blocker / next milestone → that Specialist's own `STATUS.md`.
- Specialist needs cross-thread judgment → its own `STATUS.md` with `Needs Core Decision: Yes`, if the threshold is met.
- Core priority / activation / cross-thread decision → `Project_Horizon/00_Project_Control/MASTER_STATUS.md` by Horizon Core.

One event may affect both Specialist and MASTER state, but each file remains single-owner. Do not collapse two owners into one write.

### Step 5 — Fetch latest target and SHA

Immediately before writing:

1. fetch the latest target file;
2. confirm current SHA;
3. check whether the intended change is already present;
4. preserve valuable existing facts.

Never write from an old cached copy when the target may have changed.

### Step 6 — Prepare the minimum patch

Change only sections justified by new evidence / decision.

Typical section mapping:

- milestone completed → `Completed`, `Current Stage`, `In Progress`, `Next Milestone`, `Evidence` as needed;
- blocker → `Blockers`, possibly `Current Stage` / `Next Milestone`;
- Core decision needed → `Needs Core Decision` plus concise decision request;
- route change → `Current Goal` / `Current Stage` / `In Progress` / `Next Milestone`;
- Core activation / priority → relevant `MASTER_STATUS` summary sections only.

Update `Last Updated` only when a meaningful write occurs.

Do not rewrite unaffected sections for style.

### Step 7 — Normalize governance terminology only when touching the file

When a meaningful update already requires editing a legacy Specialist STATUS, opportunistically migrate stale governance wording such as:

- `Project Control` → `Horizon Core` when the meaning is current authority;
- `Needs Master Decision` → `Needs Core Decision`.

Do **not** create a standalone commit solely for cosmetic renaming.

Historical references to old decisions / bridge artifacts may remain historical when accurate.

### Step 8 — Verify before commit

Check:

- target owner is correct;
- no plan is recorded as completed;
- new evidence classification is honest;
- old valuable facts are preserved;
- no unrelated sections changed;
- `Last Updated` is correct;
- `Needs Core Decision` is used only when genuinely required;
- no sensitive secrets are written.

### Step 9 — Commit with a meaningful message

Use a concise commit message describing the actual state change, not the conversation.

## Output Contract

The workflow should end in one of two states:

### A. No formal update

```text
Formal update: No
Reason: <threshold not met>
```

No repository write is made.

### B. Formal update required

```text
Formal update: Yes
Owner: <Horizon Core / Specialist>
Target: <repo/path>
Meaningful change type: <milestone / blocker / route / result / next gate / priority / decision need>
Evidence: <classification + reference>
Sections changed: <minimal list>
```

Then perform the authorized write.

## Verification Checklist

- [ ] Meaningful-change threshold passed
- [ ] Correct single owner identified
- [ ] Latest target + SHA fetched immediately before write
- [ ] Only justified sections changed
- [ ] Plans not written as completions
- [ ] Evidence classification preserved
- [ ] Useful prior facts preserved
- [ ] `Last Updated` changed only with meaningful state
- [ ] Legacy terminology migrated only opportunistically
- [ ] No unauthorized cross-role write
- [ ] No sensitive secrets added

## Stop / Escalation Conditions

Stop or escalate when:

- ownership is ambiguous;
- evidence conflicts materially with current formal state;
- a Specialist is being asked to modify Core / another Specialist state;
- a Core decision requires Specialist evidence that does not exist and cannot be responsibly inferred;
- a user report is too ambiguous to state factually;
- the write would contain sensitive credentials or secrets;
- repository access fails and the latest SHA cannot be confirmed.

## Trial Plan

HZN-002 v0.1 should be trialed only on real status-update situations.

Seek evidence across at least two distinct cases, preferably including:

1. one **No formal update** case where the Skill correctly prevents churn;
2. one **real meaningful update** case where it produces a minimal, evidence-based patch;
3. ideally both Specialist and Core-side behavior over time, without manufacturing events.

Do not update a STATUS merely to test HZN-002.

## Change Log

### v0.1 — 2026-08-29 — Candidate / Trial

- First Horizon Core version.
- Encodes meaningful-change gate, ownership routing, evidence classification, minimum-patch rules and opportunistic legacy-term migration.
- Designed directly from Charter v4.0 / `THREAD_PROTOCOL.md` v2.0 and observed Specialist STATUS patterns.

### Multi-repository path adaptation — 2026-09-04

- Physical path references updated for the multi-repository architecture.
- No change to authority, lifecycle state or behavior.
