---
name: syssec-disclosure
description: >
  Disclosure Worker for system security research. Manage responsible disclosure
  material, affected-version notes, communication sequencing, and publication
  boundary decisions. Use when a possible vulnerability has disclosure
  implications.
---

# syssec-disclosure

Use `syssec-disclosure` when a finding may need coordinated communication
before or alongside publication.

## Inputs

- validated or suspected vulnerability notes
- exploitability or impact evidence
- vendor or maintainer context

## Outputs

- `disclosure-log.md`
- disclosure timeline
- affected-version summary
- publication boundary guidance

## Workflow

1. Define the current confidence and impact level.
2. Record affected versions and prerequisites.
3. Define what can be shared now and what must wait.
4. Draft the disclosure sequence and key facts.
5. Route publication text through the updated disclosure boundary.

## Boundaries

- Do not disclose beyond validated knowledge.
- Do not publish operational exploit detail prematurely.
