---
name: syssec-method-design
description: >
  Method Design Worker for system security research. Turn a scoped question,
  threat model, target understanding, and baseline plan into a concrete method
  design that is implementable and evaluable. Use when the study needs a clear
  mechanism before prototyping or evaluation.
---

# syssec-method-design

Use `syssec-method-design` to convert an interesting idea into a bounded
technical plan.

## Reference

- `references/design-checklist.md`

## Inputs

- research question and hypotheses
- threat model
- target-understanding notes
- baseline matrix
- artifact inventory

## Outputs

- `method-design.md`
- proof-obligation list
- implementation boundary
- evaluation hooks

## Workflow

1. State the exact security property or attack path the method targets.
2. Define the mechanism and where it sits in the system.
3. Bind the method to assumptions and threat boundaries.
4. List what has to be implemented, instrumented, or emulated.
5. Map the method to evaluation questions and expected evidence.

## Boundaries

- A design is not a validated result.
- If the target system is still unclear, route back to
  `syssec-target-understanding`.
- If the design cannot be evaluated under the current constraints, say so
  before implementation starts.
