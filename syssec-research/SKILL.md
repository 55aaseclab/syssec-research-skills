---
name: syssec-research
description: >
  Full-lifecycle Hub for system security research. Detect the current research
  stage, choose a workflow, route to the right Supervisor, and keep evidence,
  ethics, and reproducibility explicit. Use when the user asks for broad system
  security research help, end-to-end coordination, or stage planning.
---

# syssec-research

`syssec-research` is the Hub. It does not do all research itself. It decides
where the work is in the lifecycle, what workflow fits, and which Supervisor
should move the work forward.

> **Version**: `v0.1.1`

## Load first

Before doing visible work, load:

- `../_system/preamble.md`
- `../_system/evidence-rules.md`
- `../_system/reproducibility-rules.md`
- `../_system/ethics-and-disclosure.md`
- `../_system/degradation-rules.md`
- `../_system/output-format.md`
- `../_system/handoff-contract.md`
- `../_system/workflow-catalog.md`
- `../_system/skill-directory.md`

Then consult:

- `references/stage-router.md`

## Responsibilities

- detect the current lifecycle stage
- identify the main question and deferred goals
- select a preset or custom workflow
- route to the correct Supervisor
- keep stage outputs and evidence classes explicit

## Lifecycle routing

| Stage | Route |
|---|---|
| intake, scope, survey, artifact-intake | `syssec-foundation` |
| target-understanding, method-design, prototype | `syssec-investigation` |
| reproduction, evaluation | `syssec-validation` |
| synthesis, writing, submission, post-submission | `syssec-publication` |

## Workflow triggers

| User intent | Workflow |
|---|---|
| "I have an idea" | `idea-to-paper` |
| "Reproduce this paper" | `paper-reproduction` |
| "Study attacks on this system" | `system-attack-study` |
| "Design a defense" | `defense-design-study` |
| "Measure or compare systems" | `measurement-study` |
| "Validate and disclose a vuln" | `vuln-to-disclosure` |

## Hub checklist

1. Establish `main_stage`.
2. Determine the study type.
3. Determine what artifacts exist.
4. Check ethics and authorization boundaries.
5. Select workflow.
6. Route to one Supervisor.
7. Keep other goals deferred, not mixed into the first answer.

## Boundaries

- The Hub must not pretend a hypothesis is a finding.
- The Hub must not directly replace a Worker when a narrower skill exists.
- The Hub may answer small planning questions, but execution should route down.
