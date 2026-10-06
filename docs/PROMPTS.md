# Owner prompts

Replace bracketed text before use. These prompts request work; approval must be an explicit owner decision.

## Bootstrap a project

> Read AGENTS.md and specs/SPEC.md. My project brief is: [users, problem, essential flow, constraints, and success measure]. Adapt the draft index and initial release, then draft the first feature specifications. Resolve discoverable questions from repository context and primary sources. Record blocking owner decisions. Do specification and research work only; do not implement or approve specifications.

## Promote a backlog item

> Promote [item] for discovery. Read the active release and affected specifications. Draft its feature specification, update the index and dependencies, investigate feasibility, and record the owner decisions needed for approval. Do not implement it.

## Approve specified scope

> I approve [exact specification paths and revision/commit] for [scope]. Record this approval in those specifications. These are my resolved decisions: [decisions]. This approval alone does not request implementation.

## Implement approved scope

> Implement [feature or acceptance criteria] under the approved active release and affected specifications. Verify the approval record, use a dedicated worktree from the authoritative remote integration branch, keep the scope cohesive, test success and failure cases, update documentation, and commit with a verification handoff. Do not integrate or publish unless separately authorized.

## Review a change

> Review [branch or pull request] against [specifications]. Check acceptance coverage, failure behavior, dependency boundaries, privacy, and factual verification claims. Report actionable findings with evidence and remaining gates. Do not silently change approved requirements.

## Resolve a requirement conflict

> Investigate the conflict between [requirement] and [evidence]. Document the options and consequences in a proposed decision. Continue independent work, but stop the conflicting implementation until I choose an option.

## Integrate a reviewed change

> Integrate [branch/commit] into [remote/integration branch] and push it. From the change's worktree, fetch the latest remote branch, rebase, rerun affected verification, and push HEAD directly to the integration branch. If the remote advances, fetch and retry after resolving safely. Never force-push or discard unrelated changes.
