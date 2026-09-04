# Horizon Life & Health Skill Intake — 2026-09-05

Status: Completed — Selective Absorption / Trial
Owner: Horizon Core

## Purpose

Extend Horizon Skills into low-friction life maintenance without importing generic wellness advice, medical overreach or a new self-optimization workload.

The intake was triggered by an active Life Operations need: build a practical Nutrition & Recovery baseline and make everyday behavior change easier to execute.

## Sources Reviewed

### Community Agent Skills — method sources only

- `JayRHa/AgentSkills` — `meal-plan-builder` (MIT)
- `JayRHa/AgentSkills` — `habit-builder` (MIT)
- `JayRHa/AgentSkills` — `workout-planner` (MIT)

Community Skills were treated as workflow inspiration, not health authority.

### Higher-authority health / behaviour references

- WHO — `Healthy diet`, updated 2026-01-26
- NICE PH49 — `Behaviour change: individual approaches`
- CDC sleep guidance / current sleep-health material when sleep-specific facts are needed

For future health facts, Horizon should prefer relevant national official guidance, WHO / authoritative public-health bodies and high-quality professional guidance over community Skills.

## Absorbed Now — Candidate / Trial

### 1. `nutrition-planning v0.1`

Why now:

- directly supports the approved Nutrition & Recovery baseline;
- solves recurring campus-food / budget / convenience decisions;
- can reduce repeated meal-planning effort without creating a new line.

Absorbed:

- focused intake around real constraints;
- budget / convenience trade-offs;
- ingredient overlap and intentional leftovers;
- shopping consolidation;
- batch preparation only when it reduces friction;
- explicit medical-nutrition boundary.

Rejected / softened:

- automatic calorie estimation for every user;
- fixed macro splits;
- universal protein floors;
- narrow daily numeric tolerances;
- detailed seven-day meal grids as the default output.

Horizon default: **decision rules + repeatable meal architecture before precision tracking**.

### 2. `habit-change v0.1`

Why now:

- recurring real use cases already exist: sleep timing, study-start friction, phone distraction, nail biting and other everyday routines;
- behaviour-change support is useful across Life Operations without deserving a separate thread.

Absorbed:

- define one observable behavior;
- map cue / context;
- make desired behavior easier and unwanted behavior harder;
- start small;
- use replacement behavior when reducing a habit;
- review and adapt from real behavior.

Strengthened with NICE behaviour-change guidance:

- explicit goals and action planning;
- if-then coping / relapse plans;
- feedback / monitoring only where useful;
- environmental restructuring;
- capability / opportunity / motivation as a diagnostic frame;
- long-term maintenance and recovery rather than streak perfection.

Rejected / softened:

- rigid `never miss twice` doctrine;
- identity framing as a mandatory mechanism;
- immediate rewards / streaks as universal requirements;
- complicated habit dashboards.

Horizon default: **small experiment → environmental change → explicit action / recovery plan → minimal monitoring → review**.

## Deferred

### `workout-planning`

Useful later, but not activated as a standing Horizon Skill now.

Reason:

- the current Life Operations scope is Nutrition & Recovery;
- a separate structured training programme has not yet demonstrated enough recurring need;
- the community Skill contains many prescriptive volume / rep / split defaults that require stronger domain-specific verification before reuse.

If the user begins regular training and needs repeated programme design / adjustment, revisit the smallest useful training Skill then.

### `recovery-check`

Not created as a separate Skill yet.

Reason:

- ordinary recovery / sleep guardrails can initially live inside Nutrition & Recovery and use `habit-change` where the problem is behavioral;
- creating a third Life Skill before real use would add architecture before evidence.

Revisit only if repeated recovery decisions show a distinct recurring workflow.

## Health Safety Rule

Life / health Skills must use a stricter evidence boundary than ordinary engineering workflow Skills.

- community Skills may contribute process ideas;
- mutable or quantitative health claims should be freshly verified from authoritative sources when material;
- clinical diagnosis / treatment, significant injury, dangerous symptoms, eating disorders, addiction and similar issues are outside ordinary optimization Skills;
- do not represent the AI as a physician, dietitian, therapist or certified trainer.

## Trial Rule

Both new Skills are **Candidate / Trial**.

They should be tested on the user's actual Life Operations baseline rather than through artificial benchmark tasks.

Useful evidence includes:

- less repeated planning effort;
- a simpler food system that survives the real campus environment;
- a behavior change that becomes easier to start / resume;
- fewer repeated decisions or reminders;
- no meaningful safety or tracking burden.

Adopt only if real use proves they reduce friction.

## Bottom Line

Current Life Skill stack remains deliberately small:

```text
nutrition-planning v0.1   — Candidate
habit-change v0.1         — Candidate
workout-planning          — Deferred
recovery-check            — Deferred / handled locally for now
```

The next step is not another scan. It is a real Nutrition & Recovery plan using these Skills.
