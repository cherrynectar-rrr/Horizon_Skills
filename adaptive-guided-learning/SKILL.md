---
name: adaptive-guided-learning
description: Use when the learner is entering unfamiliar or abstract technical material and passive self-study, long resource reading, or fragmented one-question-at-a-time tutoring is creating unnecessary friction. Guide learning through quick diagnosis, minimal explanation, meaningful tasks, dynamic step size, targeted repair, and transfer. Do not use as a formal exam mode or for already-mastered repetitive work.
metadata:
  version: "0.1"
  lifecycle: "Candidate / Trial"
  owner: "Horizon Core"
---

# Adaptive Guided Learning

Version: 0.1  
Status: Candidate — Trial  
Owner: Horizon Core  
Created: 2026-09-04

## Purpose

Provide a high-efficiency guided learning mode for cases where:

- long self-study/resource reading does not reliably turn into understanding;
- the learner is new enough that they do not yet know what to ask;
- continuous tiny questions create excessive interaction cost;
- the subject benefits from immediate feedback, practice, debugging or physical execution.

This Skill is a **trial learning mode**, not a new learning line or governance layer. It complements `horizon-learning-loop` v0.2 during the trial. If it proves consistently better on real tasks, its strongest parts should be absorbed into a future `horizon-learning-loop` revision rather than preserved as unnecessary parallel machinery.

## Core Principle

> **Minimum intervention, maximum useful step.**

AI should remove low-value friction while preserving the thinking that actually builds capability.

Use AI aggressively for:

- narrowing scope;
- locating high-quality or authoritative material;
- explaining a concrete blockage;
- generating targeted practice;
- giving fast feedback;
- reviewing, testing and comparing completed work.

Do **not** automatically remove:

- recall;
- derivation;
- choosing a method;
- first meaningful implementation;
- debugging attempts;
- explaining why something works;
- transfer to unfamiliar problems;
- real-world measurement and verification.

The goal is not low-effort learning. The goal is **shorter time-to-independent-capability**.

## Default Loop

```text
1. Define one concrete capability
→ 2. Quick diagnosis
→ 3. Minimal teaching / map
→ 4. One meaningful task chunk
→ 5. Inspect performance
→ 6. Expand step size or repair only the real gap
→ 7. Independent transfer / practical use
→ 8. Later retrieval when useful
```

Do not force every subject through every step. The mode should feel lightweight.

## 1. Define One Concrete Capability

Start with what the learner should be able to **do**, not what chapter should be consumed.

Examples:

- define a Python `Student` class, create multiple objects and explain instance state;
- construct and use a one-dimensional prefix sum and justify the interval formula;
- build, flash and debug a minimal STM32 project and explain the path from source to board;
- derive and apply one mathematical result to a nearby unfamiliar problem.

Keep the target small enough to reach in one coherent learning session or short sequence.

## 2. Quick Diagnosis

Diagnose starting level with the smallest useful signal.

Default:

- use at most a few high-information prompts;
- prefer one compact task or explanation over many tiny confirmation questions;
- infer already-demonstrated lower-level knowledge from stronger evidence;
- skip prerequisites the learner has already shown in real work.

A diagnostic question is justified only if the answer can materially change the next teaching step.

Do not ask obvious confirmation questions merely to keep the conversation interactive.

## 3. Minimal Teaching / Map

Teach only the next concept or mechanism required for progress.

Prefer:

- connection to something the learner already knows;
- one concrete example;
- a small diagram / mental model when useful;
- a short authoritative excerpt or reference only when needed.

Avoid front-loading an entire chapter, long lecture, API catalog or theory stack before the learner has a place to use it.

Use **just-in-time knowledge** rather than just-in-case coverage.

## 4. One Meaningful Task Chunk

After teaching, the learner should do something substantial enough to reveal capability.

Prefer:

- a complete short trace instead of one trace step at a time;
- a small runnable code unit instead of filling one token / line at a time;
- one coherent derivation instead of many trivial arithmetic confirmations;
- a real configuration / measurement step instead of purely verbal hardware discussion;
- one representative problem with explanation instead of several near-identical micro-questions.

Example for two pointers:

Instead of repeatedly asking which pointer moves after each sum, ask the learner to execute the full algorithm on one small array and report `(left, right, sum, action)` for the whole run, then explain the movement rule once.

## 5. Dynamic Step Size

The teaching granularity must change with performance.

### Expand the step size when

- the learner gives correct reasoning without prompting;
- a higher-level task already demonstrates lower-level knowledge;
- the same idea has been shown correctly more than once;
- continued micro-checking would not change the teaching path.

Then move directly to a larger task, harder variant or transfer problem.

### Reduce the step size when

- the learner repeatedly makes the same conceptual error;
- the mental model is missing;
- a prerequisite turns out to be absent;
- the learner cannot explain or reconstruct the method;
- safety requires slower hardware guidance.

Reduction is temporary. Once the gap is repaired, increase the step size again.

## 6. Targeted Repair

When a mistake appears, repair the smallest real gap.

Examples:

- indexing / boundary confusion;
- misunderstanding object state;
- incorrect complexity model;
- missing MCU clock / GPIO mental model;
- wrong mathematical prerequisite;
- inability to distinguish two methods.

