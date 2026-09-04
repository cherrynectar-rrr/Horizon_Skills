# Horizon External Skill Scan — 2026-09-04

Status: Completed — Selective Absorption Authorized
Owner: Horizon Core

## Purpose

Survey current public Agent Skill ecosystems and extract only the procedures that can materially improve Project Horizon now or later without turning Skills into a new workload.

This is not a bulk-install decision. Horizon absorbs ideas selectively, rewrites them for its own constraints, preserves provenance, and keeps new methods in Trial until real work proves value.

## Sources Reviewed

Higher-trust / primary references:

- Agent Skills open specification — `agentskills/agentskills` / agentskills.io
- Anthropic public Skills / Skill Creator — `anthropics/skills`
- GitHub Awesome Copilot Skills and official Agent Skills documentation — `github/awesome-copilot`
- OpenAI current skill/plugin examples, including `openai/openai-agents-python`; the old `openai/skills` catalog is deprecated and was not treated as a current install source

Strong engineering-method sources:

- `mattpocock/skills`
- `obra/superpowers`

Lower-trust / idea sources used only for methodology extraction:

- public scientific-agent skill collections covering research methodology, experiment design and literature review

## Intake Filter

A candidate is absorbed only when it passes most of these checks:

1. It solves a recurring Horizon problem rather than creating a new activity.
2. It is meaningfully distinct from an existing Horizon Skill.
3. It improves evidence quality, reliability, learning or decision quality.
4. It can be rewritten without depending on unavailable subagents, proprietary runtimes or a specific editor.
5. Its default workflow is lighter than the cost of the failure it prevents.
6. It respects Horizon Core / Specialist ownership and the human-only showcase boundary.
7. It can be tested on real Horizon work before adoption.

## Absorbed Now — Candidate / Trial

### 1. `completion-verification`

Sources / ideas:

- `obra/superpowers` — `verification-before-completion`
- OpenAI implementation / release review patterns

Why Horizon needs it:

Horizon already forbids plans being recorded as completion, but there was no universal final gate for claims such as "fixed", "works", "passes", "migrated", "build succeeded" or "hardware is working". This Skill makes completion claims evidence-bound.

### 2. `change-review`

Sources / ideas:

- `mattpocock/skills` — `code-review`
- OpenAI final-review patterns

Why Horizon needs it:

As Student Manager V2, competition code, Embedded projects and later research software grow, Horizon needs a review method that separately checks intended behavior and engineering quality instead of collapsing both into generic style feedback.

### 3. `codebase-orientation`

Sources / ideas:

- `github/awesome-copilot` — `acquire-codebase-knowledge`

Why Horizon needs it:

Future lab work, internships, open-source contribution and paper-code reproduction will repeatedly require entering unfamiliar repositories. The upstream skill is intentionally comprehensive; Horizon keeps only a lightweight map-first version and does not generate seven documents by default.

### 4. `source-grounded-research`

Sources / ideas:

- `mattpocock/skills` — `research`
- structured literature-review skills used as secondary methodology references

Why Horizon needs it:

Horizon already requires fresh official facts for admissions, funding, labs, software versions and similar decisions. This Skill extends that rule into an explicit research workflow: question → source hierarchy → evidence → contradiction / uncertainty → synthesis → durable note only when useful.

### 5. `experiment-design`

Sources / ideas:

- research-methodology / experiment-agent skill patterns from public scientific-agent repositories
- OpenAI `runtime-behavior-probe` principles for control cases, validation matrices and claim-scope discipline

Why Horizon needs it:

Earth Flywheel, Embedded measurements, model comparisons and future research all require the ability to design tests that distinguish hypotheses rather than merely collect data. This Skill remains dormant until a real experiment appears.

## Existing Skills Strengthened Instead of Duplicated

### `engineering-debug-loop`

Do not import another `systematic-debugging` Skill. The existing Horizon Skill already covers reproducible signals, minimisation, competing hypotheses, instrumentation and physical-system debugging.

Absorb two useful safeguards from `obra/superpowers`:

- if repeated evidence-backed fixes fail, stop stacking patches and re-question the architecture / assumptions;
- hand completion claims to `completion-verification`.

### `design-grill`

Do not add a second brainstorming/spec Skill.

Absorb two useful ideas from `obra/superpowers`:

- decompose multi-subsystem requests before detailed design;
- run a short coverage / YAGNI check before implementation.

## Architecture Improvements Absorbed

From the Agent Skills specification, Anthropic Skill Creator, GitHub documentation and skill-benchmarking projects:

- new or materially revised Skills should use standard YAML frontmatter with at least `name` and `description`;
- `description` is a routing surface and must say both what the Skill does and when it should trigger;
- use progressive disclosure: keep `SKILL.md` compact, move optional depth into `references/`, deterministic helpers into `scripts/`, and templates into `assets/` only when needed;
- external provenance should be recorded for non-trivial adaptations;
- a Skill should prove value on real tasks, not be adopted because its source repository is popular;
- where practical, compare with-skill vs without-skill outcomes or at least record a natural failure the Skill prevented;
- scripts or tool instructions from external Skills are never imported blindly; inspect capability, side effects, dependencies and license first.

## Deferred — Useful Later, Not Worth Activating Now

- **Security review:** high future value for web/API/auth/network-facing software, but premature as a standing Horizon Skill today. Revisit when a real attack surface exists.
- **Documentation / Diátaxis:** useful when a project grows a real user-facing documentation surface; current README / STATUS split is adequate.
- **Performance audit / profiling:** use `engineering-debug-loop` until real bottlenecks justify a dedicated profiling procedure.
- **Git worktrees / merge-conflict / release workflows:** useful when collaboration and release pressure become real; unnecessary for present solo learning work.
- **Issue triage / global task systems:** rejected for now because Horizon deliberately avoids becoming a project-management bureaucracy.
- **Large quality-playbook / council / multi-agent orchestration systems:** rejected for current Horizon; too much ceremony and context cost relative to current projects.
- **Full systematic literature-review pipelines:** defer until an actual thesis/research question requires systematic-review rigor. Ordinary technical research should not pretend to be a systematic review.

## Trial Rule

The five newly absorbed Skills are not new learning lines. They consume no scheduled study time.

They are invoked only when a natural task matches. Adoption requires evidence that the Skill improves a real Horizon task without disproportionate overhead.

## Bottom Line

The scan supports **selective absorption, not a larger Skill stack**.

The strongest additions are the ones that enforce the Horizon flywheel itself:

`understand → build → observe → verify → review → learn`
