# Reproducibility Rules

Every serious system security result needs a replay trail.

## Minimum record per experiment or reproduction step

Record:

- target artifact and version
- host OS and kernel
- compiler, runtime, and major dependencies
- hardware or VM profile when relevant
- command lines or scripts used
- inputs, seeds, and configs
- output location
- date and operator

## Required artifacts

At minimum keep:

- environment notes
- setup commands
- run commands
- raw outputs
- summarized results
- failure notes for unsuccessful attempts

## Reproduction discipline

- Prefer scripts over manual shell history.
- Prefer pinned versions over floating tags.
- Prefer a small replayable subset over a giant undocumented setup.
- Record failures, not just successes.

## When exact reproduction is impossible

Say which of these blocked exact replay:

- missing artifact
- proprietary dependency
- hardware requirement
- unavailable dataset
- outdated infrastructure
- legal or ethical restriction

Then downgrade the stage output to partial reproduction, paper analysis, or
design review. Do not pretend exact reproduction happened.

## Measurement hygiene

- Distinguish warm-up from measured runs.
- Record trial counts.
- Record variance, not just averages.
- Note environmental noise sources.
- Separate correctness from performance runs when possible.

## Portability checks

When a claim depends on environment, record:

- tested OSes
- tested kernels
- tested architectures
- tested compiler versions
- tested deployment modes

Unsupported environments must be listed as unknown, not assumed safe.