Do not reteach the whole topic because of one error.

Use:

`error → diagnose cause → focused explanation / example → nearby retry`

## 7. Attempt Before Assist

For core capability tasks, obtain a genuine learner attempt before giving the complete solution whenever practical.

The attempt may be:

- code;
- a derivation;
- a trace;
- a design sketch;
- an explanation;
- a debugging hypothesis;
- a description of exactly where reasoning stopped.

Do not require ceremonial waiting or arbitrary struggle time. The purpose is to preserve active reasoning, not to waste time.

When the learner is completely new and cannot form a meaningful attempt, provide enough scaffold to make the first real attempt possible.

## 8. Resource Use

Resources support learning; consuming them is not the learning objective.

Default resource behavior:

- AI may first compress the map and identify the small relevant section;
- use one good primary teaching source when a structured source is genuinely useful;
- use official documentation / manuals as authority for APIs, hardware and mutable technical facts;
- avoid asking the learner to read long material before any mental model exists;
- stop resource searching once a source is good enough to proceed.

A long textbook, video series or reference manual may be used later for depth, consolidation or reference after the learner has a conceptual hook.

## 9. AI Assistance Levels

AI involvement should change with the stage.

### Orientation — high AI assistance

AI narrows the field, maps prerequisites, finds sources and identifies what can be skipped.

### Foundation — moderate AI assistance

AI explains and scaffolds, but the learner performs the core reasoning and first meaningful construction.

### Independent Retrieval — low assistance

The learner explains, derives, codes, traces or diagnoses without solution leakage.

### AI-Native Application — high assistance allowed

After the foundation is demonstrated, AI may help substantially with implementation, boilerplate, research, tests, review and iteration. The learner remains responsible for understanding important behavior and decisions.

### Audit / Transfer — assistance constrained by the test

Give unfamiliar code, results, design or problems and test whether the learner can inspect, modify, debug, verify or transfer independently.

## 10. Anti-Fragmentation Rules

To avoid low-value chat loops:

- do not ask a question whose answer will not affect the next step;
- do not require explicit confirmation of knowledge already demonstrated in a harder task;
- do not split one coherent reasoning chain into many trivial prompts;
- batch simple checks when several are genuinely needed;
- prefer code, full traces, derivations, design choices and transfer problems over repeated yes/no or single-step questions;
- after repeated correct performance, advance rather than seek extra reassurance;
- when a learner is clearly ready, let them complete the whole task before intervening.

Interaction count is not a learning metric.

## 11. Completion / Transfer Gate

A guided session is not complete because the explanation felt clear.

Before treating the capability as learned, obtain at least one meaningful evidence signal such as:

- an independently solved unfamiliar or modified problem;
- runnable code produced or substantially reconstructed by the learner;
- successful debugging of a new failure;
- correct explanation of mechanism and boundaries;
- physical hardware behavior plus explanation / measurement;
- transfer of the idea into a small real project.

The evidence should match the claim being made.

## 12. Later Retrieval

Do not turn every topic into a daily flashcard routine.

When retention matters, reintroduce earlier capabilities through:

- mixed later problems;
- cumulative assessments;
- real projects;
- delayed debugging / review tasks;
- occasional recall or derivation checks.

Prefer naturally embedded retrieval where it fits the domain.

## Domain Adaptation

### Algorithm

- derive the main idea from a concrete problem when possible;
- use full small traces rather than one pointer movement per message;
- quickly transition to independent implementation and unseen variants;
- ask about invariants, boundaries and complexity only where they provide real evidence.

### Python / C++

- teach a new concept through the current project or a small executable example;
- avoid long syntax tours;
- after the concept is understood, permit increasing AI implementation assistance;
- verify through debugging, modification, tests and unfamiliar code review.

### Embedded

- anchor learning to a physical objective;
- teach the minimum model needed for the next board action;
- use datasheets / reference manuals just in time;
- let build output, debugger state, measurements and real hardware decide what is true.

### Mathematics / Physics

- preserve derivation and problem-solving effort;
- use AI to clarify concepts, choose examples and diagnose gaps;
- avoid fragmenting derivations into trivial line-by-line confirmations;
- require transfer to a nearby unfamiliar problem.

## Trial Evaluation

Trial on natural Horizon learning work, especially current Python OOP and Algorithm Prefix Sums when appropriate.

Evaluate qualitatively against the previous learning surface using:

- time-to-independent-capability;
- number of low-value conversational turns;
- ability to solve a transfer task;
- retention when later reused;
- learner friction / boredom;
- whether AI assistance reduced search waste without reducing real understanding.

Do not create extra logs or dashboards just to measure the trial. Record only meaningful evidence or friction.

## Relationship to `horizon-learning-loop`

`horizon-learning-loop` v0.2 remains the adopted shared learning procedure during this trial.

This Candidate specifically tests whether Horizon should replace the rigid **Self-Study + Assessment default** with a more adaptive rule:

> **unfamiliar → guided efficiently; understanding → larger independent tasks; foundation passed → AI-native application; mastery → audit and transfer.**

If the trial succeeds, merge the useful behavior into a future version of `horizon-learning-loop` and retire this separate Candidate rather than maintaining duplicate learning systems.
