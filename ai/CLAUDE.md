# CLAUDE.md (For Claude Code)

This project follows the engineering rules defined in **TEAM_GUIDE.md**.

Always read and follow that document before making changes.

## Important Rules

- Prefer small, safe, incremental changes.
- Do not refactor unrelated code.
- When editing legacy files, improve only the touched area.
- Do not copy poor legacy patterns into new code.
- If broader cleanup is needed, propose it separately.

## When Writing Code

Prefer:

- clear logic
- descriptive naming
- minimal side effects
- small helper functions when useful

Avoid:

- clever but hard-to-read code
- unnecessary abstraction
- rewriting large files

## When Modifying Existing Code

- preserve behavior unless change is requested
- keep edits localized
- suggest larger improvements separately