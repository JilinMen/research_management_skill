# Research Management Skill

## Purpose

Use this skill to manage research-oriented work in a structured, traceable, and iterative way. The goal is to prevent ad hoc execution before the research objective, data, methods, expected outputs, process files, and current project status are clearly defined.

This skill should be activated whenever the user appears to be conducting, designing, revising, evaluating, coding, analyzing, or writing about research.

## Automatic activation criteria

Activate this skill when the user request involves any of the following:

- Developing a research idea, proposal, project, manuscript, abstract, presentation, report, or response to reviewers
- Designing experiments, validation workflows, model comparisons, statistical analysis, or data-processing pipelines
- Planning data collection, field campaigns, laboratory measurements, remote-sensing workflows, or model training
- Asking for research framing, objectives, hypotheses, methods, figures, expected results, discussion points, limitations, or novelty
- Writing, revising, or evaluating research code, including preprocessing scripts, model scripts, validation scripts, plotting scripts, or notebooks
- Continuing a prior research task where a research plan may already exist

Do not activate this skill for simple translation, grammar polishing, casual explanation, administrative email drafting, or general advice unless the content clearly belongs to a research project.

## Required first step before thinking or execution

Before doing substantive reasoning, analysis, writing, coding, or editing for a research task:

1. Check whether a `plan.md` file is available in the current working context.
2. If `plan.md` exists:
   - Read it first.
   - Use it as the governing research context.
   - Pay special attention to the project state summary, process-file registry, file-dependency map, research log, decision log, TODO list, and experiment registry.
   - Align the response with the plan unless the user explicitly asks to deviate.
   - If the user request conflicts with the plan, point out the conflict and suggest whether the plan should be updated.
3. If `plan.md` does not exist:
   - Do not proceed directly to the research task.
   - First generate a detailed research plan based on the user-provided topic.
   - Ask the user to confirm whether the plan is feasible before executing the full research task.
   - If information is missing, make reasonable assumptions and mark them clearly instead of blocking progress unnecessarily.

## Creating `plan.md`

When no `plan.md` exists, create a draft research plan detailed enough to guide later writing, analysis, implementation, and interpretation.

The plan should include:

1. Project State Summary
2. Research Topic
3. Background and Motivation
4. Research Objectives
5. Research Questions or Hypotheses
6. Study Area or Research Scope
7. Data
8. Methods
9. Evaluation Metrics
10. Expected Results
11. Discussion Points
12. Novelty and Contribution
13. Risks, Limitations, and Mitigation Strategies
14. Expected Deliverables
15. Timeline and Milestones
16. Open Questions for User Confirmation
17. Process File Registry
18. File Dependency and Workflow Map
19. Research Log
20. Decision Log
21. Open Issues and TODOs
22. Experiment Registry

Use `plan_template.md` as the preferred structure.

## Discussing the plan with the user

When presenting a newly generated research plan:

- State that no existing `plan.md` was found.
- Present the draft plan clearly.
- Ask the user to confirm whether the plan is feasible.
- Ask for permission to update or save the plan as `plan.md`.
- Do not begin the full research execution until the user confirms the plan or asks to proceed.

Example wording:

> I did not find an existing `plan.md`, so I drafted a research plan first. Please review whether this plan is feasible. With your permission, I will update `plan.md` and then proceed based on it.

## Updating `plan.md`

During discussion with the user:

1. Identify whether the user is suggesting changes to the plan.
2. If the user explicitly approves the change, update `plan.md`.
3. If the user gives informal feedback that clearly improves the plan, ask permission before updating.
4. If the user says to revise, update, adjust, add, remove, or replace part of the plan, update `plan.md` directly.
5. After updating, briefly summarize what changed.

Examples of changes that should be written into `plan.md` when allowed:

- New research objective
- Revised study area
- Different dataset
- Different method
- Added validation strategy
- Removed infeasible analysis
- Updated expected figures
- Revised manuscript framing
- Added limitation or risk
- Changed target journal, conference, or deliverable
- Approved model script
- Approved plotting script
- Approved dataset or intermediate output
- Confirmed experiment result
- New TODO or blocker
- Confirmed research decision

## Research process file tracking

This skill must track important process files generated or used during the research workflow. The purpose is to make future conversations recover the project status from `plan.md` without relying on chat history.

Process files include:

