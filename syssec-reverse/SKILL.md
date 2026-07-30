---
name: syssec-reverse
description: >
  Reverse Engineering Worker for system security research. Analyze binaries,
  firmware, or closed components to recover structure, behavior, and candidate
  security-relevant logic. Use when source code is missing or insufficient.
---

# syssec-reverse

Use `syssec-reverse` when binary-level analysis is required.

## Inputs

- binary, firmware, or image
- scope and threat model
- target-understanding notes

## Outputs

- reverse notes
- recovered control or data-flow observations
- candidate hot spots
- evidence-labeled hypotheses

## Workflow

1. Identify format, architecture, and protections.
2. Recover key modules, entry points, and trust transitions.
3. Trace security-relevant paths.
4. Separate confirmed behavior from inferred behavior.
5. Route to dynamic analysis, exploit, or defense work as needed.

## Boundaries

- Do not present guessed semantics as confirmed code behavior.
- Route to dynamic analysis for runtime-only questions.
