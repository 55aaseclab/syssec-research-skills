---
name: syssec-baseline
description: >
  Baseline Worker for system security research. Choose the prior systems,
  methods, or settings that should be compared and explain why they are fair.
  Use when the study needs comparison discipline.
---

# syssec-baseline

Use `syssec-baseline` to define what the work must outperform, match, or
contextualize.

## Inputs

- related-work map
- threat model
- target deployment context
- available artifacts

## Outputs

- `baseline-matrix.md`
- fairness notes
- infeasible baseline notes

## Workflow

1. List candidate baselines from prior work.
2. Check whether assumptions and deployment targets are comparable.
3. Separate mandatory baselines from aspirational ones.
4. Record why each kept or dropped baseline is justified.
5. Mark which baselines require reproduction or artifact intake next.

## Boundaries

- Do not compare incompatible threat models without saying so.
- Do not hide dropped baselines without a reason.
