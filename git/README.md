# Git Aliases Reference

## 💾 Commits

| Alias | Usage | Description |
|-------|-------|-------------|
| `cap` | `git cap "fix login bug"` | Add all files, commit with message, and push in one command |
| `undo` | `git undo` | Undo last commit, keep changes staged |
| `amend` | `git amend` | Add staged changes to last commit without editing message |
| `amendm` | `git amendm` | Add staged changes to last commit and edit the message |

## 📤 Push

| Alias | Usage | Description |
|-------|-------|-------------|
| `pf` | `git pf` | Force push current branch to origin |

## 🌿 Branches

| Alias | Usage | Description |
|-------|-------|-------------|
| `new` | `git new feature/auth` | Create and switch to a new branch |
| `branches` | `git branches` | List all local branches with last commit info |
| `wipe` | `git wipe` | Delete ALL local branches except current (force) |
| `gone` | `git gone` | Delete local branches that no longer exist on remote |

## 🔍 Diff

| Alias | Usage | Description |
|-------|-------|-------------|
| `ds` | `git ds` | Show staged changes not yet committed |
| `dm` | `git dm` | Show all changes between current branch and main |

## 📜 Logs

| Alias | Usage | Description |
|-------|-------|-------------|
| `gr` | `git gr` | Colored graph log of current branch with relative dates |
| `grall` | `git grall` | Colored graph log of ALL branches |
| `gralt` | `git gralt` | Graph log with absolute ISO dates and author |
| `last` | `git last` | Last commit with changed files and stats |
| `today` | `git today` | Your commits since midnight (one-line format) |

## 🔎 Search

| Alias | Usage | Description |
|-------|-------|-------------|
| `find-merge` | `git find-merge <commit> [branch]` | Find merge commit that brought a commit into a branch |
| `show-merge` | `git show-merge <commit> [branch]` | Show that merge commit |

## 📦 Stash

| Alias | Usage | Description |
|-------|-------|-------------|
| `ss` | `git ss "WIP: auth"` | Save current changes to stash with description |
| `sl` | `git sl` | List all stashed changes |
| `sp` | `git sp` | Apply and remove the most recent stash |
| `sd` | `git sd` | Drop the most recent stash without applying |

## 🔄 Synchronization

| Alias | Usage | Description |
|-------|-------|-------------|
| `sync` | `git sync` | Fetch from origin and rebase current branch on top |


 ## 🌳 Worktrees
 
 New worktrees are created next to the main repo as `<repo>-<branch>` (slashes in the branch name become dashes), e.g. `~/code/app` + `feature/auth` → `~/code/app-feature-auth`. All aliases take a **branch name**, not a path.
 
 | Alias | Usage | Description |
 |-------|-------|-------------|
 | `wtl` | `git wtl` | List all worktrees |
 | `wts` | `git wts` | Short status of every worktree |
 | `wtp` | `git wtp [branch]` | Print path of the worktree for a branch (no argument = main worktree) |
 | `wta` | `git wta feature/auth [base]` | Add a worktree for a branch; creates the branch (from `base` or HEAD) if it does not exist, tracks `origin/<branch>` if it does |
 | `wtsend` | `git wtsend feature/auth` | Move uncommitted changes (including untracked files) from the current worktree to the worktree of a branch |
 | `wtc` | `git wtc feature/auth [base]` | Create a worktree and carry current uncommitted changes into it (`wta` + `wtsend`) |
 | `wtmv` | `git wtmv feature/auth ../new-dir` | Move a worktree directory to a new location |
 | `wtrm` | `git wtrm feature/auth [--force]` | Remove the worktree of a branch (keeps the branch) |
 | `wtrmb` | `git wtrmb feature/auth [--force]` | Remove the worktree and delete its branch (safe `-d`) |
 | `wtpr` | `git wtpr` | Prune records of worktrees whose directories were deleted manually |
 
 A git alias cannot change the directory of your shell, so switching is done with `cd "$(git wtp feature/auth)"`. To make it a one-word command, add this to `~/.bashrc` / `~/.zshrc`:
 
 ```sh
 # wt            -> cd to the main worktree
 # wt <branch>   -> cd to the worktree of <branch>
 wt() { cd "$(git wtp "$1")" || return; }
 ```

## ⚙️ Utilities

| Alias | Usage | Description |
|-------|-------|-------------|
| `aliases` | `git aliases` | Show all configured git aliases |