- Data preprocessing scripts
- Model training scripts
- Model architecture files
- Inference scripts
- Validation scripts
- Statistical analysis scripts
- Plotting or figure-generation scripts
- Table-generation scripts
- Configuration files
- Notebooks
- Intermediate datasets
- Final datasets
- Trained model weights
- Figure outputs
- Table outputs
- Manuscript drafts
- Response-to-reviewer drafts

## When to consider recording a file

Whenever the AI creates, modifies, recommends, or helps debug a file that may be useful for the research workflow, it should consider whether this file should be recorded in `plan.md`.

Examples:

- The user asks the AI to write a model, and the resulting model appears useful.
- The user asks the AI to write plotting code, and the resulting figure is useful.
- The user asks the AI to write a preprocessing script that will likely be reused.
- The user approves a validation workflow script.
- A notebook becomes the main analysis notebook.
- A figure-generation script produces a final or near-final figure.
- A configuration file defines important experimental settings.
- A trained model checkpoint becomes a candidate final model.

## User confirmation requirement for code and files

The AI must not automatically mark a file as accepted or approved only because it created the file.

Before recording a file as important in `plan.md`, the AI should ask for the user's judgment when appropriate.

Example questions:

> This model script seems useful for the project. Do you want me to mark it in `plan.md` as the current main model implementation?

> The plotting script appears to generate the desired figure. Should I record this script path in `plan.md` as the approved Figure 3 plotting code?

> This preprocessing script may become part of the formal workflow. Would you like me to add it to the process-file registry in `plan.md`?

If the user clearly approves, update `plan.md`.

If the user says the script is not good, experimental, temporary, or should not be tracked, do not mark it as accepted. It may be listed as rejected or experimental only if the user wants that history preserved.

## Recording code quality and status

When adding a file to `plan.md`, record its status based on user confirmation.

Recommended status values:

- `proposed`: generated or suggested but not yet tested
- `under_review`: user or AI is reviewing the file
- `approved`: user confirmed that the file is useful or should be kept
- `needs_revision`: user confirmed that the file is useful but requires changes
- `deprecated`: file was replaced by a newer version
- `rejected`: user decided not to use the file
- `archived`: file is retained for reference but not part of the active workflow

Do not label a file as `approved` unless the user explicitly agrees or gives a clear positive judgment.

## Process File Registry

`plan.md` should contain a section named `Process File Registry`.

Recommended subsections:

- Active Core Files
- Supporting Scripts
- Data and Intermediate Outputs
- Figures, Tables, and Manuscript Outputs
- Deprecated, Rejected, or Archived Files

Each tracked file should include:

- ID
- File path
- File type
- Role in project
- Status
- Whether user-confirmed
- Last updated date
- Notes

## File Dependency and Workflow Map

`plan.md` should contain a section named `File Dependency and Workflow Map`.

This section should record relationships between important files, such as:

- preprocessing script produces processed dataset
- processed dataset is used by model script
- model script produces metrics file
- metrics file is used by plotting script
- plotting script produces manuscript figure

Recommended relationships include:

- `produces`
- `uses`
- `depends on`
- `replaces`
- `supersedes`
- `validates`
- `visualizes`
- `summarizes`
- `exports`
- `documents`

If an approved file replaces an older one:

- Mark the older file as `deprecated`.
- Add a relationship showing that the new file `supersedes` or `replaces` the old file.
- Briefly explain why the replacement happened.

## Project State Summary

`plan.md` should include a compact project-state summary near the beginning.

It should include:

- Current stage
- Main objective
- Active dataset(s)
- Active model or method
- Active preprocessing script
- Active validation script
- Main figure/table scripts
- Main outputs in progress
- Latest confirmed decision
- Current blockers
- Immediate next step
- Last updated date

Update this section whenever there is a meaningful change in project direction, active data, active code, confirmed files, experiment status, or next steps.

## Research Log

The research log records important actions and findings that may not be captured by file paths alone.

Record entries for events such as:

- A model was tested
- A dataset was found unsuitable
- A preprocessing strategy changed
- A figure concept was accepted
- A validation result revealed an issue
- A reviewer comment was resolved
- A manuscript section was reorganized
- A workflow was blocked by missing data or software issues

Each entry should include:

- Date
- Action
- Key finding or decision
- Related files
- Next step

## Decision Log

The decision log preserves major research decisions and the reasoning behind them.

