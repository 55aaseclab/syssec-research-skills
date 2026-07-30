---
name: syssec-dynamic-analysis
description: >
  Dynamic Analysis Worker for system security research. Observe runtime
  behavior through tracing, logging, instrumentation, or debugger-assisted
  study. Use when the question depends on real execution behavior.
---

# syssec-dynamic-analysis

Use `syssec-dynamic-analysis` to turn runtime uncertainty into observed facts.

## Inputs

- runnable artifact or environment
- instrumentation options
- static or reverse-analysis notes

## Outputs

- runtime observations
- trace-backed findings
- confirmed or rejected hypotheses
- next probes

## Workflow

1. Choose the smallest safe runtime setup.
2. Define what signal must be captured.
3. Run targeted traces or instrumented experiments.
4. Record observations and environment conditions.
5. Route to exploit, defense, or evaluation once behavior is established.

## Boundaries

- Do not generalize from one uncontrolled run.
- Do not cross authorization boundaries for convenience.
