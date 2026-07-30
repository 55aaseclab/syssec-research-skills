---
name: syssec-target-understanding
description: >
  Target Understanding Worker for system security research. Build a structured
  picture of the target system, trust boundaries, components, and attack
  surface. Use when the study needs architectural clarity before deeper
  analysis or prototyping.
---

# syssec-target-understanding

Use `syssec-target-understanding` to create an architectural and security
context for later technical work.

## Inputs

- target artifact inventory
- available docs or source
- scope and threat model

## Outputs

- `system-notes.md`
- architecture summary
- trust-boundary summary
- attack-surface map

## Workflow

1. Identify major components and privilege boundaries.
2. Map data flow, control flow, and trust transitions.
3. Highlight interfaces exposed to attackers or defenders.
4. Mark observability points and candidate chokepoints.
5. Recommend static, dynamic, reverse, or fuzzing paths.

## Boundaries

- Do not confuse missing knowledge with confirmed simplicity.
- Route back to scope if the real target differs from the assumed one.
