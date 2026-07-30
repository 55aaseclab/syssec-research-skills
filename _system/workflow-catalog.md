# Workflow Catalog

These workflows are presets, not cages. Use them when they fit. Compose a
custom stage path when they do not.

## `idea-to-paper`

Use when the user starts with an idea, target area, or open problem.

```text
intake → scope → survey → baseline → artifact-intake →
method-design → prototype → evaluation → synthesis → writing →
submission → post-submission
```

## `paper-reproduction`

Use when the user already has a paper and wants to reproduce or audit it.

```text
intake → survey → artifact-intake → reproduction →
experiment-design → evaluation → threats-validity → writing
```

## `system-attack-study`

Use when the goal is to analyze a system, identify an attack path, build a
PoC, and evaluate it.

```text
intake → scope → target-understanding → reverse or static-analysis →
dynamic-analysis or fuzzing → exploit → evaluation → synthesis →
writing → disclosure
```

## `defense-design-study`

Use when the goal is to design and validate a defense.

```text
intake → scope → survey → baseline → target-understanding →
method-design → defense-prototype → evaluation → performance →
compatibility → threats-validity → writing → submission
```

## `measurement-study`

Use when the goal is large-scale characterization, comparison, or trend
analysis.

```text
intake → scope → survey → baseline → artifact-intake →
experiment-design → evaluation → statistics → synthesis →
writing → submission
```

## `vuln-to-disclosure`

Use when a possible vulnerability was found and needs disciplined validation
and disclosure.

```text
intake → scope → target-understanding → static-analysis or dynamic-analysis →
reproduction → exploit or defense-prototype → evaluation →
disclosure → writing → post-submission
```

## Workflow selection rules

- If the user already has experimental data, skip to `evaluation` or
  `synthesis`.
- If the user only wants writing help, enter `writing` but demand the current
  evidence state first.
- If authorization is unclear, avoid live-target stages and prefer analysis.
