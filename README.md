# SysSec Research Skills

[English](README.md) | [简体中文](README.zh-CN.md)

This is a full-lifecycle Skill system for systems security research. It is not
just a loose pile of papers, commands, and templates. It turns systems
security research into an operational system that can be routed, handed off,
reproduced, and audited.

It covers the full chain from topic selection, literature, artifact intake,
reproduction, system analysis, attack or defense prototyping, experimental
evaluation, and paper writing, through submission, rebuttal, artifact
evaluation, disclosure, and follow-up maintenance.

**Latest version: v0.1.3**

**Positioning**: a full-lifecycle orchestration system for systems security
research

**Core principles**:

- Do not assume a specific project, lab, venue, or toolchain
- Do not write guesses as conclusions
- Do not treat one successful run as reproducibility
- Do not treat paper claims as locally verified results

---

## Changelog

### v0.1.3 (2026-07-31)

- **Added workspace homepage workflow schema**: provides
  `workspace-prebuilt-workflows.json` so the research workspace homepage can
  auto-load this set of prebuilt workflows
- **Added literature-review to homepage prebuilt workflows**: it no longer
  exists only in docs and the workflow catalog

### v0.1.2 (2026-07-31)

- **Added the literature-review workflow**: splits literature reviews and
  related-work mapping out from `paper-reproduction` into a dedicated primary
  path
- **Updated Hub routing triggers**: literature review requests can now hit a
  prebuilt workflow directly
- **Added an example entry**: new `examples/literature-review.md`

### v0.1.1 (2026-07-30)

- **Added formal versioning**: introduced `VERSION`, `CHANGELOG.md`, and a git
  tag based release cadence
- **Filled missing stages**: added `syssec-method-design` and
  `syssec-post-submission`
- **Filled missing templates**: completed templates for research artifacts,
  evaluation notes, writing notes, disclosure notes, and post-submission notes
- **Filled the reference layer and examples**: added `references/` for the
  Hub, Supervisors, and key stages, plus root `examples/`
- **Removed dangling references**: closed README, workflow, and Supervisor
  references to files or stages that did not actually exist in the repo

### v0.1.0 (2026-07-30)

- **Initialized the system architecture**: established a three-layer structure
  with `1 Hub + 4 Supervisor + 27 Worker`
- **Built the protocol layer**: added preamble, evidence rules,
  reproducibility rules, ethics and disclosure, degradation rules, output
  format, handoff contract, workflow catalog, and skill directory
- **Covered the full lifecycle**: from intake all the way to the
  post-submission stage
- **Added core templates**: research brief, threat model, artifact inventory,
  reproduction log, experiment matrix, claim-evidence map, and more
- **Shipped 7 prebuilt research workflows**: covering idea-to-paper,
  paper-reproduction, literature-review, system-attack-study,
  defense-design-study, measurement-study, and vuln-to-disclosure

---

## Versioning

This system has been formally versioned since `v0.1.1`:

- The current version is defined by `VERSION`
- Human-readable changes are tracked in `CHANGELOG.md`
- Release points are fixed through git tags

---

## System Architecture

SysSec Research Skills is not a bag of disconnected research prompts. It is a
three-layer orchestration system for systems security research:

```text
L0  Hub          syssec-research ───── system entry · top-level routing ·
                                      workflow orchestration
                  │
L1  Supervisors   ├── syssec-foundation ───── research foundation hub
                  │     └─ intake / scope / survey / baseline / artifact-intake
                  │
                  ├── syssec-investigation ── technical investigation hub
                  │     └─ target-understanding / method-design / reverse /
                  │        static / dynamic / fuzzing / exploit /
                  │        defense-prototype
                  │
                  ├── syssec-validation ───── validation and evaluation hub
                  │     └─ reproduction / experiment-design / evaluation /
                  │        performance / compatibility / statistics /
                  │        threats-validity
                  │
L2  Workers       └── syssec-publication ──── writing and disclosure hub
                        └─ synthesis / write / related-work / figures /
                           submission / rebuttal / disclosure /
                           artifact-eval / post-submission
```

### What do the three layers mean?

| Layer | Role | Purpose |
|:---|:---|:---|
| **L0 Hub** | `syssec-research` | System entry point. Identifies the current research stage, selects a workflow, and routes to the right Supervisor. |
| **L1 Supervisor** | 4 hubs | Secondary routing. Takes stage tasks from the Hub, dispatches them to the right Worker, coordinates execution, and collects results. |
| **L2 Worker** | 29 execution engines | The actual executors. Each Worker solves one clear research problem only. It does not mix stages or overstate conclusions. |

