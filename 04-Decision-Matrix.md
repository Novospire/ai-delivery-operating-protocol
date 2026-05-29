# Decision Matrix

## Purpose

This document tracks which AI workflow ideas are accepted, delayed, rejected or project-specific.

A decision is not accepted because it sounds advanced.

A decision is accepted only if it makes delivery safer, faster, clearer or more repeatable.

## Status Values

* ACCEPT_NOW
* PILOT_LATER
* REJECT_FOR_NOW
* PROJECT_SPECIFIC_ONLY
* NEEDS_VERIFICATION
* ACCEPT_PARTIAL
* REJECT_AS_DEFAULT

## Core Decisions

| Topic                        | Decision                                                                |                Status | Applies To                | Notes                                      |
| ---------------------------- | ----------------------------------------------------------------------- | --------------------: | ------------------------- | ------------------------------------------ |
| Repo source of truth         | Repo files, git diff, build/test output and PR diff are source of truth |            ACCEPT_NOW | All projects              | Chat is guidance only                      |
| Small ticket workflow        | One prompt should normally equal one small ticket                       |            ACCEPT_NOW | All projects              | Prevents scope creep                       |
| Branch + PR workflow         | Never push directly to main                                             |            ACCEPT_NOW | All projects              | Use branch → PR → review → merge           |
| Clean WIP before work        | Start with branch/status/log checks                                     |            ACCEPT_NOW | All projects              | Dirty WIP must be understood first         |
| Docs/code separation         | Docs PRs must not touch application code                                |            ACCEPT_NOW | All projects              | Prevents hidden scope expansion            |
| Technical debt firewall      | Old warnings are logged, not fixed opportunistically                    |            ACCEPT_NOW | All projects              | Separate ticket unless blocking            |
| PR history hygiene           | Dirty PR history must be cleaned before merge                           |            ACCEPT_NOW | All projects              | Backup branch/reset/cherry-pick if needed  |
| Context-Pack                 | Use short project context instead of full chat memory                   |            ACCEPT_NOW | All projects              | Reduces token waste                        |
| Current-State.md             | Track current repo state in project-local docs                          |            ACCEPT_NOW | All projects              | Helps fresh sessions                       |
| Next-Ticket.md               | Keep one active ticket visible to agents                                |            ACCEPT_NOW | All projects              | Prevents ambiguity                         |
| AGENTS.md                    | Add repo-level rules for Codex/general coding agents                    |            ACCEPT_NOW | All coding projects       | Short and operational                      |
| CLAUDE.md                    | Add Claude Code project memory                                          |            ACCEPT_NOW | Claude Code projects      | Avoid vague rules                          |
| DESIGN.md / Design-Reference | Use for UI consistency                                                  |            ACCEPT_NOW | UI projects               | Especially Antigravity workflows           |
| Claude Code                  | Use for multi-file implementation/debug/refactor                        |            ACCEPT_NOW | All coding projects       | Must show diff/verification                |
| Codex                        | Use for implementation or PR review/second opinion                      |            ACCEPT_NOW | All coding projects       | Good for scope/architecture checks         |
| Antigravity                  | Use for UI/layout/visual iteration                                      |            ACCEPT_NOW | UI/frontend work          | Not backend/auth/db by default             |
| NotebookLM                   | Use for long docs/PDF/research only                                     | PROJECT_SPECIFIC_ONLY | Maretech, Flowpilot later | Not repo truth                             |
| MCP/RAG                      | Use only when real retrieval problem exists                             | PROJECT_SPECIFIC_ONLY | Flowpilot/Maretech later  | Not default workflow                       |
| Subagents                    | Do not use routinely yet                                                |           PILOT_LATER | Maretech/Flowpilot later  | Start with one reviewer subagent if needed |
| Hooks                        | Do not add heavy hooks initially                                        |           PILOT_LATER | All projects              | Light safety hooks later                   |
| AgentField.ai                | Too heavy for current stage                                             |        REJECT_FOR_NOW | Flowpilot later           | Avoid infrastructure distraction           |
| 10-15 parallel sessions      | Not default workflow                                                    |     REJECT_AS_DEFAULT | All projects              | High control-loss risk                     |
| Cross-model review           | Use only for high-risk work                                             |            ACCEPT_NOW | Risky tasks               | Auth, payment, DB, legal, AI output        |
| Fresh Opus reviewer          | Use for high-risk decision/review only                                  |            ACCEPT_NOW | Risky tasks               | Not for small CSS/text edits               |
| Karpathy-style rules         | Keep clarity, minimal edits, surgical changes                           |        ACCEPT_PARTIAL | All projects              | Do not blindly copy full repo              |
| Plugin hunting               | Do not install plugins without clear benefit                            |        REJECT_FOR_NOW | All projects              | One tool, one project, one pilot           |
| Gemini capacity              | Do not assume unlimited quota                                           |    NEEDS_VERIFICATION | Gemini workflows          | Verify account/limits first                |

## Project-Specific Risk Areas

| Project               | Main Risk                                                | Required Control                   |
| --------------------- | -------------------------------------------------------- | ---------------------------------- |
| Maretech              | AI output, legal/diagnosis language, app/site separation | Detailed workflow + challenge pass |
| İyikitap              | SEO, affiliate flow, admin/import, Prisma                | Small tickets + PR discipline      |
| Haremaltın-style site | Data source, API quota, formula, financial language      | Data/legal decision brief          |
| Flowpilot             | Customer data, CRM automation, approval workflow         | Privacy + approval protocol        |

## Hard Rule

If a decision increases complexity without reducing delivery risk, it should be rejected or delayed.
