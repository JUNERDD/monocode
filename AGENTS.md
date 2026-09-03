# Repository Constraints

This checkout is a **fork-based workflow**. Read-only upstream and writable fork:

- `origin` → `https://github.com/hardbeat920/monocode.git` (**upstream, read-only**).
  Used only for `fetch` / syncing upstream code. NEVER push here.
- `junerdd` → `https://github.com/JUNERDD/monocode.git` (**own fork, writable**).
  All pushes go here.

## Hard Rules

1. **NEVER push to `origin`.** Any `git push origin ...` will fail (403) at best
   and risks polluting upstream at worst. Always push explicitly:
   `git push junerdd <branch>`.
2. **NEVER open a PR against the upstream repository**
   (`hardbeat920/monocode`). No merge / PR to the main repo, period.
3. Before any push, verify the target with `git remote -v` and
   `git branch -vv` (the current branch must track `junerdd/...`).
4. Do NOT use repo aliases that default to `origin`:
   `push1`, `pull1`, `hew-remote` (deletes remote refs on `origin`).
   `put` (bare `git push`) is only safe when the branch tracks `junerdd/*`.
