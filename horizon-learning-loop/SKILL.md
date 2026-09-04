# Horizon Learning Loop

Version: 0.2
Status: Adopted — Active
Owner: Horizon Core
Last Updated: 2026-09-01

## Purpose

Provide the default learning procedure for Project Horizon learning-oriented Specialist Threads.

The default mode is now **Self-Study + Assessment**, not continuous step-by-step tutoring.

Horizon should define what to learn, select a small set of high-quality resources, define evidence and assessment gates, then let the learner study independently. Specialist Threads evaluate capability through examinations, debugging tasks, transfer problems and real projects.

This Skill is a learning procedure, not a governance layer. It does not change thread ownership, activation state, roadmap priority or write authority.

## Core Principle

The default relationship is:

`Horizon defines capability + resources + assessment`

`→ learner self-studies`

`→ Horizon tests independent capability`

`→ gaps are diagnosed`

`→ targeted remediation / retest`

The assistant should not continuously lead the learner through every concept, line of code, derivation or implementation step unless the learner explicitly requests tutoring for a specific difficulty.

The success test is not whether material was watched or read. It is whether the learner can independently retrieve, explain, apply, debug and transfer the knowledge.

## Default Learning Architecture

```text
1. Capability Specification
→ 2. Resource Pack
→ 3. Independent Study
→ 4. Unit Assessment
→ 5. Stage Assessment
→ 6. Project / Practical Gate
→ 7. Final Assessment when useful
→ 8. Gap Diagnosis
→ 9. Targeted Remediation
→ 10. Retest / Transfer
```

Not every subject requires every layer. The assessment architecture should match the domain and the strategic value of the material.

## 1. Capability Specification

Before learning begins, define what the learner should be able to **do**.

Good examples:

- implement and explain binary search, including its invariant and boundary cases;
- write and debug a small object-oriented Python program without following a tutorial;
- build, flash and debug a minimal STM32 project and explain the bring-up path;
- use Linux tools to inspect and diagnose a real process or file-permission problem;
- derive and apply a control or mathematics result to a nearby unfamiliar problem.

Weak targets:

- finish Chapter 4;
- watch ten videos;
- complete a playlist;
- read a book from cover to cover without an output criterion.

## 2. Resource Pack

Horizon should normally provide a **small curated resource pack**, not an endless list.

Default resource shape:

1. **Primary video course / lecture series** — one main structured teaching source when useful.
2. **Primary book / textbook** — one main written reference.
3. **Official documentation / reference manual** — when the domain depends on APIs, tools, hardware or standards.
4. **Exercise / problem source** — only when practice requires a separate bank.
5. **Optional secondary reference** — only if the primary source has a known weakness.

Avoid giving five equivalent courses and ten books. Resource selection should minimize switching cost.

For mutable resources, software versions, current courses, documentation or external programmes, verify current availability and relevance before recommending them.

For each resource, state briefly:

- what it is for;
- which chapters / lectures matter;
- what can be skipped or deferred;
- what capability it should unlock.

## 3. Independent Study

The learner studies independently using the assigned resource pack.

Default behavior for Specialist Threads:

- do not interrupt the learner with continuous micro-lessons;
- do not require conversational check-ins after every small concept;
- do not turn the chat into a substitute lecture course;
- allow the learner to return with specific questions, failed attempts or requests for clarification;
- answer direct questions clearly when asked;
- preserve safety guidance for hardware, destructive commands or high-cost actions.

The learner may take notes, solve exercises, reproduce examples and build small artifacts during self-study, but completion is not inferred from resource consumption alone.

## 4. Unit Assessment

After a coherent unit, Horizon may issue a **Unit Test**.

A unit test should feel like a real paper or practical check rather than a guided conversation.

Possible components:

- closed-book recall;
- short explanations;
- hand tracing / derivation;
- coding from a blank file;
- debugging an unfamiliar broken example;
- predicting program / system behavior;
- one nearby transfer problem.

Default rule: do not reveal solutions before submission unless the assessment is explicitly open-book or practice-only.

After submission, grade the work, identify error classes and explain only the gaps that matter.

## 5. Stage Assessment

After several units, use a cumulative **Stage Exam / Midterm** when useful.

It should test whether the learner can choose the correct method without being told which topic is being tested.

Prefer mixed assessment:

- concepts from earlier units;
- unfamiliar combinations;
- debugging;
- design choices;
- transfer;
- explanation of trade-offs.

The purpose is to detect fragile recognition-based learning before it compounds.

## 6. Project / Practical Gate

For engineering domains, a project may be a stronger assessment than a written exam.

A project gate should provide requirements and acceptance criteria but should avoid tutorial-like implementation instructions.

Examples:

- build a Python application from a requirements sheet;
- implement an algorithmic mini-library and pass hidden tests;
- bring up an STM32 peripheral from datasheet / reference material;
- diagnose and repair a Linux environment problem;
- reproduce a small ML baseline and analyze its errors;
- implement a control experiment in simulation and justify the controller.

The learner should decide architecture, implementation order and debugging strategy unless safety or scope requires constraints.

A strong project rubric evaluates:

- correctness;
- robustness / edge cases;
- independent debugging;
- explanation of design decisions;
- reproducibility;
- transfer beyond the exact tutorial example.

## 7. Final Assessment

A subject or block may end with a **Final Exam** when cumulative retrieval matters.

The final may be:

- a written / coding paper;
- a practical lab examination;
- a capstone project;
- a mixed examination + project.

Do not create finals merely for ceremony. If a real project already gives stronger evidence, the project can replace the traditional final.

## 8. Gap Diagnosis

Assessment errors should be classified before remediation.

Common gap classes:

