---
name: syssec-survey
description: >
  Survey Worker for system security research. Build a map of related work,
  extract comparison dimensions, and identify unresolved gaps. Use when the
  project needs a credible prior-work foundation.
---

# syssec-survey

Use `syssec-survey` to understand what is already known and where the real
research gap is.

## Inputs

- research question
- threat model
- venue or maturity expectations
- seed papers, if any

## Outputs

- `related-work-map.md`
- grouped paper list
- gap statements
- open issues worth checking

## Workflow

1. Collect and group prior work by approach.
2. Extract assumptions, artifacts, and evaluation style.
3. Compare threat models and deployment assumptions.
4. Identify where claims, systems, or conditions differ.
5. Produce the smallest honest gap statement.

## Boundaries

- Do not invent novelty before checking close neighbors.
- Route to `syssec-baseline` when comparison systems are now clear.
