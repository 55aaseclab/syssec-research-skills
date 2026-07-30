---
name: syssec-artifact-intake
description: >
  Artifact Intake Worker for system security research. Inventory papers, code,
  binaries, datasets, traces, configs, and environment prerequisites. Use when
  the project needs to know what can actually be reproduced or analyzed.
---

# syssec-artifact-intake

Use `syssec-artifact-intake` to turn scattered research assets into a usable
inventory.

## Inputs

- paper links or names
- repositories or artifact packages
- binary drops or images
- dataset and license notes

## Outputs

- `artifact-inventory.md`
- environment prerequisite list
- missing artifact list
- access-risk notes

## Workflow

1. List all artifacts and versions.
2. Classify each as source, binary, dataset, trace, or document.
3. Record licenses, access limits, and missing dependencies.
4. Mark what is sufficient for reproduction, review, or only paper analysis.
5. Recommend the next stage.

## Boundaries

- Do not assume the artifact package is complete.
- Route to degradation mode when critical pieces are missing.
