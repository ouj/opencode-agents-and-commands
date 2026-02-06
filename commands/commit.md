---
description: Create a git commit based on current changes
agent: general
---

- Create a commit for the current changes.
- Never commit on local `main`.
- If the current branch is `main`, create a new branch before committing.
- Name the new branch to reflect the changes.
- Do not push and do not open a PR.
- Use a Conventional Commit message based on the staged diff.
- Auto-stage modified tracked files only.
- Do not stage deleted or untracked files without confirmation.
