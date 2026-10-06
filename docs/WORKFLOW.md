# Working with the baseline

## Authority and approval

The project index identifies the active release. The release governs cross-feature scope; feature specifications own behavior; core specifications own reusable contracts. AGENTS.md governs procedure. Drafting and research may proceed before approval. Implementation requires both owner approval of the applicable specifications and a request to implement.

An agent may record an explicit owner approval with its scope and reference; it may never infer approval from delivery progress or grant approval itself. If a requirement changes materially, record the conflict and obtain a new owner decision before implementing that change.

## Delivery states

| State | Meaning |
| --- | --- |
| Backlog | Not scheduled for active delivery |
| Blocked | A named dependency or decision prevents progress |
| Ready | Discovery is complete and work can begin once approval and implementation authorization are present |
| In progress | Work is actively underway; this does not imply approval |
| Implemented | Behavior exists, but required verification gates remain |
| Verified | All required acceptance and release gates have evidence |

Track `Approval: Draft | Approved` separately. Explain blockers and outstanding checks instead of overstating completion.

## Isolate a change

Before Git exists, initial steering can be written directly. For an initialized project with an integration branch, inspect the repository status, remotes, default branch, and existing worktrees. Confirm which branch is authoritative. Fetch that remote branch, then create a dedicated worktree and focused agent branch from its current remote-tracking reference.

For example, only after confirming that this project's remote is `origin` and its integration branch is `main`:

```sh
git fetch origin main
git worktree add -b codex/feature-topic ../project-feature-topic origin/main
```

Perform edits, checks, and commits in that worktree. Do not use another change's branch. Keep the owner checkout intact. Fetch again before handoff and rebase when needed for clean integration; rerun affected checks. Stop if resolving a conflict would require discarding user work or changing approved behavior.

Commit completed work for review. Publishing branches, creating pull requests, integrating, or deleting worktrees requires authorization covering that action. When integration and push are explicitly requested, perform them from the change worktree and push its HEAD directly to the confirmed integration branch. Never force-push the integration branch.

## Discovery and evidence

Use the smallest specification set that describes the work. Promote backlog items into feature directories only when needed. Introduce core contracts for concrete consumers, keeping product policy inside features. Use research and decision templates when uncertainty is consequential; avoid paperwork for routine implementation choices within approved scope.

## Verify and hand off

Assign stable acceptance identifiers such as `AC-1`. Map tests and manual checks to those identifiers and the release success scenarios. Record actual environment and results. Check failure paths, accessibility when applicable, and affected consumers of changed core contracts. Run the relevant available lint, type, test, and build commands selected by the project.

Keep authoritative documentation accurate in the same change. Use the handoff template for review evidence. A missing device or credential is a remaining gate, not a passing check. Do not mark delivery Verified while required checks remain.
