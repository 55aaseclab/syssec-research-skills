---
name: syssec-foundation
description: >
  Foundation Supervisor for system security research. Handle intake, scope,
  literature survey, baseline mapping, and artifact intake. Use when the work
  is still being framed or when the research needs a stronger factual base
  before implementation or evaluation.
---

# syssec-foundation

`syssec-foundation` is the framing and evidence-base Supervisor.

## Load first

Load the `_system/` protocol layer through `../_system/`.

## Route here when

- the question is still vague
- the threat model is missing
- prior work is unclear
- baseline systems are not mapped
- artifacts, code, datasets, or binaries need inventory

## Workers

| Need | Worker |
|---|---|
| define the task and deliverable | `syssec-intake` |
| define question, assumptions, threat model | `syssec-scope` |
| map literature and gaps | `syssec-survey` |
| choose prior work and comparison baselines | `syssec-baseline` |
| inventory code, datasets, binaries, environments | `syssec-artifact-intake` |

## Standard outputs

- `research-brief.md`
- `questions-and-hypotheses.md`
- `threat-model.md`
- `related-work-map.md`
- `baseline-matrix.md`
- `artifact-inventory.md`

## Boundaries

- Do not claim a baseline is valid before checking comparability.
- Do not move to exploit or defense work with an undefined threat model.
- Do not over-collect artifacts that are not needed for the question.
