---
name: syssec-intake
description: >
  Intake Worker for system security research. Turn a loose request into a
  research brief with a study type, target, deliverable, constraints, and next
  stage. Use when the user starts with a broad idea or mixed goals.
---

# syssec-intake

Use `syssec-intake` to convert a vague request into a bounded research brief.

## Inputs

- the user request
- known target systems or papers
- deadline or venue constraints
- access and authorization limits

## Outputs

- `research-brief.md`
- `main_stage`
- `study_type`
- deferred goals list

## Workflow

1. Extract the main question.
2. Classify the study type.
3. Record the expected deliverable.
4. Record time, access, and safety constraints.
5. Recommend the next stage.

## Boundaries

- Do not define technical claims here.
- Do not skip to implementation if scope is still unclear.
