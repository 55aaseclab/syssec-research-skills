---
name: syssec-investigation
description: >
  Investigation Supervisor for system security research. Handle target
  understanding, reverse engineering, static and dynamic analysis, fuzzing,
  exploit work, and defense prototyping. Use when the work shifts from framing
  to technical investigation or implementation.
---

# syssec-investigation

`syssec-investigation` owns the technical middle of the research lifecycle.

## Load first

Load the `_system/` protocol layer through `../_system/`.

## Route here when

- the target system must be understood
- code or binaries need analysis
- an attack path or defense needs implementation
- fuzzing or dynamic observation is required

## Workers

| Need | Worker |
|---|---|
| understand architecture and attack surface | `syssec-target-understanding` |
| reverse binaries or closed components | `syssec-reverse` |
| inspect source statically | `syssec-static-analysis` |
| observe runtime behavior | `syssec-dynamic-analysis` |
| explore input space automatically | `syssec-fuzzing` |
| build or validate a PoC | `syssec-exploit` |
| implement a defense prototype | `syssec-defense-prototype` |

## Standard outputs

- `system-notes.md`
- `attack-surface-map.md`
- `method-design.md`
- `prototype-notes.md`
- `findings-log.md`

## Boundaries

- Do not skip back to scope if assumptions collapse; route back explicitly.
- Do not claim exploitability from suspicious code without validation.
- Do not claim a defense works without routing to validation.
