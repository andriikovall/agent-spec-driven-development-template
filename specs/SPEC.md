# <Project name> project specification

Status: Draft project index
Owner: <project owner>
Last updated: YYYY-MM-DD

## Product purpose

Pending the owner's brief: intended users, problem, and observable value.

## Current release

The [initial release](releases/initial/SPEC.md) is a draft. No product implementation is authorized.

## Specification authority

| Concern | Source of truth |
| --- | --- |
| Purpose, priorities, dependencies, backlog | This file |
| Cross-feature scope and success gate | Active release specification |
| User flows, business policy, acceptance criteria | `src/features/<feature>/SPEC.md` |
| Reusable contracts and invariants | `src/core/<capability>/SPEC.md` |
| Cross-cutting decisions | `specs/decisions/` when needed |
| Evidence | Co-located `research/` when needed |
| Agent procedure | [AGENTS.md](../AGENTS.md) |

State requirements once and link to them. Lower-level documents clarify higher-level requirements; they cannot silently change them. Examples and templates are not approved project requirements.

## Repository settings

- Remote: confirm from this project's Git configuration before work.
- Integration branch: confirm with the owner and remote default branch; do not inherit a branch name from the source template.
- Agent branch prefix: `codex/` (change explicitly for another team convention).
- Verification commands: pending actual implementation stack.

## Active feature index

None. Promote an item using [FEATURE.md](templates/FEATURE.md) when discovery or delivery is requested.

## Active core index

None. Use [CORE.md](templates/CORE.md) only for a concrete reusable contract.

## Dependency direction

`application composition → features → core`

Features expose public contracts for composition; they do not import one another's private files. Core never imports features.

## Delivery order

1. Capture the brief and initial release success gate.
2. Draft affected feature and core specifications.
3. Resolve consequential decisions and feasibility gates.
4. Obtain owner approval before requested implementation.
5. Implement, verify, and hand off for review.

## Selected implementation direction

Pending. No language, framework, infrastructure, provider, or persistence choice is inherited.

## Global product guardrails

Pending: supported platforms, accessibility, languages, data/privacy obligations, and constraints from the owner.

## Backlog

None yet. Record priority, purpose, and known dependencies without creating placeholder modules.

## Promotion rule

Create a draft feature specification when the owner requests discovery or delivery. Link it here, record dependencies, and check consistency with the active release.
