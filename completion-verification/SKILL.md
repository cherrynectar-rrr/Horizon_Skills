---
name: completion-verification
description: Verify fresh evidence before claiming work is complete, fixed, passing, migrated, ready, or working. Use before milestone completion, final implementation claims, project-gate transitions, commits/PR handoffs, data-pipeline completion, or hardware bring-up claims.
metadata:
  version: "0.1"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Completion Verification

## Purpose

Bind success claims to fresh evidence.

Use this Skill immediately before saying that code, data, documentation, migration, hardware or a project gate is complete / fixed / passing / ready.

## Core Rule

**Evidence first. Claim only what the evidence actually proves.**

Default flow:

`claim → proof signal → fresh verification → inspect result → state supported conclusion`

## 1. State the Claim Precisely

Avoid vague claims such as:

- it works;
- migration is done;
- the bug is fixed;
- Phase 0 passed.

Translate them into observable claims:

- `pytest` reports zero failures for the relevant suite;
- the migrated canonical file exists and contains the expected state;
- the original bug reproduction is now green;
- the STM32 project builds, flashes, enters debug and changes the intended real pin / LED;
- the historical dataset loads with the expected rows and every final record has a traceable source.

## 2. Identify the Strongest Practical Proof

Ask:

> What observation would make this claim false if the work were still broken?

Prefer, roughly in order:

- automated test / build / linter / type-check output when it directly proves the claim;
- exact reproduction of the original bug;
- end-to-end acceptance check;
- runtime / hardware observation;
- file / repository verification after a write;
- structured manual checklist when automation is not practical.

Do not substitute a nearby signal for the real claim.

Examples:

- a linter does not prove the program builds;
- a mocked GPIO does not prove the physical board output works;
- successful file creation does not prove cross-repository links are correct;
- tests passing do not prove every requirement is implemented unless the tests cover those requirements.

## 3. Run or Observe Fresh Evidence

Use the current candidate state, not an old successful run.

For software, capture the command / test and the actual result.

For GitHub / repository work, refetch or otherwise inspect the destination after meaningful writes when the existence or content of the written artifact is part of the claim.

For hardware, use real physical evidence when the claim concerns physical behavior:

- debugger state;
- UART / telemetry;
- measured voltage / signal;
- visible LED / actuator response;
- another appropriate physical observation.

For data work, verify both computation and provenance when provenance is part of the deliverable.

## 4. Read the Result, Including Negative Evidence

Check the complete relevant output:

- exit status;
- failure count;
- warnings that invalidate the claim;
- missing rows / files / artifacts;
- unexpected hardware state;
- partial requirements.

If verification fails, report the actual state. Do not soften it into a completion claim.

## 5. Match Claim Scope to Evidence Scope

Good:

> The Python unit tests for persistence pass; real cross-platform file behavior has not been tested yet.

Bad:

> The whole application is production-ready.

Good:

> Build / flash / debug / onboard LED are verified on the NUCLEO board.

Bad:

> Embedded Phase 1 is complete.

When evidence is partial, use a partial conclusion.

## 6. Requirements Check for Milestones

Before marking a Horizon milestone complete:

1. reread the milestone / acceptance criteria;
2. map each criterion to evidence;
3. identify any criterion without evidence;
4. only then update STATUS / MASTER if the meaningful-change gate is satisfied.

A test suite is evidence, not a substitute for reading the actual gate definition.

## Tool / Access Limits

If the available environment cannot run the required verification, say so explicitly.

Use wording such as:

> The file was created successfully, but I cannot claim the application passes because the runtime test was not executed here.

Do not invent verification evidence to preserve momentum.

## Relation to Other Horizon Skills

- `engineering-debug-loop` finds and fixes causes; this Skill verifies the final claim.
- `behavior-first-testing` creates useful behavioral checks; this Skill confirms they actually pass in the candidate state.
- `change-review` reviews correctness / quality; this Skill verifies the accepted result before completion is declared.
- `status-update` decides whether verified work is meaningful enough to enter formal state.

## Trial Gate

Pass when a natural Horizon task reaches a tempting completion claim and this Skill either:

- catches an unverified / partial result before it is recorded as complete; or
- produces fresh evidence that safely closes a real milestone.

## Attribution

Conceptually adapted from the MIT-licensed `verification-before-completion` Skill in `obra/superpowers`, with additional influence from release / final-review verification patterns in public OpenAI repositories.

Horizon adaptation broadens verification beyond software commands to data provenance, GitHub state and physical Embedded evidence.
