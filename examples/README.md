# Fictional example: a personal reading list

This is an illustration of the workflow, not the scope of a generated project. All example scope remains Draft; no owner approval or completed verification is implied.

## Brief → release

An owner wants to capture a book title and mark it read. The draft initial release proposes one user journey: add a title, see it in the list, and mark it read. Sharing, recommendations, and accounts are non-goals. Persistence and supported platforms remain explicit owner decisions rather than agent assumptions.

## Release → feature specification

A draft `src/features/reading-list/SPEC.md` would own title validation, list behavior, and read/unread transitions:

| ID | Draft acceptance criterion | Proposed verification |
| --- | --- | --- |
| AC-1 | Adding a nonblank title creates one unread entry | Feature acceptance test |
| AC-2 | A whitespace-only title is rejected without adding an entry | Validation and user feedback test |
| AC-3 | Marking an entry read changes that entry and preserves other entries | State transition regression test |
| AC-4 | A failed save leaves input recoverable and reports the failure | Failure injection after persistence is selected |

The owner resolves persistence and platform questions, then approves the release and feature specifications. Only a subsequent implementation request starts delivery.

## Boundaries

Title rules and read/unread behavior stay in the feature. A persistence helper stays private until a concrete shared contract justifies core. If such a contract becomes necessary, draft its core specification, identify consumers and failure semantics, and obtain approval before implementing it.

## Verification → review

The agent works on its own branch and worktree. Its handoff maps AC-1 through AC-4 to actual results, identifies outstanding platform checks, and updates delivery status accurately. If automated checks pass but a required keyboard check has not run, delivery stays Implemented. It becomes Verified only after every required gate has evidence.

If later evidence requires changing an approved persistence rule, the agent records the conflict and asks for that decision before changing the affected behavior.
