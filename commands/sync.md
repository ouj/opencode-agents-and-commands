---
description: Sync and rebase current branch onto origin/main
agent: general
---

- Sync the current branch with the latest `origin/main`.
- Never run rebase on `main`; if currently on `main`, create a new branch first.
- Fetch remote updates.
- Rebase the current branch onto `origin/main`.
- If conflicts occur, resolve all conflicts, stage resolved files, and continue
  the rebase until complete.
- If any conflict cannot be resolved safely, stop and report the exact blockers.
- Force push the current branch with `--force-with-lease`.
- Report rebase result, conflicts handled, and push outcome.
