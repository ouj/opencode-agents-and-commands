---
description: Commit changes and push to a remote branch
agent: build
model: openai/gpt-5.2-codex
---

- Create a conventional commit for the current staged changes.
- If there are no staged files, ask users whether they want to stage all changes or select files to stage.
- Do not stage files without user confirmation; only inspect staged changes.
- Handle `main` safely: if the current branch is `main`, ask the user for a new branch name, create the branch, then commit on that branch.
- Never commit or push directly to `origin/main`.
- After committing, push the current branch to the remote; if the branch does not track a remote, set upstream with `-u`.
- Use a proper Conventional Commits message and match the language of recent commit messages.
