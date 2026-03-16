# AI Engineering Guide

This repository includes a lightweight guideline for using AI tools
safely and consistently across our projects.

The goal is **not to enforce heavy processes**, but to help us:

-   keep code maintainable
-   avoid large unintended refactors
-   work safely with legacy codebases
-   make AI-assisted development predictable

The core rules are defined in **TEAM_GUIDE.md**.

------------------------------------------------------------------------

# Quick Start

If you are using AI tools such as **Cursor, Codex, or Claude Code**,
these files provide the context for how AI should behave in this
repository.

    TEAM_GUIDE.md → core engineering rules  
    AGENTS.md → instructions for Codex / Cursor agents  
    CLAUDE.md → instructions for Claude Code

AI tools automatically read these files when generating or modifying
code.

------------------------------------------------------------------------

# Key Principles

When working with AI in this repository:

1.  **Make the smallest safe change**
2.  **Do not refactor unrelated code**
3.  **Improve only the touched area in legacy files**
4.  **Propose larger refactors separately**

These rules exist to prevent AI from making large unintended changes.

------------------------------------------------------------------------

# Working With Legacy Code

Some projects contain very large or messy files.

When modifying legacy code:

✔ preserve existing behavior\
✔ improve only the modified area\
✔ extract small helpers if needed

Avoid:

✘ rewriting entire files\
✘ restructuring modules without a dedicated task\
✘ introducing new patterns unnecessarily

------------------------------------------------------------------------

# Typical AI Workflow

Recommended workflow when using AI tools:

1.  Ask AI to analyze the relevant code
2.  Implement the smallest safe change
3.  Verify the change manually or with tests
4.  If structural problems are discovered → create a separate refactor
    task

Example:

Bad:

    Fix bug + refactor module + move files

Good:

    Fix bug
    → propose refactor separately

------------------------------------------------------------------------

# When To Propose Refactoring

Instead of refactoring immediately, propose a refactor task if:

-   a file is extremely large (1000+ lines)
-   the module has unclear responsibilities
-   the same logic is duplicated many times
-   the code repeatedly causes bugs

------------------------------------------------------------------------

# What This Guide Does NOT Do

This guide intentionally avoids strict architecture rules.

It does **not enforce**:

-   specific folder structures
-   specific frameworks
-   heavy documentation processes

Different projects may use different stacks.

The only requirement is that **changes remain safe and maintainable**.

------------------------------------------------------------------------

# Updating The Guide

If we notice recurring issues with AI-generated code, we update the
guide.

The guide will evolve gradually:

    v1.0 → basic AI safety rules  
    v1.1 → code structure conventions  
    v1.2 → workflow improvements

The goal is **continuous improvement**, not perfection from day one.

------------------------------------------------------------------------

# Summary

Use AI freely, but follow these principles:

-   small changes
-   no unrelated refactors
-   gradual improvements
-   maintainable code

If unsure, prefer **safe and minimal changes**.

------------------------------------------------------------------------

**Important:**\
AI tools must follow the rules defined in `TEAM_GUIDE.md`.
