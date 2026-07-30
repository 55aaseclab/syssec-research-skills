# syssec-research-skills

`syssec-research-skills` is a full-lifecycle skill system for system security
research. It is not tied to one paper, one lab workflow, or one repository.
Its job is to help an agent move a research effort from idea intake to
publication, artifact evaluation, disclosure, and post-submission follow-up.

## Design goals

- Cover the whole research lifecycle.
- Keep evidence, ethics, and reproducibility explicit.
- Separate routing from execution.
- Force stage outputs instead of hand-wavy advice.
- Degrade honestly when code, data, privileges, or time are missing.

## Architecture

```text
Hub
└── syssec-research
    ├── syssec-foundation
    │   ├── syssec-intake
    │   ├── syssec-scope
    │   ├── syssec-survey
    │   ├── syssec-baseline
    │   └── syssec-artifact-intake
    ├── syssec-investigation
    │   ├── syssec-target-understanding
    │   ├── syssec-reverse
    │   ├── syssec-static-analysis
    │   ├── syssec-dynamic-analysis
    │   ├── syssec-fuzzing
    │   ├── syssec-exploit
    │   └── syssec-defense-prototype
    ├── syssec-validation
    │   ├── syssec-reproduction
    │   ├── syssec-experiment-design
    │   ├── syssec-evaluation
    │   ├── syssec-performance
    │   ├── syssec-compatibility
    │   ├── syssec-statistics
    │   └── syssec-threats-validity
    └── syssec-publication
        ├── syssec-synthesis
        ├── syssec-write
        ├── syssec-related-work
        ├── syssec-figures
        ├── syssec-submission
        ├── syssec-rebuttal
        ├── syssec-disclosure
        └── syssec-artifact-eval
```

## Lifecycle coverage

1. Intake and research framing
2. Scope, threat model, and hypotheses
3. Literature survey and baseline mapping
4. Artifact intake and environment constraints
5. Reproduction of prior work
6. Target understanding and attack surface analysis
7. Method design and prototype building
8. Security, performance, and compatibility evaluation
9. Claim synthesis and paper writing
10. Submission, rebuttal, artifact evaluation, and disclosure

## Core workflows

- `idea-to-paper`
- `paper-reproduction`
- `system-attack-study`
- `defense-design-study`
- `measurement-study`
- `vuln-to-disclosure`

Workflow entry rules live in `_system/workflow-catalog.md`.

## Protocol layer

All skills load `_system/` before doing user-visible work:

- `preamble.md`
- `evidence-rules.md`
- `reproducibility-rules.md`
- `ethics-and-disclosure.md`
- `degradation-rules.md`
- `output-format.md`
- `handoff-contract.md`
- `workflow-catalog.md`
- `skill-directory.md`

## Standard research artifacts

The Hub should maintain or request these artifacts over time:

- `research-brief.md`
- `questions-and-hypotheses.md`
- `threat-model.md`
- `related-work-map.md`
- `baseline-matrix.md`
- `artifact-inventory.md`
- `reproduction-log.md`
- `system-notes.md`
- `experiment-matrix.md`
- `findings-log.md`
- `results-summary.md`
- `claim-evidence-map.md`
- `paper-outline.md`
- `submission-checklist.md`
- `disclosure-log.md`

Templates for the core artifacts live under `templates/`.

## What this repository does not assume

- No fixed conference target
- No fixed data-collection tool
- No fixed analysis tool
- No fixed benchmarking harness
- No guarantee of source code, datasets, or paper artifacts

The skills must adapt to incomplete inputs and say exactly what is missing.
