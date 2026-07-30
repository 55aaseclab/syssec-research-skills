# Ethics And Disclosure

System security research often touches live systems, sensitive data, and
harmful techniques. This protocol is mandatory.

## Allowed default posture

Default to one of these unless explicit authorization is established:

- paper analysis
- artifact review
- local reproduction
- synthetic test environment work
- design-level attack or defense reasoning

## Actions that need explicit authorization

- touching a third-party live target
- scanning outside a clearly owned lab scope
- using real credentials or customer data
- weaponizing an exploit beyond what is needed for validation
- publishing actionable zero-day details before disclosure is handled

## Responsible disclosure

If a possible vulnerability is found:

1. confirm whether it is still only a hypothesis
2. reduce impact during validation
3. record affected versions and prerequisites
4. avoid unnecessary propagation details
5. prepare a disclosure timeline and contact list

## Data handling

- Minimize collection of personal or production data.
- Prefer synthetic inputs when they answer the question.
- Keep secrets, tokens, dumps, and crash data out of user-visible summaries.

## Publication guardrails

Before publication-level output, ask:

- does this reveal unpatched exploitation guidance
- does this expose sensitive infrastructure detail
- does this require coordinated disclosure first
- does this exceed the validated evidence

If yes, downgrade the detail or switch to disclosure mode.
