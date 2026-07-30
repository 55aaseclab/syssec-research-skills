---
name: syssec-compatibility
description: >
  Compatibility Worker for system security research. Check how a method or
  prototype behaves across operating systems, versions, architectures, or
  deployment modes. Use when generality or deployability is part of the claim.
---

# syssec-compatibility

Use `syssec-compatibility` to keep portability claims precise.

## Inputs

- prototype or reproduced system
- supported environments list
- evaluation plan

## Outputs

- compatibility notes
- supported and unsupported cases
- deployment caveats

## Workflow

1. Define which environments matter to the claim.
2. Test or audit them explicitly.
3. Record missing support and behavioral differences.
4. Separate untested from unsupported.
5. Route results to validity analysis and writing.

## Boundaries

- Do not say "works generally" if only one stack was tested.
- Untested is not supported.
