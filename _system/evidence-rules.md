# Evidence Rules

System security research fails when guesses are presented as findings. Use
these evidence classes in every stage.

## Evidence classes

### E1: Direct verified evidence

Use when the claim is supported by directly inspected artifacts, code, logs,
measurements, traces, or reproduced results.

Examples:

- source code path and behavior confirmed
- benchmark output reproduced
- packet trace or syscall trace captured
- crash reproduced with the recorded input

### E2: Derived evidence

Use when the claim is not directly observed but is derived from verified
artifacts through a documented transformation.

Examples:

- CFG derived from verified binary
- metric aggregated from raw run results
- table built from a logged experiment matrix

### E3: Supported inference

Use when the claim is a reasoned inference from available evidence but still
needs confirmation.

Examples:

- likely root cause based on observed control flow
- likely threat boundary mismatch based on policy structure

### E4: Hypothesis

Use when the idea is plausible but not yet confirmed by artifact inspection or
experiment.

Examples:

- expected exploit condition
- expected performance bottleneck
- candidate explanation for a failed reproduction

### E5: External claim only

Use when the statement comes from a paper, README, issue tracker, or other
external source and has not been locally validated.

## Rules

- Never present E3, E4, or E5 as if they were E1.
- When a stage output mixes evidence classes, label the weakest link.
- A paper claim is not local validation.
- A benchmark number from a paper is not a reproduced result.
- A reverse-engineered guess is not a confirmed bug root cause.

## Claim discipline

Every important claim should answer three questions:

1. What is the claim?
2. What evidence class supports it?
3. What would upgrade it to the next class?

## Red flags

Stop and relabel the output if you see any of these:

- "obviously" without direct verification
- exploitability asserted from code smell alone
- performance conclusions from one run
- generalization beyond tested platforms
- a defense claimed sound without boundary analysis
