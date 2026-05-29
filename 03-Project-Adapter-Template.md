# Project Adapter Template

## Purpose

This template converts the general AI Delivery Operating Protocol into a short project-specific operating layer.

Do not copy the full general protocol into project repositories.

Each project should receive only the minimum rules needed to guide AI coding safely.

## 1. Project Identity

Project name:

Repo URL:

Current phase:

Primary product type:

Primary users:

Current status:

## 2. Source-of-Truth Files

List the files agents should read first.

Required:

- README.md
- AGENTS.md
- CLAUDE.md
- docs/00-context/Context-Pack.md
- docs/00-context/Current-State.md
- docs/00-context/Next-Ticket.md
- docs/00-context/Agent-Operating-Protocol.md

Optional:

- docs/00-context/Design-Reference.md
- DESIGN.md
- ADR files
- API spec
- PRD
- Sprint backlog
- Research summary

## 3. Non-Negotiables

Define project-specific rules that must not be broken.

Examples:

- product boundaries
- legal language boundaries
- pricing rules
- data handling rules
- user flow constraints
- architecture constraints

## 4. Forbidden Scope

List what agents must not touch unless explicitly approved.

Examples:

- auth
- payments
- database schema
- migrations
- deployment
- production config
- legal wording
- unrelated UI
- package dependencies

## 5. Tool Allocation

ChatGPT / Summer:

Claude Code:

Codex:

Antigravity:

NotebookLM / MCP / RAG:

Other tools:

## 6. Workflow Level

Basic Workflow applies to:

Detailed Workflow applies to:

Challenge/review pass required for:

## 7. Current Ticket Format

Each active ticket must define:

- title
- goal
- allowed files
- forbidden files
- acceptance criteria
- verification commands
- known non-blockers
- stop conditions

## 8. Agent Handoff Format

Every AI tool handoff should include:

- repo URL
- branch
- files to read
- current ticket
- non-negotiables
- allowed files
- forbidden files
- expected output
- verification requirements
- stop conditions

## 9. PR Requirements

Every PR must include:

- why
- scope
- non-scope
- changed files
- verification
- known warnings
- related ADRs or tickets when applicable

## 10. Project-Specific Risk Checklist

Before implementation, check:

- Does this violate product boundaries?
- Does this touch forbidden files?
- Does this mix unrelated work?
- Does this require an ADR?
- Does this require a challenge/review pass?
- Does this require docs update?
- Does this require legal, data, payment or security review?

## 11. Hard Rule

A project adapter must be short, operational and specific.

If it becomes a general manifesto, it has failed.
