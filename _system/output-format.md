# Output Format

Every user-visible response should be stage-bounded and evidence-aware.

## Default structure

```markdown
# Stage
One sentence stating the current research stage and goal.

## Established
- Facts established in this step
- Evidence class for each important fact when needed

## Work Done
- What was analyzed, produced, or decided

## Uncertainties
- Remaining assumptions, blockers, or pending validations

## Next Step
- The next stage or worker to run
- The concrete artifact or decision it should produce
```

## Style rules

- Separate facts from hypotheses.
- Prefer short, technical sentences.
- Use stable stage names.
- Do not hide blockers.
- Do not overstate novelty, exploitability, or generality.

## Required labels when relevant

Explicitly mark:

- `Verified`
- `Derived`
- `Inference`
- `Hypothesis`
- `External claim`

These labels map to `_system/evidence-rules.md`.
