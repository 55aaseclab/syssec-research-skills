---
name: syssec-reproduction
description: >
  Reproduction Worker for system security research. Rebuild or audit prior
  work, record exact and partial replay status, and explain where deviations
  come from. Use when a paper or artifact must be reproduced before claims can
  be reused.
---

# syssec-reproduction

Use `syssec-reproduction` for exact or partial replay of prior work.

## Inputs

- paper and artifact inventory
- baseline target
- environment constraints

## Outputs

- `reproduction-log.md`
- exact or partial reproduction status
- deviation notes
- unverified claim list

## Workflow

1. Define what counts as successful reproduction.
2. Reconstruct the environment as closely as possible.
3. Replay the critical steps and record commands.
4. Compare observed outputs to the original claim.
5. Downgrade honestly if exact replay is impossible.

## Boundaries

- A build success is not a reproduced result.
- Route to experiment design once the replay boundary is clear.
