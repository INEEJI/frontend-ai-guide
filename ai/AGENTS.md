# AGENTS.md (For Codex CLI, Cursor agent)

This repository follows the rules defined in **TEAM_GUIDE.md**.

All AI agents working in this repository must follow that guide.

## Key Rules

1. Make the **smallest safe change** that solves the task.
2. Do **not refactor unrelated code**.
3. In legacy files, **improve only the touched area**.
4. Do not introduce new dependencies without clear justification.
5. Separate refactor proposals from implementation work.

## Legacy Code Policy

Some files may be extremely large or poorly structured.

When working with such files:

- preserve existing behavior
- do not rewrite the file
- extract small helpers or constants only if needed for clarity
- propose larger refactors separately

## Output Expectations

When presenting changes:

- show only relevant changes when possible
- explain assumptions briefly
- highlight any risks or areas that should be verified