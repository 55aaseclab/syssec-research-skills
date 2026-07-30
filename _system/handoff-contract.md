# Handoff Contract

All internal handoffs should use the same structure. This keeps routing,
blocking, and stage completion explicit.

```yaml
completion:
  from: syssec-<skill>
  status: DONE | DONE_WITH_CONCERNS | NEEDS_CONTEXT | BLOCKED | OUT_OF_SCOPE
  stage: intake | scope | survey | artifact-intake | reproduction |
    target-understanding | method-design | prototype | evaluation |
    synthesis | writing | submission | post-submission
  main_question_answered: true | false
  evidence_level_used: E1 | E2 | E3 | E4 | E5
  artifacts_written:
    - path: "<artifact path>"
      type: "<brief | notes | matrix | log | draft | figure | checklist>"
  concerns:
    - "<remaining concern>"
  blocked_reason: ""
  unblock_condition: ""
  needs:
    - what: "<missing input>"
      where: "<where it should come from>"
  out_of_scope:
    reason: ""
    suggested_route: "syssec-<skill>"
  suggested_next:
    - skill: "syssec-<skill>"
      reason: "<why this next step follows>"
  handoff_summary:
    completed: "<what was done>"
    key_findings: "<what the next stage must know>"
    evidence_notes: "<what evidence level supports the result>"
```

## Status guidance

- `DONE`: the stage goal was completed.
- `DONE_WITH_CONCERNS`: useful output exists but some caveats matter.
- `NEEDS_CONTEXT`: more context would materially improve accuracy.
- `BLOCKED`: the stage cannot advance without a missing precondition.
- `OUT_OF_SCOPE`: route up or sideways.

## Rules

- Prefer `DONE_WITH_CONCERNS` over `BLOCKED` when a bounded result exists.
- Use `OUT_OF_SCOPE` for layer violations.
- Do not hide evidence weakness inside `key_findings`.
