# Templates Pack

## Purpose

Reusable templates for project-local AI coding workflow files.

These templates must be adapted per project.

Do not copy them blindly.

## 1. AGENTS.md Template

```md
# AGENTS.md

## Source of Truth

Use repository files as source of truth.

Chat history is guidance only.

Read first:

- README.md
- docs/00-context/Context-Pack.md
- docs/00-context/Current-State.md
- docs/00-context/Next-Ticket.md
- docs/00-context/Agent-Operating-Protocol.md

## Rules

- Never push directly to main.
- Use branch → PR → review → merge.
- One task = one small ticket.
- Do not expand scope without approval.
- Do not edit forbidden files.
- Show changed files and verification before done.

## Forbidden by Default

- secrets
- .env
- local artifacts
- node_modules
- build outputs
- database migrations
- package dependencies
- production config

## PR Requirements

Include:

- why
- scope
- non-scope
- changed files
- verification
```

## 2. CLAUDE.md Template

```md
# CLAUDE.md

## Project Memory

This file gives Claude Code short project-local operating rules.

Do not treat chat history as source of truth.

Read first:

- AGENTS.md
- docs/00-context/Context-Pack.md
- docs/00-context/Current-State.md
- docs/00-context/Next-Ticket.md

## Claude Code Rules

- Start with repo safety checks.
- Read only relevant files.
- Plan before non-trivial edits.
- State intended files before editing.
- Show diff and verification before done.
- Do not perform opportunistic refactors.
- Do not silently fix unrelated technical debt.
```

## 3. Current-State.md Template

```md
# Current State

## Last Confirmed Baseline

Branch:

Commit:

Date:

## Current Status

## Completed

## In Progress

## Known Warnings / Non-Blockers

## Open Risks

## Next Recommended Ticket
```

## 4. Next-Ticket.md Template

```md
# Next Ticket

## Title

## Goal

## Allowed Files

## Forbidden Files

## Acceptance Criteria

## Verification Commands

## Known Non-Blockers

## Stop Conditions
```

## 5. Agent-Operating-Protocol.md Template

```md
# Agent Operating Protocol

## Tool Roles

ChatGPT / Summer:

Claude Code:

Codex:

Antigravity:

NotebookLM / MCP / RAG:

## Basic Workflow

Use for:

## Detailed Workflow

Use for:

## Challenge Required When

## Forbidden Scope

## Done Means

Done requires:

- changed files list
- diff summary
- verification output
- known warnings
```

## 6. Design-Reference.md Template

```md
# Design Reference

## Visual Direction

## Product Feeling

## Primary References

## Allowed UI Changes

## Forbidden UI Changes

## Typography / Color / Layout Notes

## Screens or Sections in Scope

## Screens or Sections Out of Scope
```

## 7. .claude/commands/repo-safety.md Template

```md
# repo-safety

Check repository safety only.

Do not edit files.

Report:

- current branch
- git status
- latest commits
- changed files
- whether it is safe to proceed
- risks or stop conditions
```

## 8. .claude/commands/challenge.md Template

```md
# challenge

Act as a skeptical senior reviewer.

Do not edit files.

Review the current plan for:

- scope creep
- unnecessary complexity
- product boundary violations
- security/data/legal risk
- simpler alternatives
- missing verification
```

## 9. .claude/commands/pr-review.md Template

```md
# pr-review

Review the PR before merge.

Check:

- changed files
- scope vs non-scope
- forbidden files
- build/test/lint evidence
- documentation impact
- known warnings
- merge readiness

Return:

- mergeable: yes/no
- blockers
- non-blocking notes
- recommended next action
```

## 10. Pull Request Template

```md
## Why

## Scope

## Non-scope

## Changed Files

## Verification

## Known Warnings / Non-Blockers

## Related Tickets / ADRs

## Merge Checklist

- [ ] Scope is limited
- [ ] No forbidden files changed
- [ ] Verification completed
- [ ] No secrets or local artifacts
- [ ] Ready for squash merge
```

## Hard Rule

Templates are starting points.

Project-specific adapters must stay short, operational and specific.
