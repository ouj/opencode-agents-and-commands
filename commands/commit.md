---
description: Create a git commit based on current changes
agent: build
model: opencode/big-pickle
---

- Create a conventional commit for the current staged changes.
- If there are no staged files, ask users whether they want to stage all changes or select files to stage.
- Do not stage files without user confirmation; only inspect staged changes.
- Use a proper Conventional Commits message and match the language of recent commit messages.
