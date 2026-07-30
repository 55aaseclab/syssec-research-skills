---
name: syssec-statistics
description: >
  Statistics Worker for system security research. Summarize variance,
  significance, confidence, and uncertainty in measured results. Use when
  repeated runs or comparative results need disciplined interpretation.
---

# syssec-statistics

Use `syssec-statistics` when the result interpretation depends on more than a
single observed number.

## Inputs

- raw run results
- experiment matrix
- result summaries

## Outputs

- uncertainty notes
- summary statistics
- significance caveats
- weak-result flags

## Workflow

1. Check trial counts and result completeness.
2. Compute and report descriptive statistics.
3. Apply only justified significance language.
4. Highlight unstable or underpowered comparisons.
5. Route to synthesis once the uncertainty is visible.

## Boundaries

- Do not imply significance without enough evidence.
- Do not let a noisy number become a headline claim.
