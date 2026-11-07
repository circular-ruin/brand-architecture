# brand-architecture

## Cross-product docs

Shared engineering and ops docs for Circular Ruin (signing, release pipelines,
CI, versioning, private npm package auth, secrets inventory, frontend
conventions, preset format) live in the private repo
[`circular-ruin/docs`](https://github.com/circular-ruin/docs). Keep a local
copy and use it.

**At the start of every session, before other work:**

1. Find the main clone of this repo, even from a submodule or worktree. Run
   `git rev-parse --show-superproject-working-tree`. If it prints nothing, run
   `git rev-parse --show-toplevel` instead. Then run
   `git -C <that path> rev-parse --path-format=absolute --git-common-dir`. The
   parent of the `.git` directory it prints is the main clone.
2. The docs belong in a folder named `docs` beside the main clone, in the same
   parent directory (for example `~/projects/torus` → `~/projects/docs`).
3. If that folder doesn't exist, clone it with
   `gh repo clone circular-ruin/docs <docs path>`. If it exists, update it with
   `git -C <docs path> pull --ff-only`.
4. Read `<docs path>/README.md`. It indexes every doc.

If the clone or pull fails (no `gh` auth, no network, local changes in the
docs folder), tell the user, then carry on with the copy you have. Without any
local copy, read single files with
`gh api repos/circular-ruin/docs/contents/<file> -H "Accept: application/vnd.github.raw"`.

**While working:**

- Before changing or advising on anything the README index covers, read that
  doc first.
- Links to `https://github.com/circular-ruin/docs/blob/main/<file>` anywhere in
  this repo refer to `<docs path>/<file>`.
- The docs are the source of truth for cross-repo conventions. If a doc and
  this repo's code disagree, tell the user instead of quietly following either.
- Don't edit the docs as a side effect of work here. If a doc is wrong or
  missing something, tell the user. Fixes go through a PR to
  `circular-ruin/docs`.
