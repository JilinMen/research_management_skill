# Research Management Skill

A custom AI skill for managing research projects across conversations.

## Files

- `SKILL.md`: Main instruction file for the research-management skill.
- `plan_template.md`: Template for creating or maintaining `plan.md` in a research project.

## Core idea

When the AI detects that the user is doing research, it should first check for `plan.md` before substantive thinking, writing, coding, or analysis.

- If `plan.md` exists, the AI reads it first and uses it as the project state.
- If `plan.md` does not exist, the AI drafts a detailed research plan and asks the user to confirm feasibility before execution.
- During the research process, the AI maintains not only the plan, but also important process files, file dependencies, logs, decisions, TODOs, and experiments.

## Continuity modules in `plan.md`

The skill asks the AI to maintain:

1. Project State Summary
2. Research Plan
3. Process File Registry
4. File Dependency and Workflow Map
5. Research Log
6. Decision Log
7. Open Issues and TODOs
8. Experiment Registry

This is designed to make future conversations recover the project objective, current status, active datasets, approved scripts, model versions, figures, experiments, decisions, blockers, and next steps from `plan.md`.
