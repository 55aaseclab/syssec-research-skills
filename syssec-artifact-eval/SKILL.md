---
name: syssec-artifact-eval
description: >
  Artifact Evaluation Worker for system security research. Prepare, audit, and
  document a reproducible evaluation package for reviewers or artifact
  committees. Use when the research must be replayable by others.
---

# syssec-artifact-eval

Use `syssec-artifact-eval` to make the research package testable by outsiders.

## Inputs

- paper draft
- reproduction log
- environment and setup notes
- scripts, code, and datasets

## Outputs

- artifact-eval notes
- replay checklist
- packaging gaps

## Workflow

1. Define the minimal replay path.
2. Check setup, run, and expected-output documentation.
3. Check that versions, scripts, and data pointers are consistent.
4. Mark heavyweight or unreplayable parts honestly.
5. Route missing pieces back to reproduction or submission.

## Boundaries

- Do not claim "artifact available" if replay steps are incomplete.
- Prefer a small working package over a large broken one.
