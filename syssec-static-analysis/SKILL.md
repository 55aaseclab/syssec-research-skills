---
name: syssec-static-analysis
description: >
  Static Analysis Worker for system security research. Inspect source, build
  logic, configs, and call structure to find assumptions, trust transitions,
  and candidate weaknesses. Use when offline code reasoning can advance the
  question.
---

# syssec-static-analysis

Use `syssec-static-analysis` for source-level or static artifact inspection.

## Inputs

- source tree or extracted code
- threat model
- target-understanding notes

## Outputs

- static-analysis notes
- confirmed control or data-flow findings
- candidate weakness list
- follow-up probes

## Workflow

1. Locate code paths that matter to the research question.
2. Inspect trust boundaries, validation logic, and privilege changes.
3. Record confirmed behavior with file or function references.
4. Separate suspicious patterns from validated weaknesses.
5. Route to dynamic analysis, fuzzing, or exploit validation.

## Boundaries

- Static suspicion is not exploitability.
- If behavior depends on runtime state, route to dynamic analysis.
