---
name: syssec-fuzzing
description: >
  Fuzzing Worker for system security research. Design and run input exploration
  campaigns to uncover crashes, state divergences, or policy violations. Use
  when automated search can test the hypothesis space better than hand-picked
  inputs.
---

# syssec-fuzzing

Use `syssec-fuzzing` for automated discovery under a defined target and safety
boundary.

## Inputs

- target surface
- input model or harness idea
- crash or oracle definition

## Outputs

- fuzzing plan
- corpus or seed notes
- crash or divergence records
- triage priorities

## Workflow

1. Define the target interface and oracle.
2. Choose or design a harness.
3. Define seeds, mutations, and stop conditions.
4. Record crashes, hangs, or semantic failures.
5. Route confirmed issues to exploit, reproduction, or disclosure.

## Boundaries

- Do not confuse a crash with a security impact.
- Do not run uncontrolled campaigns against unsafe targets.
