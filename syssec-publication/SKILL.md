---
name: syssec-publication
description: >
  Publication Supervisor for system security research. Handle synthesis,
  writing, related work, figures, submission readiness, rebuttal, disclosure,
  and artifact evaluation. Use when the work must be turned into a defensible
  paper or a responsible post-discovery package.
---

# syssec-publication

`syssec-publication` converts validated work into publication and disclosure
artifacts.

## Load first

Load the `_system/` protocol layer through `../_system/`.

## Route here when

- findings must be turned into claims
- a paper outline or section draft is needed
- figures or tables need narrative support
- a submission package needs checking
- disclosure, rebuttal, or artifact evaluation is active

## Workers

| Need | Worker |
|---|---|
| align claims to evidence | `syssec-synthesis` |
| draft the paper | `syssec-write` |
| structure related work | `syssec-related-work` |
| define figures and tables | `syssec-figures` |
| prepare submission package | `syssec-submission` |
| answer review feedback | `syssec-rebuttal` |
| manage responsible disclosure | `syssec-disclosure` |
| prepare artifact evaluation package | `syssec-artifact-eval` |

## Standard outputs

- `claim-evidence-map.md`
- `paper-outline.md`
- `figures-plan.md`
- `submission-checklist.md`
- `rebuttal-notes.md`
- `disclosure-log.md`

## Boundaries

- Do not introduce new unsupported claims during writing.
- Do not hide weak evidence behind polished prose.
- Do not publish exploit detail that should stay inside disclosure flow.
