# AI Delivery Operating Protocol — Start Here

## Purpose

This repository/folder defines the general AI-assisted coding and delivery protocol used across Novospire projects.

Current target projects:

1. Maretech App + Maretech Marketing Site  
2. İyikitap  
3. Haremaltın-style Gold/Currency Tracking Site  
4. Flowpilot  

The purpose is not to collect more AI tools.

The purpose is to make AI-assisted development:

- cheaper
- safer
- faster
- more repeatable
- less dependent on chat memory
- easier to continue across Claude Code, Codex, Antigravity, ChatGPT and future tools

## Core Principle

Repo files are source of truth.

Chat history is guidance only.

AI outputs are never accepted as truth unless verified through:

- actual repository files
- git diff
- build/test/lint output
- local verification
- pull request diff
- documented decisions

## Why This Exists

The main risk is not lack of tools.

The main risks are:

- too many tools
- too much context
- too many agents
- vague prompts
- large tickets
- scope creep
- trusting AI summaries without checking files
- losing context between sessions
- mixing product decisions with implementation
- allowing coding agents to touch unrelated files

This protocol exists to prevent those failures.

## Operating Model

ChatGPT / Summer acts as:

- product and delivery strategist
- scope controller
- ticket writer
- prompt writer
- risk challenger
- quality gate
- decision filter

Coding or implementation tools may include:

- Claude Code
- Codex
- Antigravity
- Gemini / Gemini CLI when useful
- NotebookLM / MCP only for specific research or document workflows

No AI tool is treated as autonomous owner of the project.

## Project Repositories vs General Protocol

This general protocol is not copied wholesale into every project repository.

Each project repo gets only a short, project-specific operating layer.

General protocol lives here.

Project-specific truth lives inside each project repo.

Example:

### General Protocol

Defines:

- common AI coding rules
- platform playbooks
- decision matrix
- reusable templates
- tool adoption filter
- repo/WIP safety rules

### Maretech Repo

Should contain only Maretech-specific rules such as:

- Osmosis and Corrosion are two separate products under one app shell
- no diagnosis language
- not a survey replacement
- probabilistic visual-signal language only
- async-only inference
- app and marketing site are separate workstreams

### İyikitap Repo

Should contain only İyikitap-specific rules such as:

- editorial affiliate commerce logic
- FiveBooks-style list structure
- Amazon affiliate flow
- SEO slug rules
- Monocle-style editorial visual direction

### Haremaltın-style Repo

Should contain only project-specific rules such as:

- data provider decision
- API quota and refresh logic
- formula transparency
- financial/legal language boundaries
- no investment-advice positioning

### Flowpilot Repo

Should contain only project-specific rules such as:

- SME workflow selection
- approval-based automation
- CRM/customer data boundaries
- demo scenario
- privacy/security constraints

## Standard Project Adapter

Every project should have a compact adapter derived from this protocol.

Minimum project-local files:

- AGENTS.md
- CLAUDE.md
- docs/00-context/Context-Pack.md
- docs/00-context/Current-State.md
- docs/00-context/Next-Ticket.md
- docs/00-context/Agent-Operating-Protocol.md
- docs/00-context/Design-Reference.md or DESIGN.md when UI matters
- .claude/commands/repo-safety.md
- .claude/commands/challenge.md
- .claude/commands/pr-review.md
- .github/pull_request_template.md
- CONTRIBUTING.md

Not every project needs every file on day one.

The minimum useful set should be added before meaningful AI coding work begins.

## Universal Rules

1. Never push directly to main.
2. Use branch → PR → review → merge.
3. One prompt should normally equal one small ticket.
4. Do not mix docs, UI, backend, database, auth, API and deployment changes in one ticket.
5. Do not trust AI summaries without checking the actual diff.
6. Do not let agents scan the whole repo by default.
7. Give agents exact files, current ticket, acceptance criteria and forbidden scope.
8. Build/test/lint/local verification is required before “done”.
9. Technical debt is not fixed opportunistically.
10. Old warnings are logged and scheduled as separate tickets unless they block the current task.
11. PR history must be clean before merge.
12. Dirty WIP must be secured before new work starts.
13. Local artifacts must not be committed.
14. General protocol updates must not be mixed with project feature work.
15. Project-specific rules must stay short and operational.

## Tool Adoption Filter

Every new AI tool, plugin, MCP server, RAG system, subagent setup or automation idea must be classified before use.

Allowed statuses:

- ACCEPT_NOW
- PILOT_LATER
- REJECT_FOR_NOW
- PROJECT_SPECIFIC_ONLY
- NEEDS_VERIFICATION
- ACCEPT_PARTIAL
- REJECT_AS_DEFAULT

Evaluation questions:

1. What real problem does this solve?
2. Is it needed at the current stage?
3. Does it reduce token/context cost or increase it?
4. Does it respect repo source-of-truth?
5. Does it fit Windows/local/GitHub workflow?
6. Does it create security or data exposure risk?
7. Can it be tested in one project first?
8. Which project actually benefits from it?
9. Can it be removed easily if it fails?
10. Does it make the workflow simpler or more fragile?

## Current Rollout Order

### Phase 0 — Build the General Protocol Archive

Create and maintain:

- 00-START-HERE.md
- 01-General-AI-Coding-Protocol.md
- 02-Platform-Playbooks.md
- 03-Project-Adapter-Template.md
- 04-Decision-Matrix.md
- 05-Templates-Pack.md

### Phase 1 — Apply to Maretech

Create a Maretech-specific agent operating layer before the next implementation sprint.

Maretech is the first pilot because it has high-risk product boundaries:

- AI visual analysis
- legal/diagnosis language risk
- mobile app architecture
- app/site workstream separation
- two products under one shell

### Phase 2 — Apply to İyikitap

Use the same structure, but adapt it to:

- editorial affiliate commerce
- SEO
- admin/import
- Prisma
- Amazon affiliate redirect
- visual design consistency

### Phase 3 — Apply to Haremaltın-style Site

Adapt it to:

- data provider selection
- API quota
- refresh strategy
- formula policy
- financial/legal language

### Phase 4 — Apply to Flowpilot

Adapt it to:

- SME workflow
- approval-based automation
- customer data
- CRM/Notion/n8n integrations
- portfolio/demo positioning

## Non-Goal

This protocol is not an attempt to build a complex multi-agent infrastructure.

It is not a tool collection project.

It is not a prompt library.

It is not an AI hype tracker.

It is an operating system for controlled, repo-first, small-ticket AI-assisted delivery.

## Hard Rule

If a process does not make the work safer, faster, clearer or more repeatable, it does not belong here.
