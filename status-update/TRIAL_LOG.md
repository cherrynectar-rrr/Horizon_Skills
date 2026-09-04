# HZN-002 — status-update Trial Log

Last Updated: 2026-08-29
Status: Active Candidate Trial
Owner: Horizon Core

## Purpose

Record only meaningful real uses of `HZN-002 — status-update` that reveal value, failure, friction or a needed revision.

Do not create formal state merely to generate Trial evidence.

---

## Trial 002 — Legacy Terminology Detected, No Formal Update

- Date: 2026-08-29
- Invoking role: Horizon Core
- Context: While evaluating HZN-002, Core inspected Academic and Finance STATUS files and observed legacy governance wording such as `Project Control` / `Needs Master Decision`.
- Task classification: status-maintenance review; no-write threshold test.

### Meaningful-change gate

The only immediately available change was terminology normalization after the Horizon Core merger. `THREAD_PROTOCOL.md` explicitly allows legacy wording to remain until the next meaningful status update and says not to create churn solely for renaming.

### Outcome

**Formal update: No**

No Academic or Finance STATUS write was made.

### Trial verdict

**Pass — no-write gate prevented unnecessary STATUS churn.**

---

## Trial 001 — Core Authorizes HZN-002 Candidate and Updates MASTER

- Date: 2026-08-29
- Invoking role: Horizon Core
- Trigger: After HZN-001 v0.5 adoption, Core separately approved HZN-002 v0.1 for Candidate Trial.
- Meaningful change: HZN-002 moved from frozen backlog to Candidate — Trial; HZN-003 through HZN-005 remained frozen.
- Owner: Horizon Core
- Target: `Project_Horizon/00_Project_Control/MASTER_STATUS.md`

### Outcome

The meaningful-change gate correctly permitted a bounded Core-state write while Specialist STATUS files remained untouched.

### Trial verdict

**Pass — first real write produced a bounded Core-state patch.**

---

## Remaining Evidence Gap

Before adoption, seek at least one natural Specialist-side event that either:

1. correctly produces a minimal Specialist STATUS update from real evidence; or
2. correctly refuses a tempting but sub-threshold Specialist update.

Do not manufacture a milestone or edit a Specialist STATUS merely to finish the Trial.

## Migration Note — 2026-09-04

This log was migrated from the legacy `Project_Horizon/00_Strategy/Voyage_Room/skills/status-update/` location to `Horizon_Skills/status-update/`. Historical pre-separation detail remains available in the old repository history.
