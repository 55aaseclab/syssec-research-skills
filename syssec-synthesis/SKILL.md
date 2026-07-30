---
name: syssec-synthesis
description: >
  Synthesis Worker for system security research. Convert validated findings
  into a claim-evidence map with explicit boundaries, caveats, and contribution
  statements. Use when the work is moving from results to paper claims.
---

# syssec-synthesis

Use `syssec-synthesis` to decide what the work really established.

## Inputs

- results summaries
- validity notes
- baseline comparisons

## Outputs

- `claim-evidence-map.md`
- contribution list
- caveat-aware claim set

## Workflow

1. List candidate claims.
2. Attach evidence class and source to each claim.
3. Remove or weaken claims that lack support.
4. Group claims into contributions.
5. Route the map to writing and figures.

## Boundaries

- Do not write the paper around claims that are still hypotheses.
- A clean story must still match the actual evidence.
