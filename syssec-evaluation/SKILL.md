---
name: syssec-evaluation
description: >
  Evaluation Worker for system security research. Execute the experiment matrix,
  summarize security and correctness results, and preserve the raw evidence
  trail. Use when a study needs measured outputs.
---

# syssec-evaluation

Use `syssec-evaluation` to turn an experiment plan into evidence-backed
results.

## Inputs

- experiment matrix
- runnable artifacts
- benchmark inputs

## Outputs

- `results-summary.md`
- raw result references
- anomalies and failure cases
- claim support table

## Workflow

1. Run the planned experiment matrix.
2. Separate successful, failed, and inconclusive runs.
3. Summarize results by hypothesis or claim.
4. Record anomalies, outliers, and environment notes.
5. Route to performance, statistics, or validity analysis as needed.

## Boundaries

- Do not collapse raw evidence into prose without keeping the trail.
- One result table is not the same as a validated claim set.
