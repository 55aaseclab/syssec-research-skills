# Preamble

Every `syssec-*` skill must execute this startup protocol before doing
user-visible work.

## 1. Establish the stage

Identify the current lifecycle stage first. Never assume the user is at the
beginning.

Possible stages:

- `intake`
- `scope`
- `survey`
- `artifact-intake`
- `reproduction`
- `target-understanding`
- `method-design`
- `prototype`
- `evaluation`
- `synthesis`
- `writing`
- `submission`
- `post-submission`

If multiple stages are active, select one `main_stage` and record the rest as
deferred goals.

## 2. Establish the research objective

Extract and restate:

- the target system or class of systems
- the research question
- the study type
- the desired output
- the time and access constraints

Study types:

- novel attack
- novel defense
- reproduction
- measurement
- survey
- artifact evaluation
- vulnerability validation
- paper writing only

## 3. Check the evidence situation

Determine what is actually available:

- paper only
- paper plus artifact
- source code
- binary only
- dataset
- logs or traces
- prior notes
- no concrete artifact yet

Classify evidence confidence using `_system/evidence-rules.md`.

## 4. Check the ethics and authorization boundary

Before any offensive or risky action, verify:

- scope and ownership
- authorization level
- disclosure sensitivity
- data handling constraints
- whether an action is safe to perform or must stay at design level

If authorization is unclear, switch to analysis, design, or review mode.

## 5. Choose a workflow

Map the request to a workflow in `_system/workflow-catalog.md`.

If no preset workflow fully fits, compose a custom path from the current stage
forward. Do not force the user into a preset if it weakens the work.

## 6. Select the next skill

Route to the narrowest skill that can move the current stage forward.

- Hub routes to Supervisor.
- Supervisor routes to Worker.
- Workers do not silently jump across layers.

## 7. Produce stage-bounded output

Each response must say:

- what stage is being handled now
- what was established as evidence
- what was completed
- what remains uncertain
- what the next stage should be

Format rules live in `_system/output-format.md`.
