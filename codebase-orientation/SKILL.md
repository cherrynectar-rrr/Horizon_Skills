---
name: codebase-orientation
description: Build a lightweight evidence-backed map of an unfamiliar codebase before substantial modification. Use when onboarding into a lab, internship, open-source, research-code, or unfamiliar project repository, or when the user explicitly asks to map or understand a repo.
metadata:
  version: "0.1"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Codebase Orientation

## Purpose

Understand enough of an unfamiliar repository to work safely without turning onboarding into a documentation project.

Default flow:

`stated intent → executable reality → entrypoints → relevant data/control flow → conventions/tests → risks/unknowns → first safe task`

## Trigger Boundary

Use when:

- first entering a lab / internship / open-source repository;
- reproducing research code from an unfamiliar project;
- taking ownership of a substantial existing module;
- the user asks to map, explain or onboard into a codebase.

Do not run for a narrow edit in a codebase that is already understood.

## 1. Read Intent Before Source Details

Start with the repository's own stated intent when available:

- README;
- contribution guide;
- design / architecture docs;
- task / issue / paper associated with the code.

Treat these as **intent**, not proof of current implementation.

## 2. Verify the Executable Reality

Inspect evidence such as:

- language / package manifests;
- build files;
- entrypoints;
- source tree;
- tests;
- CI configuration;
- example configuration files;
- recent relevant changes when necessary.

Do not infer frameworks, architecture, database, hardware or runtime behavior from names alone.

Generated / build output is not a source-of-truth for coding conventions.

## 3. Build the Minimum Useful Map

Answer only what is needed to become productive:

### Purpose
What does the repository actually appear to do?

### Run / Build / Test
What are the known commands or procedures to execute and verify it?

### Entry Points
Where does execution start?

### Relevant Structure
Which modules / folders matter to the current task?

### Main Flow
Trace one important control / data path through the system.

### External Boundaries
What hardware, services, files, databases, APIs, environment variables or other repositories does it depend on?

### Tests / Observability
How can we tell whether a change works?

### Conventions
What repo-owned style / architecture rules are visible and actually relevant?

### Concerns / Unknowns
What cannot be established from current evidence?

## 4. Distinguish Intent from Reality

If README / docs disagree with implementation, record the divergence rather than silently choosing one.

Examples:

- docs say Python 3.10, CI uses 3.12;
- architecture doc names a module that no longer exists;
- paper describes preprocessing that current script does differently.

This divergence may be the most important onboarding result.

## 5. Scope to the Task

For a large repository, do not map the whole system by default.

Map the smallest slice that lets the user safely perform the current task, then expand only when a dependency crosses the boundary.

## 6. Evidence and Unknowns

Attach paths, commands or runtime evidence to non-trivial claims when useful.

Use explicit labels:

- **Verified** — supported by files / commands / runtime observation;
- **Likely** — strong inference but not yet confirmed;
- **Unknown** — current evidence is insufficient;
- **Needs human context** — team intent cannot be recovered from the repository.

Never fill unknowns just to make the map look complete.

## Persistence Rule

Default output is a concise in-chat orientation.

Create or update a durable codebase map only when repeated work in that repository will benefit from it. Do not generate a fixed set of documents merely because a template exists.

## First Safe Task

Finish by identifying one low-risk task or verification action that would deepen understanding while producing real value.

Examples:

- run the existing tests;
- trace one real request / sensor packet;
- reproduce one known issue;
- change one small feature behind an existing test seam.

Do not immediately refactor architecture during onboarding.

## Trial Gate

Pass when a real unfamiliar repository is entered and the Skill reduces incorrect assumptions, unnecessary reading or unsafe first edits.

## Attribution

Conceptually adapted from GitHub Awesome Copilot's MIT-licensed `acquire-codebase-knowledge` Skill.

Horizon adaptation is intentionally lighter: no mandatory seven-document output, and discovery expands only as current work requires.
