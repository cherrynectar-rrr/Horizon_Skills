---
name: nutrition-planning
description: Use when the user wants a practical meal, canteen, takeout, shopping, or food-budget plan that supports everyday health with minimal friction. Build from the user's real food environment, cost, time, preferences and constraints. Do not use as medical nutrition therapy or as a rigid calorie/macro prescription engine.
metadata:
  version: "0.1"
  lifecycle: "Candidate / Trial"
  owner: "Horizon Core"
---

# Nutrition Planning

Version: 0.1  
Status: Candidate — Trial  
Owner: Horizon Core  
Created: 2026-09-05

## Purpose

Build a realistic, economical and low-maintenance food system that can survive ordinary university life.

The goal is not a theoretically perfect diet. The goal is a repeatable set of choices that supports health, stable energy, study and recovery without turning eating into a tracking project.

## Trigger

Use when the user asks for:

- a daily / weekly eating plan;
- campus canteen or takeout decision rules;
- a low-budget food plan;
- a grocery / stocking list;
- simple meal prep or ingredient reuse;
- help reducing food friction or waste;
- a practical nutrition baseline.

## Safety Boundary

This Skill is for ordinary planning, not diagnosis or medical nutrition therapy.

Do not use it to independently manage:

- eating disorders;
- diabetes or other clinically significant metabolic conditions;
- renal, hepatic or other disease-specific diets;
- severe allergies without appropriate medical guidance;
- pregnancy-specific medical nutrition;
- unexplained major weight change or other clinically concerning symptoms.

When a plan depends on a quantitative health recommendation, supplement limit, food-safety rule or other mutable health fact, verify a current authoritative source before treating the number as reliable.

Do not hard-code one universal calorie target, macro split, protein target or weight-loss rate as the default for all users.

## Minimum Intake

Collect only what materially changes the plan:

1. **Environment** — canteen, takeout, dorm food, kitchen / refrigerator access.
2. **Budget** — approximate food budget and where cost pressure is real.
3. **Schedule** — which meals are rushed, skipped or hard to obtain.
4. **Current pattern** — a normal day or several representative meals.
5. **Goals** — e.g. stable energy, adequate nutrition, convenience, training support, cost control.
6. **Preferences / hard constraints** — dislikes, dietary restrictions, allergies, foods that are unrealistic to sustain.
7. **Exercise context** — only when it materially changes food planning.

Do not ask for sensitive medical information unless the user raises a specific health question that genuinely requires it.

## Core Workflow

```text
real environment
→ identify the biggest food friction / gap
→ define a minimum viable meal architecture
→ create simple decision rules
→ reduce cost and preparation friction
→ add shopping / prep only where useful
→ test in real life
→ review and simplify
```

### 1. Find the real constraint

Do not begin with an ideal menu. First identify what actually breaks the user's eating pattern:

- cost;
- inconvenient meal timing;
- low protein / produce variety;
- excessive takeout;
- no cooking access;
- too much decision-making;
- skipped breakfast / lunch;
- food waste;
- poor stocking.

Fix the highest-value constraint first.

### 2. Build a repeatable meal architecture

Prefer a small number of reusable meal patterns over seven completely different days.

A meal architecture may use simple anchors such as:

- staple / main carbohydrate;
- practical protein source;
- vegetables / fruit;
- water / ordinary beverage;
- optional add-ons only when they solve a real need.

The exact foods should reflect the user's environment and preferences.

### 3. Use decision rules before detailed menus

Campus life often benefits more from rules than from a rigid schedule.

Examples of rule shape:

- at the canteen, choose one reliable protein + staple + vegetable combination;
- if one meal is weak, repair the next meal rather than declaring the day failed;
- keep a small set of shelf-stable / dorm-friendly backup foods;
- use repeated breakfast or snack options to remove unnecessary decisions.

Do not turn examples into universal prescriptions.

### 4. Reduce cost and waste

Absorb the useful parts of the external `meal-plan-builder` pattern:

- overlap ingredients across meals;
- intentionally reuse leftovers;
- consolidate shopping quantities;
- surface the trade-off between cost and convenience;
- prefer a few reliable staples over a high-variety shopping list when the user values simplicity.

Shopping lists should map to real purchasable quantities rather than mathematically precise but impractical fractions.

### 5. Quantify only when it answers a real question

Calorie, macro or micronutrient calculations are optional tools, not the default surface.

Use numbers when they materially help with a concrete goal and can be justified from current reliable guidance. State assumptions and uncertainty.

Avoid pseudo-precision.

### 6. Produce the smallest useful plan

Default output should be compact:

- daily meal architecture;
- 3–6 practical decision rules;
- a short backup-food / shopping list when useful;
- the most important current gap;
- one review point after real use.

A detailed 7-day menu is appropriate only when the user actually benefits from that level of structure.

### 7. Review from reality

After several days or a week, ask what actually failed:

- too expensive?
- too inconvenient?
- hunger / satiety problems?
- canteen availability mismatch?
- food spoiled?
- too much prep?
- plan ignored because it was too complicated?

Change the plan, not the user's self-description.

## Evidence / Source Policy

For ordinary planning, use strong public-health guidance as the factual floor and tailor execution to the user's environment.

Preferred source hierarchy when facts need verification:

1. current national health authorities / official dietary guidance relevant to the user;
2. WHO and other authoritative public-health bodies;
3. high-quality professional guidelines;
4. peer-reviewed evidence when a narrower question requires it;
5. community Skills only as workflow inspiration, never as authority for medical or quantitative claims.

## Provenance

Method source inspected:

- `JayRHa/AgentSkills` — `meal-plan-builder` (MIT).

Absorbed:

- focused intake;
- budget / convenience constraints;
- ingredient overlap;
- intentional leftovers;
- consolidated grocery lists;
- batch-prep only when it saves effort;
- explicit medical-nutrition boundary.

Deliberately not adopted as universal defaults:

- automatic calorie estimation for every user;
- fixed macro splits;
- a universal protein floor;
- narrow numeric tolerances for every day's intake;
- detailed weekly meal grids when a few decision rules would be lighter.

## Success Test

The Skill succeeds when the user can eat reasonably well for several weeks with less cost, less decision friction and little or no tracking burden.

If the plan requires constant logging, repeated recalculation or frequent AI consultation to survive ordinary life, simplify it.
