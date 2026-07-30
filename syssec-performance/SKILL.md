---
name: syssec-performance
description: >
  Performance Worker for system security research. Quantify overhead, resource
  cost, scaling behavior, and operational trade-offs. Use when the study
  claims a defense or system change is practical.
---

# syssec-performance

Use `syssec-performance` to isolate cost and deployment implications.

## Inputs

- experiment matrix
- evaluation outputs
- baseline systems

## Outputs

- performance notes
- overhead summary
- scaling observations
- cost caveats

## Workflow

1. Define the relevant cost dimensions.
2. Compare against appropriate baselines.
3. Separate median behavior from tail behavior.
4. Record environmental sensitivity.
5. Route to compatibility or writing after the cost story is honest.

## Boundaries

- Do not market average overhead while hiding worst-case collapse.
- Performance claims require the tested setup to be named.
