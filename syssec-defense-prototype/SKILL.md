---
name: syssec-defense-prototype
description: >
  Defense Prototype Worker for system security research. Design or implement a
  bounded defense prototype with explicit assumptions, trust boundaries, and
  deployment expectations. Use when the study proposes mitigation or a new
  protection mechanism.
---

# syssec-defense-prototype

Use `syssec-defense-prototype` to turn a defense idea into something that can
be validated.

## Inputs

- threat model
- baseline systems
- target-understanding notes
- design objectives

## Outputs

- prototype notes
- implementation boundary
- expected guarantees
- evaluation dependencies

## Workflow

1. Define the security property the defense targets.
2. Define where it sits in the system.
3. Define what assumptions it needs.
4. Implement or specify the smallest useful prototype.
5. Route to evaluation, performance, and compatibility testing.

## Boundaries

- Do not claim soundness from design intent alone.
- Keep unsupported deployment assumptions explicit.
