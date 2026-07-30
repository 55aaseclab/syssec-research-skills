# Degradation Rules

When a perfect research path is blocked, degrade honestly instead of faking
completion.

## Common blockers

- no source code
- no binary
- no dataset
- no artifact package
- insufficient privileges
- unsafe target
- missing hardware
- missing dependency or infrastructure
- paper omits critical setup details

## Degradation ladder

### From attack or defense execution

Downgrade in this order:

1. full implementation and evaluation
2. partial implementation with bounded claims
3. design and feasibility analysis
4. threat-model and assumption audit
5. literature-only comparative analysis

### From reproduction

Downgrade in this order:

1. exact reproduction
2. partial reproduction
3. environment reconstruction analysis
4. claim-by-claim reproducibility audit
5. paper-method critique

### From evaluation

Downgrade in this order:

1. full benchmark matrix
2. representative subset
3. microbenchmark or toy setup
4. analytical cost model
5. unsupported performance claim removed

## Output rules under degradation

State clearly:

- what was intended
- what blocked it
- what downgraded path was used
- which claims remain unsupported
- what would unblock the stronger path

## Never do these

- invent missing baseline numbers
- claim exploitability from static suspicion alone
- imply reproducibility when setup is unverified
- hide that a result came from a toy environment