**Key rule**: the Hub does not replace Workers, and Workers do not jump across
groups arbitrarily. Stage transitions must happen through explicit handoff.

---

## Toolbox

### 🔀 Hub (system entry)

| Module | Purpose |
|:---|:---|
| `syssec-research` | Main entry point responsible for stage identification, workflow selection, Supervisor routing, and long-running research state maintenance |

### 🏗️ syssec-foundation - research foundation hub

| Worker | Purpose |
|:---|:---|
| `syssec-intake` | Research intake. Turns a vague request into a research brief, study type, and deliverable. |
| `syssec-scope` | Problem definition and threat model. Clarifies the research question, assumptions, boundaries, and success criteria. |
| `syssec-survey` | Related work review. Groups prior work, extracts comparison dimensions, and identifies gaps. |
| `syssec-baseline` | Baseline discipline. Defines which systems, methods, and settings must be compared, and why the comparison is fair. |
| `syssec-artifact-intake` | Artifact inventory. Organizes code, binaries, datasets, traces, environment dependencies, and missing pieces. |

### 🔬 syssec-investigation - technical investigation hub

| Worker | Purpose |
|:---|:---|
| `syssec-target-understanding` | Understands the target system. Maps architecture, trust boundaries, attack surface, and observation points. |
| `syssec-method-design` | Method design. Converges the threat model, target understanding, and expected claims into an implementable and evaluable method. |
| `syssec-reverse` | Reverse engineering. Recovers structure and critical behavior from binaries, firmware, or closed components. |
| `syssec-static-analysis` | Static analysis. Inspects source code, configuration, call paths, boundary checks, and privilege transitions. |
| `syssec-dynamic-analysis` | Dynamic analysis. Uses traces, instrumentation, and debuggers to observe real runtime behavior. |
| `syssec-fuzzing` | Fuzzing. Designs harnesses, oracles, seeds, and triage paths. |
| `syssec-exploit` | PoC and exploit validation. Determines whether a suspected issue is actually reachable, triggerable, and impactful. |
| `syssec-defense-prototype` | Defense prototyping. Implements or constrains a protection mechanism that can later be validated. |

### 📏 syssec-validation - validation and evaluation hub

| Worker | Purpose |
|:---|:---|
| `syssec-reproduction` | Reproduces prior work. Records exact or partial reproduction status and reasons for deviations. |
| `syssec-experiment-design` | Experiment design. Defines variables, metrics, baselines, trial plans, and output paths. |
| `syssec-evaluation` | Runs evaluations. Executes the experiment matrix, aggregates raw results, and records anomalies and failures. |
| `syssec-performance` | Performance evaluation. Quantifies overhead, tail behavior, resource cost, and scalability. |
| `syssec-compatibility` | Compatibility evaluation. Checks adaptation boundaries across operating systems, versions, architectures, and deployment modes. |
| `syssec-statistics` | Statistical interpretation. Handles variance, significance, and underpowered comparisons. |
| `syssec-threats-validity` | Threats to validity. Identifies internal, external, construct, and measurement risks. |

### 📝 syssec-publication - writing and disclosure hub

| Worker | Purpose |
|:---|:---|
| `syssec-synthesis` | Claim convergence. Organizes findings into a claim-evidence map with evidence levels. |
| `syssec-write` | Paper writing. Structures sections around validated claims, not wishful storytelling. |
| `syssec-related-work` | Related work writing. Turns the survey into technical positioning instead of a citation dump. |
| `syssec-figures` | Figure planning. Ensures every figure or table serves a specific claim. |
| `syssec-submission` | Submission checks. Verifies the completeness of the paper, appendix, artifact, ethics, and formatting. |
| `syssec-rebuttal` | Rebuttal orchestration. Maps reviewer comments to evidence, added experiments, and revision plans. |
| `syssec-disclosure` | Responsible disclosure. Controls publication boundaries, affected versions, and communication timing. |
| `syssec-artifact-eval` | Artifact evaluation. Prepares a package and replay checklist that outside reviewers can rerun. |
| `syssec-post-submission` | Post-submission maintenance. Handles camera-ready, artifact follow-up, release hygiene, and ongoing maintenance commitments. |

---

## Routing Map

### Routing logic

#### Primary routing (Hub -> Supervisor)

| User intent | Route to |
|:---|:---|
| The problem is still vague, or you need a threat model, literature review, baseline list, or artifact inventory | `syssec-foundation` |
| You need system architecture understanding, reverse engineering, static analysis, dynamic analysis, fuzzing, PoC validation, or a defense prototype | `syssec-investigation` |
| You need reproduction, experiment design, evaluation, performance analysis, compatibility checks, statistics, or threats to validity | `syssec-validation` |
| You need claim convergence, paper writing, figures, submission prep, rebuttal, disclosure, or artifact evaluation | `syssec-publication` |

