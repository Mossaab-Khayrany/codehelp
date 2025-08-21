# Git Quick Reference (Web Dev & Data Science)

> Focused on daily workflows: branching, merging, fixing mistakes, syncing with remote.

---

## Start a new project
```bash
git init
git add .
git commit -m "chore: initial commit"
git branch -M main
git remote add origin <url>
git push -u origin main
```

## Clone an existing repo
```bash
git clone <url>
cd <repo>
```

---

## Branching
```bash
git switch -c feature/new-feature   # create & switch
git switch main                     # move back to main
git branch                          # list branches
git branch -d <branch>              # delete merged branch
git branch -m old new               # rename branch
```

---

## Sync with remote
```bash
git fetch origin
git pull            # merge updates from remote
git pull --rebase   # rebase updates (cleaner history)
git push            # push changes
```

---

## Merging & Rebasing
```bash
git switch main
git merge feature/new-feature       # merge into main

# or, from feature branch
git rebase main                     # rebase on top of main
git rebase --continue               # after resolving conflicts
git rebase --abort                  # cancel
```

---

## Staging & Committing
```bash
git status
git add <file>                      # stage specific file
git add -A                          # stage all changes
git commit -m "feat: add login form"
git commit --amend                  # edit last commit
```

---

## Fixing mistakes
```bash
git restore <file>                  # discard changes
git restore --staged <file>         # unstage file

git reset --soft HEAD~1             # undo last commit, keep changes staged
git reset --hard HEAD~1             # undo last commit, discard changes (⚠️ dangerous)

git revert <commit>                 # safely undo a commit with new commit
```

---

## Stash (temporary save)
```bash
git stash push -m "wip: analysis"
git stash list
git stash pop
```

---

## Logs & Diffs
```bash
git log --oneline --graph --decorate --all
git diff                # unstaged changes
git diff --staged       # staged changes
```

---

## Tags (releases)
```bash
git tag -a v1.0.0 -m "release v1.0.0"
git push origin v1.0.0
```

---

## Aliases (optional)
```bash
git config --global alias.st "status -sb"
git config --global alias.lg "log --oneline --graph --decorate --all"
git config --global alias.co switch
```

---

✅ This covers **95% of daily Git use** for web developers and data analysts/scientists.
