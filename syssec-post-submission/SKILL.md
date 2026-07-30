---
name: syssec-post-submission
description: >
  Post-Submission Worker for system security research. Handle camera-ready
  fixes, artifact follow-up, release hygiene, disclosure follow-through, and
  long-tail maintenance after submission or acceptance. Use when the work has
  moved beyond the main submission checkpoint.
---

# syssec-post-submission

Use `syssec-post-submission` to keep the research package coherent after the
main submission is already out the door.

## Reference

- `references/post-submission-playbook.md`

## Inputs

- submission checklist
- rebuttal notes or acceptance feedback
- artifact-eval notes
- disclosure log

## Outputs

- `post-submission-notes.md`
- camera-ready change list
- release or maintenance action list
- unresolved follow-up risks

## Workflow

1. Record what was promised during submission, review, or disclosure.
2. Separate required camera-ready fixes from nice-to-have cleanup.
3. Track artifact follow-up, code release, and documentation debt.
4. Track disclosure coordination that still constrains public output.
5. Produce a bounded maintenance plan instead of letting the work drift.

## Boundaries

- Do not let post-submission cleanup silently change validated claims.
- Do not publish release artifacts that contradict disclosure boundaries.
