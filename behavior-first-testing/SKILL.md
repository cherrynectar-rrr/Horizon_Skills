# Behavior-First Testing

Version: 0.1
Status: Candidate — Trial
Owner: Horizon Core
Authorized: 2026-09-04

## Purpose

Use tests and acceptance checks to make program behavior explicit before implementation becomes hard to reason about.

This Skill is intended for real Python / C++ project work and later research software. It is **not** a rule that every learning exercise, getter or trivial function must use strict TDD.

## Core Principle

**Test observable behavior through a meaningful public seam, not private implementation details.**

When a feature is important enough to test, first answer:

- what input/action is visible at the boundary?
- what observable result should occur?
- which failure / edge cases actually matter?

## Default Loop

When useful:

`define behavior → create one failing check → implement the smallest useful slice → make it pass → repeat`

This is a vertical-slice loop. Do not write a huge imagined test suite before understanding the implementation.

## Good Tests / Checks

Prefer tests that read like capabilities:

- an existing student can be found by ID;
- duplicate IDs are rejected;
- saved experiment trials can be loaded without changing their values;
- invalid sensor records are rejected with a clear error;
- a parser correctly handles one complete UART packet.

Expected results should come from the requirement, worked example or known-good source rather than recomputing the same algorithm inside the test.

## Avoid

- tests of private methods solely because they are easy to reach;
- mocks of every internal collaborator;
- snapshots or assertions that cannot detect real wrong behavior;
- tests whose only purpose is increasing test count / coverage;
- forcing TDD where hardware interaction or exploratory work has no stable seam yet.

## Hardware Boundary

Embedded work often cannot use classic unit tests for the full physical system.

Use the strongest practical acceptance seam:

- pure logic can be unit-tested on host when useful;
- protocol parsers/state machines may be tested with known inputs;
- hardware behavior may require debugger state, UART output or physical measurement;
- do not pretend a mocked GPIO proves the real board works.

Testing complements, not replaces, physical verification.

## Relation to Horizon Learning Loop

For Project / Practical Gates, tests may be hidden or provided as acceptance criteria so the learner must build independently.

When the user is still acquiring basic syntax or OOP fluency, testing should support learning rather than dominate it.

## Trial Gate

Pass when at least one natural project feature defines observable behavior first and uses a useful test / acceptance check that catches a real mistake, enables safer change or improves confidence without excessive ceremony.

## Attribution

Conceptually adapted from Matt Pocock's MIT-licensed `tdd` Skill:
`https://github.com/mattpocock/skills`

Horizon intentionally softens strict TDD into behavior-first testing because the current learning stage includes beginner programming and physical Embedded work.
