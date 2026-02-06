---
description: Commit changes and push to a remote branch
agent: general
---

- Create a commit and push the current branch to the remote; do not open a PR.
- Create a commit for the current changes.
- Never commit on local `main`.
- If the current branch is `main`, create a new branch before committing.
- Name the new branch to reflect the changes.
- Use a Conventional Commit message based on the staged diff.
- Auto-stage modified tracked files only.
- Do not stage deleted or untracked files without confirmation.
- Push the current branch to the remote after committing.
- Use `-u` when setting upstream for a new branch.
- If a direct push fails, ask for confirmation before force pushing.
- Do not open a PR.
