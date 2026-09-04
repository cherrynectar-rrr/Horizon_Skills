# HZN-001 v0.5 — Candidate Trial Log

Last Updated: 2026-08-29
Status: Candidate Trial Complete — Adoption Recommended
Owner: Horizon Core

## Purpose

Record only meaningful real uses of the **v0.5 Horizon Core Edition** that reveal value, failure, friction or a needed revision.

Historical v0.1–v0.4 trial evidence remains preserved in the pre-separation `Project_Horizon` history. Adopted v0.4 remains a historical baseline.

---

## Trial 006 — Algorithm Specialist Validation Under Horizon Core

- Date: 2026-08-29
- Invoking role: Algorithm Specialist Thread
- User intent: run HZN-001 v0.5 and then continue the existing Algorithm main line.
- Evidence classification: **user-reported invocation + repository-verified clean Specialist state**.

### Repository observations

- Algorithm STATUS remained focused on real execution state.
- The Skill test did not manufacture a status update.
- No new commit was created merely to record the Skill test.
- No evidence indicated cross-thread write leakage.

### Evidence limitation

GitHub verifies the absence of incorrect writes / artificial status churn, but it does not record chat-side read telemetry. The exact internal read sequence was therefore not claimed as independently verified.

### Trial verdict

**Pass — Specialist validation sufficient for v0.5 adoption.**

---

## Trial 005 — Horizon Core Governance Migration / Self-Preflight

- Date: 2026-08-29
- Invoking role: Horizon Core
- User intent: migrate HZN-001 from the retired Voyage Room + Main Control model to the Horizon Core model.

### Authoritative state used

- Charter v4.0;
- Thread Protocol under Horizon Core;
- current MASTER state;
- adopted HZN-001 v0.4 and its historical trial evidence.

Because this state was already fresh in the same conversation, v0.5 correctly avoided redundant rereading.

### Outcome

The candidate rewrite:

1. reduced the role model from three roles to two;
2. removed live Voyage–Control bridge reads;
3. updated the authority root to Charter v4.0;
4. simplified the internal Context Packet;
5. removed obsolete cross-role Trial Log routing machinery;
6. preserved historical v0.4 evidence;
7. avoided a repository-wide scan.

### Trial verdict

**Pass — Core migration trial successful.**

## Migration Note — 2026-09-04

This current adoption evidence was migrated to `Horizon_Skills`. Full v0.1–v0.4 historical trial detail remains preserved in the legacy `Project_Horizon` Git history and is not duplicated here merely for archival volume.
