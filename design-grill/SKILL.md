---
name: design-grill
description: Clarify material design decisions, split multi-subsystem requests into manageable slices, expose hidden assumptions, and run a short coverage/YAGNI check before non-trivial software, Embedded, robotics, or research-system implementation.
metadata:
  version: "0.2"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Design Grill

## Purpose

Clarify important design decisions, boundaries and hidden assumptions before implementation creates expensive rework.

Use for non-trivial software, Embedded, robotics or research-system design when the request is underspecified, spans several subsystems, or several plausible architectures exist.

Do not use for tiny exercises, obvious bug fixes or decisions whose answer is already determined by current requirements.

## Core Principle

**Do not convert a vague or oversized idea directly into code. Resolve only the decisions that materially change what gets built.**

Default flow:

`goal → scope decomposition → fixed constraints → decision frontier → acceptance criteria → coverage/YAGNI check → implement or prototype`

## 1. Decompose the Scope Before Detailed Design

If the request contains several independent or weakly coupled subsystems, split them before asking detailed questions.

Examples:

- PC application + MCU firmware + hardware + experiment logging;
- data ingestion + analysis + dashboard + forecasting;
- robot mechanics + sensing + low-level control + learning layer.

For each subsystem, identify:

- what it is responsible for;
- what interface connects it to the others;
- whether it is needed for the first useful slice.

Then choose the **smallest end-to-end slice** that can produce real evidence.

Do not design every future subsystem just because it can be imagined now.

## 2. Map the Current Decision Frontier

Ask:

- what outcome are we trying to produce?
- what constraints are already fixed?
- which decisions must be made before implementation?
- which decisions are independent enough to answer now?
- which later decisions depend on those answers?

Ask only the current frontier. Do not dump every future question at once.

## 3. Research What Can Be Determined Externally

The assistant should research facts it can determine itself rather than making the user perform lookup work.

The user's job is to make preference / trade-off decisions that cannot be inferred safely.

For each material question, usually provide a recommended answer with a short reason so the user is choosing between understood options rather than being interrogated blindly.

## 4. Useful Question Types

Examples:

- What is the minimum successful behavior?
- What data must survive between runs?
- Where is the safety boundary between PC/Python and MCU control?
- Which sensor measurement is actually needed to answer the experiment question?
- What is baseline vs extension?
- What failure mode must the design tolerate?
- What interface should stay stable even if internals change?
- Which feature would be postponed if this one is accepted?

## 5. Define Acceptance / Experiment Criteria

Before implementation, translate the chosen first slice into observable success criteria.

Examples:

- one Student object can be saved and loaded without value loss;
- MCU receives one UART command and changes one state predictably;
- gripper closes, detects contact and stops below a safety limit;
- data pipeline loads all cited records and produces one reproducible indicator.

Acceptance criteria should test behavior, not internal architecture preferences.

## 6. Coverage / YAGNI Check

Before implementation, run a short final check:

### Coverage

- Does every fixed requirement map to a design decision, interface or acceptance criterion?
- Is any material requirement still floating without an owner?
- Are safety / persistence / failure boundaries covered where relevant?

### YAGNI

- Which proposed components are not required for the first useful slice?
- Are we adding abstractions, services, frameworks or extension hooks only because they may be useful someday?
- Can a reversible prototype answer the uncertainty more cheaply than designing a general solution now?

Delete or defer unnecessary scope before code begins.

## 7. Stop Condition

Stop grilling when the remaining uncertainty can be resolved cheaply during implementation or through a reversible prototype.

The goal is **decision-quality clarity**, not exhaustive certainty.

If a small prototype would answer the question faster than more discussion, prefer the prototype.

## Output

For significant design work, finish with a compact design summary:

- goal;
- first end-to-end slice;
- fixed constraints;
- key decisions;
- interfaces / ownership boundaries;
- deliberately deferred decisions;
- acceptance / experiment criteria;
- major unresolved risk.

Do not create ADRs, specs or extra documents unless the project actually benefits from them.

## Relation to Other Horizon Skills

- use `behavior-first-testing` when stable software behavior can be tested before implementation;
- use `experiment-design` when the design is primarily an experiment rather than a software feature;
- use `completion-verification` before claiming the designed slice is complete.

## Trial Gate

Pass when at least one natural non-trivial design session surfaces an important hidden assumption, prevents unnecessary scope, or splits a tangled multi-subsystem request into a useful first slice before implementation.

## Attribution

Conceptually adapted from Matt Pocock's MIT-licensed `grilling` / `grill-with-docs` ideas and Jesse Vincent's MIT-licensed `obra/superpowers` brainstorming / design workflow principles.

Horizon adaptation is deliberately lighter: no mandatory issue tracker, ADR system, sub-agent architecture, exhaustive interview ritual or full-project spec before a reversible prototype.
