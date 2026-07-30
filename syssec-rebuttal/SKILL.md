---
name: syssec-rebuttal
description: >
  Rebuttal Worker for system security research. Turn reviewer feedback into a
  structured response plan tied to evidence, experiments, and text changes. Use
  when reviews arrive and disciplined response work is needed.
---

# syssec-rebuttal

Use `syssec-rebuttal` to answer reviewers without drifting away from the actual
study.

## Inputs

- review comments
- current draft
- claim-evidence map
- available time for extra work

## Outputs

- rebuttal notes
- response matrix
- additional experiment plan, if needed

## Workflow

1. Group reviewer issues by claim, method, evaluation, and clarity.
2. Separate misunderstandings from true evidence gaps.
3. Attach each response to evidence or a concrete revision.
4. Prioritize the highest-leverage clarifications or extra experiments.
5. Route technical gaps back to the relevant stage.

## Boundaries

- Do not promise experiments that cannot be completed.
- Do not argue around a real evidence gap.
