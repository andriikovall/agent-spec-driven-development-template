# Agent Spec Driven Development Template

A reusable baseline for agentic, specification-driven development. Start with the owner's intent, turn it into reviewable specifications, approve the scope, then implement and verify against explicit expectations.

This repository contains agent steering and Markdown templates only. It selects no framework, language, hosting, infrastructure, provider, or application architecture beyond the documented feature/core ownership convention.

## Start a new project

1. Choose **Use this template → Create a new repository** on GitHub.
2. Clone your new repository and give your coding agent [AGENTS.md](AGENTS.md) as its starting instructions. If your tool does not automatically read it, explicitly include it in the session.
3. Use the [bootstrap prompt](docs/PROMPTS.md#bootstrap-a-project) with your product brief. Replace the project title, owner, dates, release scope, and undecided settings in [specs/SPEC.md](specs/SPEC.md).
4. Have the agent draft the release and first feature specifications. Resolve the blocking questions, then explicitly approve each applicable specification.
5. Request implementation. The agent works in its own branch and worktree, verifies the acceptance criteria, and commits the change for review.

Creating a project from this template does not approve its specifications or authorize product implementation. All starter specifications are drafts.

## What is included

| File | Purpose |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Agent workflow, authority, isolation, approval, and verification rules |
| [specs/SPEC.md](specs/SPEC.md) | Project purpose, active release, dependencies, priorities, backlog |
| [specs/releases/initial/SPEC.md](specs/releases/initial/SPEC.md) | Initial release scope and measurable success gate |
| [specs/templates/FEATURE.md](specs/templates/FEATURE.md) | User behavior, business rules, and acceptance criteria |
| [specs/templates/CORE.md](specs/templates/CORE.md) | Reusable mechanism, public contract, and invariants |
| [specs/templates/RELEASE.md](specs/templates/RELEASE.md) | Subsequent release planning |
| [specs/templates/DECISION.md](specs/templates/DECISION.md) | Consequential decisions and alternatives |
| [specs/templates/RESEARCH.md](specs/templates/RESEARCH.md) | Sources, assumptions, findings, and feasibility evidence |
| [specs/templates/HANDOFF.md](specs/templates/HANDOFF.md) | Review and verification evidence |
| [docs/WORKFLOW.md](docs/WORKFLOW.md) | Lifecycle, status meanings, and worktree procedure |
| [docs/PROMPTS.md](docs/PROMPTS.md) | Reusable owner prompts |
| [examples/README.md](examples/README.md) | A fictional worked example of specification and verification |

## Working model

`Owner brief → draft specifications → research and decisions → owner approval → requested implementation → verification → review`

Approval and delivery are separate. An implemented feature can still await manual verification. A draft with passing tests is still unapproved. Agents do not grant approval to their own work.

Keep behavior specifications, research, implementation, and tests together under `src/features/<feature>/`. Introduce `src/core/<capability>/` only when a concrete consumer needs a separately governed reusable contract. The template creates neither speculative modules nor empty feature directories.

## Adapting the baseline

Use the workflow with any coding agent that can read project files. Keep `AGENTS.md` authoritative if you add tool-specific pointers. Replace the source-directory convention explicitly if the chosen language or project needs another layout; update the index and steering together. Select verification commands only after selecting the actual stack.

The baseline generalizes an existing project's steering practice. The example is fictional and contains no application source, private project data, infrastructure configuration, or inherited project approval.
