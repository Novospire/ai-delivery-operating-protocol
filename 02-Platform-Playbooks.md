# Platform Playbooks

## Purpose

This document defines how each AI tool should be used inside the Novospire AI delivery workflow.

The goal is not to maximize tool usage.

The goal is to use each tool only where it creates leverage.

## 1. ChatGPT / Summer

Primary role:

* product strategy
* project planning
* scope control
* ticket writing
* prompt writing
* risk challenge
* decision filtering
* PR/diff review support
* continuity between projects

ChatGPT / Summer should decide:

* what should be built
* what should not be built
* which tool should do the work
* whether a task is Basic Workflow or Detailed Workflow
* whether a second review is needed

ChatGPT / Summer should not be treated as the source of truth for repo state.

Repo files, git diff, build/test output and PR diff remain source of truth.

## 2. Claude Code

Best used for:

* multi-file implementation
* debugging
* refactoring
* terminal/log-based investigation
* backend work
* test-oriented fixes
* structured code changes

Required behavior:

* start with repo safety checks
* read only the relevant files
* use plan mode for non-trivial tasks
* state intended files before editing
* show diff and verification before “done”

Useful commands or patterns:

* repo safety check
* plan before implementation
* diff review
* challenge pass
* PR review pass
* compact context when session grows

Claude Code should not be used as an uncontrolled autonomous agent.

## 3. Codex

Best used for:

* implementation
* PR review
* TypeScript / Next.js / architecture checks
* scope creep detection
* second opinion on risky diffs

Codex should be given:

* exact repo context files
* current ticket
* acceptance criteria
* forbidden scope
* changed files or PR diff when reviewing

Codex should not be asked to infer the whole product from chat history.

## 4. Antigravity

Best used for:

* UI/layout passes
* screenshot-based visual iteration
* frontend visual refinement
* design-to-code exploration
* marketing site or landing page iteration

Antigravity should not be used by default for:

* auth
* payments
* database migrations
* Prisma/schema changes
* backend architecture
* legal wording
* production deployment
* large uncontrolled repo edits

Antigravity prompts must define:

* exact UI scope
* files allowed to change
* files forbidden to change
* visual reference
* non-scope
* verification expectations

## 5. Gemini / Gemini CLI

Use only when it provides clear value, such as:

* cheaper first-pass analysis
* broad file reading
* exploratory review
* alternative implementation suggestions

Do not assume Gemini capacity is unlimited.

Always verify account, quota and connected tool context before relying on it.

## 6. NotebookLM / MCP / RAG

Use only for project-specific research or document workflows.

Good use cases:

* technical PDFs
* standards
* legal/compliance documents
* long research notes
* literature summaries
* customer documents

Bad use cases:

* replacing repo source of truth
* dumping raw research into a project repo
* adding retrieval architecture before a real retrieval problem exists

Research should be converted into decisions before entering repo context.

## 7. Cross-Model Review

Use cross-model review only for high-risk work.

Good use cases:

* auth
* payments
* database migrations
* API contracts
* security-sensitive code
* production deployment
* AI output wording
* legal/medical/financial-risk language
* major architecture decisions

Do not use cross-model review for:

* small CSS changes
* simple copy edits
* minor layout spacing
* demo visual variants
* low-risk component changes

## 8. Default Tool Routing

Ticket definition:
ChatGPT / Summer

UI/layout:
Antigravity or Claude Code, depending on repo maturity

Backend implementation:
Claude Code or Codex

Debug:
Claude Code

PR review:
Codex or Claude Code challenge pass

Architecture decision:
ChatGPT / Summer first, then Codex or Claude review if needed

Document/research review:
NotebookLM or Claude, then decision summary into repo docs

## 9. Handoff Format

Every handoff to an AI coding tool should include:

* repo URL
* current branch
* source-of-truth files to read
* current ticket
* acceptance criteria
* allowed files
* forbidden files
* verification commands
* stop conditions

## 10. Hard Rule

Do not choose the most powerful tool.

Choose the smallest tool and smallest context that can safely complete the task.