#### Secondary routing (Supervisor -> Worker)

**syssec-foundation ->**

| Intent signal | Worker |
|:---|:---|
| The request is scattered and the goal or deliverable is unclear | `syssec-intake` |
| Research question, threat model, assumptions, or boundaries | `syssec-scope` |
| Related work, gaps, or neighboring papers | `syssec-survey` |
| Baseline selection or fair comparison | `syssec-baseline` |
| Code / binary / dataset / trace / artifact inventory | `syssec-artifact-intake` |

**syssec-investigation ->**

| Intent signal | Worker |
|:---|:---|
| First understand the system architecture and attack surface | `syssec-target-understanding` |
| First clarify the method and proof obligations | `syssec-method-design` |
| No source code, need to study binaries or firmware | `syssec-reverse` |
| Source code is available, start from static logic | `syssec-static-analysis` |
| Need runtime evidence | `syssec-dynamic-analysis` |
| Need automated input exploration | `syssec-fuzzing` |
| Need to validate exploitability | `syssec-exploit` |
| Need to implement a mitigation or defense | `syssec-defense-prototype` |

**syssec-validation ->**

| Intent signal | Worker |
|:---|:---|
| Reproduce someone else's paper or artifact | `syssec-reproduction` |
| First design the experiment matrix | `syssec-experiment-design` |
| Start running experiments and reading results | `syssec-evaluation` |
| Focus on overhead and scalability | `syssec-performance` |
| Focus on OS / architecture / deployment support | `syssec-compatibility` |
| Focus on variance and significance | `syssec-statistics` |
| Focus on overclaim and validity | `syssec-threats-validity` |

**syssec-publication ->**

| Intent signal | Worker |
|:---|:---|
| First narrow the claims | `syssec-synthesis` |
| Start writing the paper | `syssec-write` |
| Organize the related work section | `syssec-related-work` |
| Plan figures and tables | `syssec-figures` |
| Prepare the submission package | `syssec-submission` |
| Respond to reviewers | `syssec-rebuttal` |
| Manage disclosure boundaries | `syssec-disclosure` |
| Prepare artifact evaluation | `syssec-artifact-eval` |
| Handle camera-ready and follow-up maintenance | `syssec-post-submission` |

### Prebuilt workflows

SysSec Research Skills ships with 7 prebuilt workflows that cover the most
common primary paths in systems security research:

| # | Workflow | Typical use case | Execution path |
|:--|:---|:---|:---|
| 1 | **idea-to-paper** | Take a research idea all the way to submission | intake -> scope -> survey -> baseline -> artifact-intake -> method-design -> prototype -> evaluation -> synthesis -> writing -> submission |
| 2 | **paper-reproduction** | You already have a paper and want reproduction plus deviation auditing | intake -> survey -> artifact-intake -> reproduction -> experiment-design -> evaluation -> threats-validity -> writing |
| 3 | **literature-review** | Build a systems security literature review, related-work map, or survey-style write-up for a topic | intake -> scope -> survey -> baseline -> synthesis -> related-work -> write -> submission |
| 4 | **system-attack-study** | Analyze a system's attack surface, build a PoC, evaluate it, and write it up | intake -> scope -> target-understanding -> reverse/static -> dynamic/fuzzing -> exploit -> evaluation -> synthesis -> writing -> disclosure |
| 5 | **defense-design-study** | Design and implement a defense, then evaluate both its security and cost | intake -> scope -> survey -> baseline -> target-understanding -> method-design -> defense-prototype -> evaluation -> performance -> compatibility -> threats-validity -> writing |
| 6 | **measurement-study** | Run a systems security measurement, taxonomy, trend, or comparative study | intake -> scope -> survey -> baseline -> artifact-intake -> experiment-design -> evaluation -> statistics -> synthesis -> writing |
| 7 | **vuln-to-disclosure** | Move from issue discovery through validation, disclosure, and publication-boundary control | intake -> scope -> target-understanding -> static/dynamic -> reproduction -> exploit/defense -> evaluation -> disclosure -> writing |

### Common paths

```text
You only have a vague idea
-> syssec-research
-> syssec-foundation
-> intake -> scope -> survey

You have a paper and want to reproduce it
-> syssec-research
-> syssec-validation
-> reproduction -> experiment-design -> evaluation

You suspect a system has a vulnerability and want to verify it
-> syssec-research
-> syssec-investigation
-> target-understanding -> static/dynamic -> exploit
-> syssec-validation -> evaluation
-> syssec-publication -> disclosure

You already have results and want to write the paper
-> syssec-research
-> syssec-publication
-> synthesis -> figures -> write -> submission
```

