# Polaris Systems Security Research Domain Pack

`main.ord` is the Polaris Business DSL representation of the seven
user-facing workflows in the SysSec Research Skills catalog.

The pack preserves the source system's evidence, authorization,
reproducibility, and publication boundaries. Ports are capability contracts;
they do not embed commands, target paths, credentials, exploit payloads, or
an execution adapter.

Install from the Wanghai repository root:

```bash
pnpm --dir ../polaris run polaris -- pack add \
  "$PWD/third_party/syssec-research-skills/polaris-domain-pack"
```

The pack contains idea-to-paper, paper reproduction, literature review, system
attack study, defense design, measurement study, and vulnerability disclosure.
