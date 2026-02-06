---
description: Start work from the current synced main head
agent: general
---

- Fetch `origin`.
- Check for uncommitted changes in the current branch. Stash them before switching branches.
- If local `main` does not exist, create it from `origin/main`. Checkout local `main`.
- Sync local `main` to the latest `origin/main`.
- If local `main` has diverged, rebase it onto `origin/main`, then soft reset
  to `origin/main`.
- After local `main` is synced, restore any stashed changes and resolve conflicts.
- Report stash/restore status and confirm local `main` is at the current head
  of `origin/main`.