- concept / mental model;
- prerequisite weakness;
- recall failure;
- syntax / API weakness;
- boundary-condition blindness;
- debugging weakness;
- inability to select the right method;
- inability to transfer knowledge;
- weak explanation despite successful execution.

Do not respond to a failed exam by reteaching the entire course.

## 9. Targeted Remediation

After diagnosis, prescribe the smallest useful remediation:

- one chapter;
- one lecture segment;
- a short problem set;
- one debugging exercise;
- one focused explanation;
- one small reconstruction task.

Then retest the weak capability.

If the learner explicitly requests tutoring on the failed area, the Specialist may temporarily switch into guided teaching mode. Guided tutoring is an exception used to repair a concrete gap, not the default learning surface.

## 10. Retest / Transfer

A retest should not merely repeat the original question with changed numbers.

Prefer a nearby but non-identical task so the learner must reconstruct the underlying idea.

Passing means the learner can perform independently with reasonable correctness and explanation, not that they remember the previous answer.

## Assessment Levels

Specialists may use the following vocabulary across domains:

- **Diagnostic / Placement Test** — determine starting level before assigning resources.
- **Unit Test** — one coherent topic or chapter group.
- **Stage Exam / Midterm** — several units, cumulative and mixed.
- **Practical Gate** — live coding, debugging, lab or system task.
- **Project Gate** — build from a requirements / acceptance specification.
- **Final Exam** — cumulative mastery check when useful.
- **Research Gate** — reproduce, critique or extend a result when entering research-level work.

## Default Grading Philosophy

Use rubrics tied to capability rather than arbitrary activity counts.

A useful default interpretation:

- **Mastered** — independently correct, explainable and transferable;
- **Pass with gaps** — functional but with specific weaknesses requiring targeted repair;
- **Not yet passed** — important capability is missing or requires excessive guidance.

Numerical scores may be used when a paper benefits from them, but the score should map back to concrete capability gaps.

For coding and projects, hidden tests or unseen constraints are preferred when practical because they reduce tutorial imitation.

## Exam Integrity Rules

When an assessment is declared closed-book:

- do not provide hints during the attempt unless the user ends the exam mode;
- do not reveal reference solutions before submission;
- grade the submitted work as-is;
- distinguish conceptual mistakes from minor syntax / arithmetic errors;
- after grading, provide corrections and remediation.

When an assessment is open-book, state what resources are permitted.

The learner may always choose to convert an exam into practice; if so, it no longer counts as independent assessment evidence.

## Domain Adaptation

### Algorithm

Use blank-page implementation, invariants, complexity analysis, mixed problem selection, hidden edge cases and transfer problems. Project gates may include a small algorithm library or contest-style set.

### Python / C++

Use coding papers, debugging tasks, tests, small design prompts and projects from requirements. Do not teach every implementation step before the project.

### Linux

Use practical scenarios: inspect state, diagnose faults, repair permissions / processes / environment / networking where safe, and explain commands used.

### Embedded

Use practical hardware gates: create or repair a project, build, flash, debug, measure and explain behavior. Provide safety constraints and hardware references, but avoid tutorialized click-by-click instructions unless explicitly requested.

### Mathematics / Physics

Use derivation, proof / reasoning, calculation, mixed cumulative problems and transfer to unfamiliar applications. Resource packs may contain lectures + textbook + problem book.

### AI / Data / Robot Learning

Use baseline reproduction, coding from specifications, experiment design, metric interpretation, error analysis, ablation reasoning and project / research gates. At advanced stages, assessment should increasingly resemble actual research work rather than textbook quizzes.

## Evidence Standard

A passed milestone should produce evidence appropriate to the domain, such as:

- graded assessment and corrections;
- independently written code;
- hidden-test results;
- hardware demonstration;
- reproducible project;
- derivation / solved set;
- debugging report;
- experiment / research artifact;
- README or concise explanation of design and limitations.

Do not manufacture artifacts merely for appearance.

## Specialist Behavior Rule

Default Specialist behavior for learning work:

1. define the next capability block;
2. recommend the minimal high-quality resource pack;
3. state what must be learned and what can be skipped;
4. define the next assessment gate;
5. let the learner self-study;
6. when the learner returns ready, issue the exam / project specification;
7. grade independent performance;
8. prescribe targeted remediation only where needed;
9. retest or advance.

Do **not** resume continuous step-by-step teaching unless the user explicitly asks for it or a narrowly diagnosed gap justifies a temporary tutoring intervention.

## Relationship to Charter

This mode preserves the Charter principles of:

- create before consuming;
- evidence over imagined mastery;
- real feedback;
- transfer;
- project-driven engineering;
- minimum necessary overhead.

The change is primarily in **who carries the learning process**: the learner now owns normal study; Horizon owns curriculum design, resource curation, assessment and evidence gates.

## Change Log

### v0.2 — 2026-09-01 — Adopted / Active

- Replaces continuous guided-discovery tutoring as the default learning surface with **Self-Study + Assessment**.
- Makes curated video courses, books, official references and problem sources the normal learning input.
- Adds diagnostic tests, unit tests, stage exams, practical gates, project gates and finals.
- Makes guided tutoring an explicit exception for concrete gaps or direct user requests.
- Adds exam-integrity, grading, remediation and retest rules.
- Preserves project-driven evidence and cross-domain adaptation.

### v0.1 — 2026-08-30 — Candidate / Cross-thread Trial

- Used a guided learning loop centered on first attempt, gap exposure, minimum theory, guided discovery, independent construction, feedback, retrieval and transfer.
- Generalized the Algorithm Course teaching mechanism across software, Linux, Embedded, mathematics/physics and AI/data work.
