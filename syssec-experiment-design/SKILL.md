---
name: syssec-experiment-design
description: >
  Experiment Design Worker for system security research. Define variables,
  metrics, datasets, baselines, trial structure, and expected observations. Use
  when a method or reproduced artifact needs disciplined evaluation.
---

# syssec-experiment-design

Use `syssec-experiment-design` to make the evaluation plan explicit before
running it.

## Inputs

- scope and hypotheses
- baseline matrix
- available artifacts
- method or prototype notes

## Outputs

- `experiment-matrix.md`
- metric definitions
- trial plan
- benchmark scope notes

## Workflow

1. Define dependent and independent variables.
2. Define the tested environments and inputs.
3. Match each hypothesis to a metric and comparison.
4. Define trial count, warm-up, and failure handling.
5. Record what evidence each experiment is expected to produce.

## Boundaries

- Do not let benchmarks drift away from the research question.
- Route back if the required baseline or artifact is still missing.
