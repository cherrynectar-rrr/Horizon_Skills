# Design Grill

Version: 0.1
Status: Candidate — Trial
Owner: Horizon Core
Authorized: 2026-09-04

## Purpose

Clarify important design decisions, boundaries and hidden assumptions before implementation creates expensive rework.

Use for non-trivial software, Embedded, robotics or research-system design when the request is still underspecified or several plausible architectures exist.

Do not use for tiny exercises, obvious bug fixes or decisions whose answer is already determined by current requirements.

## Core Principle

**Do not convert a vague idea directly into code. Resolve the decisions that materially change what gets built.**

Map the problem as a small decision tree:

- what outcome are we trying to produce?
- what constraints are already fixed?
- which decisions are independent enough to answer now?
- which later decisions depend on those answers?

Ask only the current decision frontier; do not dump every future question at once.

## Horizon Adaptation

The assistant should research facts it can determine itself rather than asking the user to do lookup work.

The user's job is to make preference / trade-off decisions that cannot be inferred safely.

For each material question, the assistant should usually provide a recommended answer with a short reason so the user is choosing between understood options rather than being interrogated blindly.

## Useful Question Types

Examples:

- What is the minimum successful behavior?
- What data must survive between runs?
- Where is the safety boundary between PC/Python and MCU control?
- Which sensor measurement is actually needed to answer the experiment question?
- What is baseline vs extension?
- What failure mode must the design tolerate?
- What interface should stay stable even if internals change?
- Which feature would be postponed if this one is accepted?

## Stop Condition

Stop grilling when the remaining uncertainty can be resolved cheaply during implementation or through a reversible prototype.

The goal is **decision-quality clarity**, not exhaustive certainty.

If a small prototype would answer the question faster than more discussion, prefer the prototype.

## Output

For significant design work, finish with a compact design summary:

- goal;
- fixed constraints;
- key decisions;
- deliberately deferred decisions;
- acceptance / experiment criteria;
- major unresolved risk.

Do not create ADRs, specs or extra documents unless the project actually benefits from them.

## Trial Gate

Pass when at least one natural non-trivial design session surfaces an important hidden assumption or trade-off before implementation and demonstrably reduces rework, scope confusion or unsafe architecture.

## Attribution

Conceptually adapted from Matt Pocock's MIT-licensed `grilling` / `grill-with-docs` ideas:
`https://github.com/mattpocock/skills`

Horizon adaptation is deliberately lighter: no mandatory issue tracker, ADR system, sub-agent architecture or exhaustive interview ritual.
