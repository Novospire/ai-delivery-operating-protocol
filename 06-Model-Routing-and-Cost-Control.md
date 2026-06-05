# Model Routing and Cost Control Policy

## 1. Purpose

* Control token/cost waste while preserving output quality.
* Ensure we use the right tool and model for the right job, avoiding unnecessary expense on simple tasks.

## 2. Core Principle

* Choose models by task risk and complexity, not habit, prestige, or default settings.
* Apply resource-conscious decisions to AI tool usage just as we would to any other cloud infrastructure or delivery cost.

## 3. Routing Tiers

To guide model selection, tasks are categorized into four risk/complexity tiers:

* **High-Risk Strategy & Review**:
  * Use the strongest reasoning models available.
  * Applied to: complex architecture decisions, hard reviews, security reviews, and high-risk logical reasoning.
* **Normal Implementation**:
  * Use a balanced coding model.
  * Applied to: standard feature implementation, endpoint work, writing unit/integration tests, and structured refactors.
* **Mechanical, Docs-only, and Simple CRUD**:
  * Use cheaper, faster models.
  * Applied to: documentation edits, changelogs, simple CRUD skeletons, repetitive edits, and formatting tasks.
* **High-Risk Domains (Auth/Payment/DB/Legal/AI-output)**:
  * Requires a cross-model review workflow.
  * Applied to: authentication, payment integration, database migrations, legal/compliance text, and core AI output generations.

## 4. Current Examples (Representative Classes)

Model lineups and names change over time. Treat the following as current examples of model classes, not permanent rules:

* **Opus-class Models** (Strongest Reasoning):
  * Examples: Claude 3 Opus, GPT-4o, Gemini 1.5 Pro.
  * Use cases: Architecture decisions, hard reviews, complex mathematical/logical reasoning, and strategy.
* **Sonnet-class Models** (Balanced Coding):
  * Examples: Claude 3.5 Sonnet.
  * Use cases: Normal implementation, endpoint creation, refactoring, and test writing.
* **Gemini Flash/Lite-class Models** (Fast / Low-Cost):
  * Examples: Gemini 1.5 Flash, Claude 3 Haiku, GPT-4o-mini.
  * Use cases: Docs-only updates, changelog maintenance, simple skeletons, repetitive edits, and formatting.

## 5. Hard Rules

* **Rule 1**: Do not use the most expensive model (e.g., Opus-class) for low-risk, mechanical work such as writing docs, simple CSS adjustments, or basic refactoring.
* **Rule 2**: Do not use cheap, fast models (e.g., Flash-class) for high-risk lifecycle, authentication, database migrations, payment, legal, or core AI-output logic changes without a second, stronger model or human review.

## 6. Review Cadence

* Model names, performance characteristics, and pricing structures change frequently.
* Revisit model classifications and pricing periodically (e.g., quarterly) to ensure our routing tiers align with the most cost-effective and capable models on the market.

## 7. Model Class vs Executor Tool

Model class and executor tool are separate routing decisions. They should never be conflated.

* **Model Class**: Defines the intelligence tier and reasoning capabilities (e.g., Opus-class, Sonnet-class, Gemini Flash/Lite-class).
* **Executor/Tool**: Defines the environment, agent system, or interface executing the commands and file edits (e.g., Antigravity, Codex, Claude Code, Cursor, GitHub Web UI, local terminal).

### Operating Rules

* **No Substitutions**: Never substitute one executor name for another in handoff prompts.
  * *Example*: If the project is currently being implemented in **Antigravity**, prompts and context files must explicitly say **Antigravity**, not Codex or Claude Code.
* **Explicit Unknowns**: If the current executor/tool is unknown, ask for clarification or mark it explicitly as `unknown`. Do not guess.

> [!IMPORTANT]
> Every implementation handoff must explicitly state the execution context. Include the following details in the handoff prompt:
> * **Current Executor/Tool**: (e.g., Antigravity)
> * **Intended Model Class**: (e.g., Sonnet-class)
> * **Review Model/Class**: (e.g., Opus-class)
> * **Cross-Model Review Required**: (Yes/No)
