---
name: syssec-validation
description: >
  Validation Supervisor for system security research. Handle reproduction,
  experiment design, evaluation, performance, compatibility, statistics, and
  threats to validity. Use when claims need disciplined testing or when prior
  work must be reproduced.
---

# syssec-validation

`syssec-validation` turns methods and claims into measured results.

## Load first

Load the `_system/` protocol layer through `../_system/`.

## Route here when

- a paper or artifact must be reproduced
- an experiment matrix must be designed
- results must be gathered or interpreted
- performance or compatibility claims need proof
- threats to validity need explicit treatment

## Workers

| Need | Worker |
|---|---|
| reproduce prior work | `syssec-reproduction` |
| define variables and experiment matrix | `syssec-experiment-design` |
| run and summarize evaluation | `syssec-evaluation` |
| isolate performance cost | `syssec-performance` |
| check portability and deployment fit | `syssec-compatibility` |
| summarize significance and uncertainty | `syssec-statistics` |
| write validity limits honestly | `syssec-threats-validity` |

## Standard outputs

- `reproduction-log.md`
- `experiment-matrix.md`
- `results-summary.md`
- `performance-notes.md`
- `compatibility-notes.md`
- `validity-notes.md`

## Boundaries

- Do not accept unlogged one-off runs as final evidence.
- Do not mix unsupported performance and security claims.
- Do not send writing-ready conclusions upstream before validity is checked.
