---
name: source-grounded-research
description: Research a factual, strategic, technical, or academic question using traceable high-quality sources, explicit uncertainty, and contradiction checks. Use when Horizon needs current external facts, technical documentation research, lab/program comparison, policy verification, or a scoped literature synthesis.
metadata:
  version: "0.1"
  status: "candidate-trial"
  owner: "Horizon Core"
---

# Source-Grounded Research

## Purpose

Turn research from "find something that sounds right" into a traceable evidence process.

Default flow:

`question → source hierarchy → search → claim/evidence check → contradiction hunt → synthesis → uncertainty → durable note only if useful`

## 1. Define the Question

State the question narrowly enough that evidence can change the answer.

When the research supports a decision, identify the decision separately from the research question.

Example:

- research question: What are the current language and admission requirements for programme X?
- decision question: Is programme X still worth keeping as a target for Horizon?

Do not let research automatically make the strategic decision.

## 2. Use a Source Hierarchy

Prefer sources that own the fact.

### Mutable policy / programme / software facts

Prefer:

1. official current documentation / regulation / programme page;
2. first-party API / source code / release notes;
3. primary institutional communication;
4. high-quality secondary sources only for context or discovery.

### Scientific / technical claims

Prefer:

1. original paper / specification / benchmark report / dataset documentation;
2. credible replication or independent comparative evidence;
3. review papers for field-level synthesis;
4. secondary explainers for orientation, not as sole support for important claims.

Use community discussions for lived experience when that is the actual question, but label them as anecdotal evidence.

## 3. Check Freshness

For facts that can change, record or notice the source date / current state.

Do not recycle old Horizon research as current verification merely because it was once correct.

If a current authoritative source cannot be found, state the limitation.

## 4. Search for Disconfirmation

After finding evidence for the leading answer, deliberately look for:

- an official exception;
- a newer rule;
- a competing empirical result;
- contradictory documentation;
- a limitation that changes the practical conclusion.

Do not stop at the first confirming source.

## 5. Keep Claims Traceable

For important research, maintain a compact internal or written claim ledger:

```text
Claim
→ Evidence / source
→ Date / version when relevant
→ Confidence
→ Caveat / contradiction
```

A claim without a source is either inference or an unresolved hypothesis; label it accordingly.

## 6. Synthesize, Do Not Just Collect

A useful result should answer:

- What is strongly supported?
- What is plausible but uncertain?
- What sources disagree?
- What important evidence is missing?
- What does this imply for the current Horizon question?

For literature-oriented work, a useful synthesis can distinguish:

- established findings;
- active disagreements;
- methodological patterns;
- gaps / unresolved questions;
- the most informative next paper or experiment.

## 7. Do Not Pretend a Scoped Search Is a Systematic Review

Use terms such as **scoped review**, **evidence scan** or **literature synthesis** unless the work actually records a systematic search protocol, databases, search strings, inclusion / exclusion criteria and screening process.

Rigor should match the claim.

## 8. Persistence Rule

Save a cited research note only when it is likely to be reused, such as:

- graduate-programme rules;
- strategic route comparison;
- research-direction evidence;
- a technical decision with non-obvious source work;
- literature synthesis that will feed an experiment / project.

For a one-off factual answer, do not create a repository artifact merely to prove research happened.

When saving, put the note with the owner of the decision / project rather than creating a second source of truth.

## 9. Separate Source-Derived Content from Inference

Use explicit language when needed:

- **Source says:** directly supported fact.
- **Inference:** reasonable conclusion from several facts.
- **Horizon judgment:** decision after weighing evidence and constraints.

Do not write strategic judgment as if an external source itself endorsed Horizon's decision.

## Trial Gate

Pass when a real research task finds a meaningful current fact, contradiction or uncertainty that materially improves a Horizon decision / implementation and remains traceable to its sources.

## Attribution

Conceptually adapted from Matt Pocock's MIT-licensed `research` Skill, with additional ideas from structured literature-review workflows in public scientific-agent repositories.

Horizon adaptation removes the mandatory background-agent assumption and integrates current-fact verification, contradiction search and strategy / evidence separation.