Record decisions such as:

- Choice of dataset
- Choice of model or algorithm
- Choice of validation strategy
- Choice of quality-control criteria
- Choice of target journal, conference, or deliverable
- Decision to drop or replace a method
- Decision to use a figure, table, or result as the main manuscript evidence

Each entry should include:

- Date
- Decision
- Reason
- Alternatives considered
- Status

Do not mark a decision as `confirmed` unless the user has clearly approved it or instructed the AI to proceed with it.

## Open Issues and TODOs

The TODO section should make the current next steps explicit.

Each task should include:

- ID
- Task
- Priority
- Status
- Related files
- Notes

Recommended task statuses:

- `pending`
- `in_progress`
- `blocked`
- `done`
- `deferred`
- `cancelled`

Update this section when a new task emerges, a task is completed, a task becomes blocked, a task becomes irrelevant, the user changes priorities, or a file/experiment creates a new follow-up action.

## Experiment Registry

The experiment registry tracks model runs, algorithm tests, parameter trials, validation experiments, data-combination tests, and other repeatable research experiments.

Each experiment should include:

- Experiment ID
- Purpose
- Input data
- Method/model
- Key settings
- Output files
- Metrics/results
- Status
- User judgment

Recommended experiment statuses:

- `proposed`
- `running`
- `completed`
- `failed`
- `deprecated`

Recommended user-judgment values:

- `unreviewed`
- `acceptable`
- `needs_revision`
- `rejected`
- `final`

The AI should ask the user before marking an experiment as `acceptable`, `final`, or as the active basis for manuscript results.

## Maintenance rules

Whenever a meaningful research step occurs, the AI should consider whether one or more plan sections should be updated.

Examples:

- If a new model script is approved:
  - Update Project State Summary
  - Update Process File Registry
  - Update File Dependency and Workflow Map
  - Add an entry to Research Log
  - Add or update an entry in Experiment Registry if the model was tested

- If the user confirms a methodological choice:
  - Add or update Decision Log
  - Update Project State Summary
  - Update relevant TODOs

- If a figure script works well:
  - Ask the user whether to record it
  - If approved, update Process File Registry
  - Update File Dependency and Workflow Map
  - Add a Research Log entry
  - Update TODOs or manuscript/figure-related notes if relevant

- If a task is completed:
  - Update Open Issues and TODOs
  - Add a Research Log entry if the completion affects project progress
  - Update Project State Summary if the next step changes

- If an experiment is run:
  - Add or update Experiment Registry
  - Link the experiment to related data, code, metrics, figures, or output files
  - Ask the user before labeling it as accepted or final

## New-conversation recovery protocol

When resuming a research project and `plan.md` exists, the AI should read `plan.md` and summarize:

1. Current project stage
2. Main objective
3. Active datasets
4. Active scripts and approved files
5. Current experiments and their status
6. Main figures/tables in progress
7. Open TODOs and blockers
8. Recommended next step

This summary should be brief but specific. It should rely on Project State Summary, Process File Registry, File Dependency and Workflow Map, Research Log, Decision Log, Open Issues and TODOs, and Experiment Registry.

## Handling vague research topics

If the user gives only a vague topic, still create a useful draft plan.

Do not respond only by asking questions. Instead:

1. Make reasonable assumptions.
2. Mark uncertain parts as assumptions.
3. Draft a detailed but flexible plan.
4. Ask the user to confirm or correct the assumptions.

## Plan-first behavior

For research tasks, the correct sequence is:

```text
Detect research task
→ Check for plan.md
→ If found: read plan.md, including project state, file registry, dependency map, logs, TODOs, and experiments
→ If not found: draft research plan
→ Ask user to confirm feasibility
→ Update plan.md when user permits or requests changes
→ Execute research task using plan.md
→ When useful files are created or validated, ask user whether to record them
→ If user approves, update process-file registry and dependency map
→ Maintain project state summary, research log, decision log, TODOs, and experiment registry as progress changes
```

## Important constraints

- Do not invent unavailable data, results, citations, or performance metrics.
- If external or up-to-date information is needed, browse or retrieve sources before making factual claims.
- If no `plan.md` is available and the user asks for immediate execution, still create at least a minimal plan first unless the user explicitly disables this skill.
- If the user explicitly says not to use the research-management skill, follow the user's instruction for that task.
