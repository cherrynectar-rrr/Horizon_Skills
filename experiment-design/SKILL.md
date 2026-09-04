---
name: experiment-design
description: Design a reproducible software, data, benchmark, Embedded, robotics, or research experiment that can distinguish competing explanations. Use before meaningful experiments, model comparisons, hardware measurements, performance benchmarks, or Earth Flywheel trials.
metadata:
  version: "0.1"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Experiment Design

## Purpose

Make experiments answer a question rather than merely produce activity or data.

Default flow:

`question → exploratory/confirmatory mode → baseline/control → variables/metrics → protocol → pilot → collect → analyze → limitations → next decision`

## Trigger Boundary

Use for:

- Embedded / robotics hardware experiments;
- Earth Flywheel trials;
- model / algorithm comparisons;
- performance benchmarks;
- data-analysis experiments;
- research reproduction or hypothesis tests.

Do not invoke for ordinary unit tests, trivial code examples or classroom exercises with an already-fixed procedure.

## 1. State the Question Operationally

The question must be answerable by observation.

Weak:

> Is this controller better?

Better:

> Under the same load and target trajectory, does controller B reduce mean tracking error without increasing over-force events compared with controller A?

If the work is exploratory, say so. Exploration is valid; it simply should not be reported as a confirmatory test.

## 2. Define the Claim Before the Data

For confirmatory work, specify:

- hypothesis / expected direction when justified;
- what observation would count against it;
- primary metric(s);
- success / failure threshold when one is meaningful.

Do not invent a threshold after seeing the result merely to declare success.

For exploratory work, define the measurements and questions but keep hypothesis generation separate from later confirmation.

## 3. Choose a Baseline / Control

Ask what comparison makes the result interpretable.

Possible controls:

- previous implementation / release;
- no-memory vs local-memory policy;
- open-loop vs feedback controller;
- same dataset with one feature removed;
- known-good hardware state;
- naive algorithm / simple heuristic.

A result with no comparison may still be useful, but its claim must stay correspondingly narrow.

## 4. Define Variables and What Is Held Constant

Record:

- variable under test;
- measured outputs;
- important conditions held constant;
- likely confounders;
- hidden state that may affect repeated runs.

For comparisons, establish parity before execution rather than explaining differences after the fact.

## 5. Check the Measurement System

Before a large experiment, verify that the measurement itself is trustworthy.

Examples:

- sensor range / calibration is adequate;
- timestamps are consistent;
- data logger does not drop records;
- benchmark warm-up effects are understood;
- target labels / source records are valid.

If measurement cannot distinguish the expected effect from noise or setup error, fix the measurement first.

## 6. Design the Smallest Useful Protocol

Specify enough to reproduce the experiment:

- setup / environment;
- inputs / objects / dataset;
- ordered procedure;
- repetitions or sample choice;
- randomization / ordering when relevant;
- what raw data is recorded;
- software / firmware / configuration version;
- failure / abort / cleanup rule.

Do not add statistical machinery that the question does not need.

For small engineering experiments, repeated measurements and transparent raw data may be more useful than premature significance testing.

## 7. Safety and Side Effects

For physical or live-system experiments, identify risks before execution:

- force / current / voltage / thermal limits;
- actuator travel or collision limits;
- destructive file / state changes;
- network / API cost;
- credentials / private data;
- rollback / cleanup requirements.

High-risk or materially costly experiments require explicit approval at the appropriate Horizon / user boundary before execution.

## 8. Run a Pilot First

Use a small pilot to answer:

- does the setup execute end-to-end?
- are measurements readable and correctly logged?
- does the baseline behave plausibly?
- is the experiment likely to answer the question?

Do not mistake pilot results for final evidence when the full protocol is needed.

## 9. Preserve Raw Evidence and Provenance

Keep raw observations when practical, not only the final summary.

Record enough provenance to connect a result to:

- code / firmware version;
- dataset / input version;
- configuration;
- hardware setup when material;
- date / runtime environment when material.

Analysis should be reproducible from the preserved evidence whenever reasonable.

## 10. Analyze at the Scale the Protocol Supports

Report:

- observed result;
- comparison against baseline / control;
- variability / failures;
- unexpected observations;
- whether the evidence supports, weakens or leaves the hypothesis unresolved;
- limitations and confounders;
- what result would need replication.

Do not generalize from a narrow test matrix to a broad claim such as "works on unknown objects" or "algorithm B is better" without adequate coverage.

## 11. Close the Loop

End with the decision value:

- continue / refine / stop;
- what changed in our belief;
- highest-value next experiment;
- whether the finding is strong enough to update project STATUS or strategy.

Experiments exist to improve capability and judgment, not to accumulate graphs.

## Trial Gate

Pass when one real data / software / hardware experiment becomes more interpretable or reproducible because the Skill forced a useful baseline, measurement check, controlled comparison, safety limit or claim-scope correction.

## Attribution

Conceptually adapted from public scientific-agent research-methodology / experiment-design Skills and from OpenAI's public `runtime-behavior-probe` patterns for validation matrices, control cases and claim-scope discipline.

Horizon adaptation deliberately keeps the method lightweight for undergraduate engineering work and does not impose clinical-trial or statistical rituals when they do not fit the question.
