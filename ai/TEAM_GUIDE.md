# TEAM_GUIDE.md

## Purpose

This guide defines the minimum engineering rules for working across many ongoing projects with mixed code quality.
The goal is not to make every project perfect immediately.
The goal is to make each change safer, clearer, and easier to maintain over time.

## Principles

- Prefer small, safe, well-explained changes.
- Prefer consistency and readability over cleverness.
- Improve code gradually within the area you touch.
- Do not spread poor existing patterns into new code.
- Do not attempt large cleanups unless explicitly requested.

## Scope of Change

- Solve the requested task with the smallest safe change.
- Do not refactor unrelated modules or files.
- Do not rename, move, or reorganize large areas unless requested.
- If a broader cleanup is needed, propose it separately instead of bundling it into the current task.

## Working in Legacy or Messy Code

Existing code may be inconsistent, overly large, or poorly structured.
Do not try to fix the whole file at once.

When editing legacy code:
- preserve current behavior unless a behavior change is requested
- improve only the touched area or the smallest safe surrounding area
- make one level of improvement, not a full rewrite
- avoid copying bad patterns into newly written code
- if the file is extremely large or tangled, prefer extracting a small helper, constant block, type, or subcomponent rather than rewriting the file

If the touched file is very large:
- do not split it just to satisfy style preferences
- split only when the extracted part has a clear responsibility and low risk
- keep the extraction behaviorally identical

## Consistency Rules

- Follow the existing project conventions first when they are reasonable.
- If existing conventions are inconsistent, choose the most local and most established pattern in the touched area.
- For new files or new modules, use the team standard rather than copying legacy structure blindly.
- Keep naming consistent with nearby code, but prefer clearer names for newly introduced code.

## Code Quality Rules

- Prefer explicit logic over compact or clever code.
- Avoid hidden side effects.
- Avoid magic numbers when a named constant would improve clarity.
- Use descriptive names for variables, functions, components, and types.
- Keep branching and nesting under control; extract small helpers when this clearly improves readability.
- Add short comments only for non-obvious intent, assumptions, constraints, or legacy quirks.

## File and Function Size

These are guidance thresholds, not hard blockers.

- Prefer files under roughly 300–500 lines when practical.
- Prefer functions under roughly 40–80 lines when practical.
- If a file or function exceeds this, do not rewrite it automatically.
- When touching oversized code, improve only the part being changed unless a dedicated refactor is requested.

## Dependencies

- Do not add a new dependency unless it provides clear value that existing code cannot reasonably cover.
- Prefer existing platform or project utilities first.
- If a new dependency is introduced, explain why.

## Specs and Documentation

Documentation should be lightweight and proportional to risk.

Create or update a short spec / task note when:
- behavior is ambiguous
- the change affects multiple modules
- public API, data contract, or workflow changes
- the code is risky enough that future maintainers will need context

Specs should describe current behavior first, then intended changes.
Do not write idealized specs that do not match reality.

## Verification

After making changes:
- state what changed
- state what did not change
- state what should be checked manually or by tests

When changing logic, add or suggest the smallest realistic verification method.

## Output Behavior for AI Agents

When modifying code:
- be concise
- explain major assumptions briefly
- avoid unrelated refactors
- prefer incremental edits over full rewrites
- if a larger refactor is needed, separate “now” from “later”

When presenting code changes:
- show only changed sections when possible
- keep comments focused on why, not what
- clearly mark newly introduced or changed parts

## Escalation

Pause and call out risk before proceeding if:
- behavior cannot be inferred safely
- the change may break external integrations
- a large legacy file likely needs structural refactoring beyond the requested task
- the task mixes bug fix, refactor, and feature work in one step

## Default Refactor Policy

- If code is messy but stable, do not rewrite it without a clear reason.
- If code is messy and being actively changed, improve it gradually in the touched area.
- If code is risky and blocks repeated work, propose a dedicated refactor task.