### Cross-group collaboration

By default, modules collaborate by research stage rather than writing in
parallel without coordination:

- `foundation` prepares the threat model, baselines, and artifact inventory
  before handing work to `investigation`
- `investigation` is responsible for technical facts and prototypes only, and
  does not declare something "proven" on behalf of `validation`
- `validation` organizes results, costs, deployment boundaries, and validity
  risks before handing them to `publication`
- `publication` can only consume established evidence and cannot reverse-engineer
  conclusions for the sake of a nicer paper

---

## Research State Artifacts

This system maintains a default set of long-running research artifacts that act
as a data bus across stages:

| Artifact | Purpose |
|:---|:---|
| `research-brief.md` | Records research goals, study type, deliverables, and constraints |
| `questions-and-hypotheses.md` | Records research questions, hypotheses, and success criteria |
| `threat-model.md` | Records the adversary, assets, boundaries, assumptions, and non-goals |
| `related-work-map.md` | Records related-work groups, comparison dimensions, and gaps |
| `baseline-matrix.md` | Records required baselines and the fairness rationale for each comparison |
| `artifact-inventory.md` | Records code, binaries, datasets, traces, dependencies, and missing pieces |
| `reproduction-log.md` | Records reproduction steps, environments, deviations, and unverified claims |
| `system-notes.md` | Records architecture, components, trust boundaries, and attack surface |
| `attack-surface-map.md` | Records entry points, boundaries, critical interfaces, and observable points |
| `method-design.md` | Records the method, proof obligations, and experiment bindings |
| `prototype-notes.md` | Records implementation boundaries and failed attempts for PoCs or defense prototypes |
| `experiment-matrix.md` | Records variables, metrics, baselines, and trial design |
| `findings-log.md` | Records observations, evidence levels, and next actions |
| `results-summary.md` | Summarizes experimental results and anomalies |
| `performance-notes.md` | Records overhead, tail behavior, scalability, and resource cost |
| `compatibility-notes.md` | Records platform support, deployment boundaries, and incompatibilities |
| `validity-notes.md` | Records internal, external, construct, and measurement risks |
| `claim-evidence-map.md` | Binds each claim to its evidence source |
| `paper-outline.md` | Organizes the paper structure and section skeleton |
| `figures-plan.md` | Records figures, tables, captions, and the claims they support |
| `submission-checklist.md` | Checks the paper, artifact, ethics, and formatting |
| `rebuttal-notes.md` | Records reviewer questions, response strategy, and added experiment plans |
| `disclosure-log.md` | Records disclosure boundaries, versions, and communication timing |
| `post-submission-notes.md` | Records camera-ready work, artifact follow-up, and maintenance actions |

The corresponding templates are in `templates/`.

---

## Protocol Layer

Before doing any real work, every skill loads the protocol layer under
`_system/`:

| File | Purpose |
|:---|:---|
| `preamble.md` | Determines the current research stage before deciding actions |
| `evidence-rules.md` | Distinguishes verified, derived, inference, hypothesis, and external claim |
| `reproducibility-rules.md` | Forces the recording of environments, commands, inputs, outputs, and versions |
| `ethics-and-disclosure.md` | Controls live targets, sensitive data, and disclosure boundaries |
| `degradation-rules.md` | Explains how to degrade gracefully when source, artifact, privileges, or hardware are unavailable |
| `output-format.md` | Forces confirmed facts and still-unverified items to be written separately |
| `handoff-contract.md` | Standardizes `DONE`, `NEEDS_CONTEXT`, `BLOCKED`, and `OUT_OF_SCOPE` handoff results |
| `workflow-catalog.md` | Catalog of prebuilt workflows |
| `skill-directory.md` | Responsibility map for all skills |

---

## Reference Layer and Examples

Beyond the protocol layer, this system includes two supporting layers:

- `references/` contains work references and checklists for the Hub,
  Supervisors, and key stages
- `examples/` contains minimal examples for common research paths so users can
  enter the right workflow faster

---

## What This System Does Not Preset

- It does not assume you have source code
- It does not assume you have an artifact package
- It does not assume paper claims will reproduce
- It does not assume you can touch a live target
- It does not assume systems security research must be exploit-only; defense,
  measurement, reproduction, and writing are all covered
- It does not assume a fixed venue, toolchain, or lab workflow

The only thing it assumes is that systems security research must make its
evidence, boundaries, reproducibility, and disclosure discipline explicit.
