---
name: change-review
description: Review a meaningful code or project change against both intended behavior and engineering quality. Use for branches, diffs, project milestones, pre-handoff review, or when the user asks whether a change is correct, complete, maintainable, or ready to keep.
metadata:
  version: "0.1"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Change Review

## Purpose

Review the change that was actually made, not an imagined ideal codebase.

Keep two questions separate:

1. **Behavior / Spec:** Did the change implement the intended behavior and scope?
2. **Engineering / Risk:** Is the implementation understandable, testable and appropriately robust for this project?

A change can pass one axis and fail the other.

## Trigger Boundary

Use for meaningful changes such as:

- Student Manager V2 features;
- competition data / analysis pipeline changes;
- Embedded state machines, protocols or drivers;
- research tooling;
- project milestones or handoffs;
- PR / branch / diff review.

Do not run a formal review for every tiny learning exercise or one-line edit.

## 1. Pin the Review Target

Prefer a concrete change boundary:

- Git diff against a commit / branch / merge-base;
- user-supplied changed files;
- one completed feature slice;
- one milestone artifact set.

Do not review unrelated historical code unless it is necessary to understand a changed behavior.

## 2. Recover Intended Behavior

Use the strongest available requirement source:

- explicit user request;
- project gate / README;
- issue / spec / task description;
- existing behavior or test contract.

If there is no formal spec, state that clearly and review only against the available intent.

## 3. Behavior / Spec Axis

Check for:

- missing requested behavior;
- partially implemented requirements;
- wrong edge-case behavior;
- scope creep that was not requested;
- contradictions between docs / tests / implementation;
- regression against behavior that should remain stable.

Tie each finding to the requirement or observable behavior it affects.

## 4. Engineering / Risk Axis

Review only risks that matter for this project's maturity and current scope.

Consider:

- unclear names or control flow that materially hides intent;
- duplicated logic likely to diverge;
- unnecessary abstraction / speculative generality;
- error handling at real boundaries;
- state / ownership confusion;
- resource lifetime / persistence problems;
- unsafe assumptions about inputs;
- performance only when scale makes it material;
- security only when there is a real attack / trust boundary;
- testability and observability;
- hardware safety / failure behavior for Embedded work.

Repository conventions override generic style preferences.

Do not turn code review into a style lecture.

## 5. Evidence Check

For each important positive or negative conclusion, ask what evidence supports it:

- test;
- reproduction;
- diff / code path;
- runtime output;
- data result;
- hardware observation;
- requirement text.

Do not assume passing tests cover requirements they do not exercise.

## 6. Prioritize Findings

Use three levels:

- **Blocking:** wrong behavior, unsafe behavior, corrupted / unreproducible evidence, or a gate cannot honestly pass.
- **Important:** meaningful maintainability, reliability or scope risk worth fixing before the next major step.
- **Optional:** improvement that can safely wait.

Prefer a few high-signal findings over a long list of cosmetic comments.

## 7. Learning Mode

When reviewing the user's learning code, preserve authorship and diagnostic value.

Separate:

- actual correctness / reliability problems;
- design trade-offs;
- style preferences.

Do not replace the whole solution merely because a cleaner one exists. Explain why a change matters and let the learner fix it when that produces stronger evidence.

## Output

Default concise format:

```text
Behavior / Spec
- [severity] finding → evidence → consequence

Engineering / Risk
- [severity] finding → evidence → consequence

Verification gaps
- what still needs to be run / observed

Verdict
- Keep / Fix before gate / Rework scope
```

If there are no material findings, say so without inventing nits.

## Handoff

After accepted fixes, use `completion-verification` before declaring the feature / milestone complete.

## Trial Gate

Pass when one real review catches a meaningful behavior or engineering issue, or provides useful confidence with low review overhead.

## Attribution

Conceptually adapted from Matt Pocock's MIT-licensed `code-review` Skill, especially the separation of Spec and Standards axes, plus risk-focused final-review patterns from public OpenAI repositories.

Horizon adaptation removes mandatory subagents / issue-tracker infrastructure and adds beginner-learning, data and Embedded review boundaries.
