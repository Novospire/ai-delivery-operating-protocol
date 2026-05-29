# General AI Coding Protocol

## 1. Source of Truth

* Repository files are source of truth.
* Chat history is guidance only.
* AI summaries are not evidence.
* Verify through git diff, build/test/lint, local run, PR diff and documented decisions.

## 2. Small Ticket Rule

* One prompt should normally equal one small ticket.
* Do not mix docs, UI, backend, database, auth, API, deployment and refactor work.
* If scope expands, stop and create a new ticket.

## 3. WIP Safety

* Start every session with branch/status/log checks.
* Never work on dirty WIP without understanding it.
* Never commit .env, secrets, local artifacts, node_modules, .next, build outputs or backup folders.
* Local backup files should stay local unless explicitly approved.

## 4. Branch and PR Discipline

* Never push directly to main.
* Use branch → PR → review → merge.
* Prefer squash merge.
* PR history must be clean before merge.
* Dirty PR history should be cleaned through backup branch, reset and cherry-pick when needed.

## 5. Planning Before Implementation

* Non-trivial tasks require a short plan before file edits.
* Risky tasks require a challenge/review pass before implementation.
* Agent must state intended files before editing.

## 6. Verification Before Done

* Agent cannot mark work done without evidence.
* Required evidence may include:

  * changed files list
  * git diff summary
  * build/test/lint output
  * local verification notes
  * known warnings / non-blockers
* Old warnings are not fixed opportunistically.

## 7. Technical Debt Firewall

* Technical debt seen during a ticket must be logged, not silently fixed.
* Only fix technical debt if it blocks the current ticket or is explicitly included in scope.

## 8. Docs vs Code Separation

* Docs PRs must not touch application code.
* Code PRs must update docs only when behavior, architecture, contract or product truth changes.
* General protocol updates must not be mixed with project feature work.

## 9. Agent Context Discipline

* Do not ask agents to scan the whole repo by default.
* Provide exact files, current ticket, acceptance criteria and forbidden scope.
* Prefer short project-local context files over long chat context.

## 10. Tool Discipline

* ChatGPT/Summer: scope, strategy, prompt, review and decision gate.
* Claude Code: implementation, debug, refactor and terminal/log analysis.
* Codex: implementation or PR review / second opinion.
* Antigravity: UI/layout and visual iteration.
* NotebookLM/MCP/RAG/subagents/plugins: project-specific only, not default.

## 11. Tool Adoption Filter

Every new tool or workflow idea must be classified as:

* ACCEPT_NOW
* PILOT_LATER
* REJECT_FOR_NOW
* PROJECT_SPECIFIC_ONLY
* NEEDS_VERIFICATION
* ACCEPT_PARTIAL
* REJECT_AS_DEFAULT

## 12. Hard Rule

If a process does not make delivery safer, faster, clearer or more repeatable, it does not belong in the workflow.
