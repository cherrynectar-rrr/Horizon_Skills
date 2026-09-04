---
name: engineering-debug-loop
description: Diagnose real bugs, failures, flaky behavior, build problems, hardware faults, or performance regressions by first creating a reproducible signal, then minimising, testing competing hypotheses, instrumenting, fixing the root cause, and verifying the original symptom.
metadata:
  version: "0.2"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Engineering Debug Loop

## Purpose

Replace random debugging with a tight evidence loop.

Use when a real Python, C++, Linux, Embedded or later robotics system is broken, failing, flaky or unexpectedly slow enough that guessing would create churn.

This Skill is not required for trivial syntax errors or obvious one-line mistakes.

## Core Rule

**Do not start by guessing the cause. First create a signal that reliably tells you whether the exact problem is present.**

Default flow:

`symptom → reproducible signal → minimise → hypotheses → targeted checks → root cause → smallest fix → verify → regression evidence when useful`

## 1. State the Exact Symptom

Describe what is actually wrong in observable terms.

Good:

- function returns `None` for an existing student ID;
- STM32 flashes successfully but PB0 never changes voltage;
- program takes 8 seconds where the previous version took 1 second.

Weak:

- code is weird;
- board does not work;
- probably a library problem.

## 2. Build the Feedback Loop

Find the smallest practical check that can go **red on this exact problem** and green when fixed.

Possible signals:

- failing unit / integration test;
- minimal script or CLI invocation;
- known input / output pair;
- debugger breakpoint or register observation;
- serial / UART log with a specific expected transition;
- multimeter / logic-analyser measurement;
- build / flash / debug checkpoint;
- timing benchmark;
- repeatable manual hardware step when automation is not practical.

For hardware, the signal may combine software observation and physical measurement.

If no credible signal can distinguish broken from correct behavior, gather more evidence before proposing a fix.

## 3. Reproduce and Minimise

Confirm the symptom more than once when practical.

Then remove unrelated inputs, modules, peripherals, configuration and steps until the smallest still-failing case remains.

Check recent relevant changes, environment differences and warnings before assuming an exotic cause.

Do not destroy useful project state merely to obtain minimality.

## 4. Generate Competing Hypotheses

Before changing several things, list a small number of plausible causes.

Each hypothesis should make a prediction that can be checked.

Example for a GPIO failure:

- pin configuration is wrong → register state should disagree with intended mode;
- code path is not reached → breakpoint / counter should remain untouched;
- physical pin / wiring is wrong → register changes but measured voltage does not;
- board power / reference issue → expected supply measurement is absent.

Prefer checks that distinguish hypotheses from each other.

## 5. Change One Variable at a Time

Use debugger, measurements and targeted logs before broad edits.

Avoid:

- reinstalling everything before localising the problem;
- changing code, wiring and configuration simultaneously;
- adding large amounts of logging with no hypothesis;
- accepting a different symptom as proof that the original bug is fixed;
- stacking a second speculative fix on top of a first failed one.

## 6. Architecture Reset Rule

If roughly **three evidence-backed fix attempts fail**, or each attempted fix reveals a new coupled failure in a different part of the system, stop before fix #4.

Re-question:

- is the assumed architecture / interface wrong?
- is the feedback signal testing the real path?
- is hidden shared state / coupling the actual problem?
- are we treating symptoms while preserving a flawed design?
- is an important environmental / physical assumption false?

Do not continue patching through inertia.

For a learning task, this is also a signal to re-explain the system model before more code changes.

## 7. Fix the Root Cause and Verify

Apply the smallest justified fix that addresses the supported cause.

Then rerun the **original feedback loop**, not just a new easier check.

When a stable software seam exists, preserve a regression test / check so the same failure is caught later.

For hardware where automatic regression testing is impractical, preserve the measurement / reproduction steps only when they are genuinely reusable.

Before declaring the issue fixed, hand the claim to `completion-verification`.

## 8. Cleanup

Remove temporary debug instrumentation and throwaway changes.

Record the root cause only when the evidence supports it. If the cause remains uncertain, say so.

## Learning Use

When the user is being assessed, independent debugging strategy itself may be part of the evidence. Do not over-guide unless the user asks for tutoring or a safety constraint requires intervention.

## Trial Gate

Pass when at least one natural real bug is handled with a concrete feedback signal before speculative changes, and the method measurably reduces guessing or leaves useful regression / debug evidence.

## Attribution

Conceptually adapted from Matt Pocock's MIT-licensed `diagnosing-bugs` Skill and Jesse Vincent's MIT-licensed `obra/superpowers` systematic-debugging method.

Horizon adaptation is intentionally smaller, adds physical-system / Embedded debugging, and uses a bounded architecture-reset rule instead of unlimited patch attempts.
