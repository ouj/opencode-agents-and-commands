---
description: Create or update a GitHub pull request
agent: build
model: opencode/big-pickle
---

- Determine the current branch; if the branch is `main`, ask for a new branch name and create it before proceeding.
- Fetch `origin/main` and check whether the branch is behind; if it is behind, ask whether to rebase onto `origin/main` before continuing.
- Base the PR title and description on the diff between the branch and `origin/main`.
- Check for an existing PR for the current branch using `gh pr view` or `gh pr list`.
- If no PR exists, create one targeting `origin/main`; if a PR exists, update its title and body to match the latest diff.
- Ensure the branch is pushed to the remote; set upstream with `-u` if needed.
- Return the PR URL.
