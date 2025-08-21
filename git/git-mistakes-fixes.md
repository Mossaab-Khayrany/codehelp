# Git Troubleshooting: Common Mistakes & Fixes

| Situation / Mistake | Command(s) to Fix | Notes |
|---------------------|-------------------|-------|
| **Committed to the wrong branch** | ```bash
git switch correct-branch
git cherry-pick <bad-commit>
git switch wrong-branch
git reset --hard HEAD~1
``` | Move commit to correct branch and remove from wrong one. |
| **Forgot to create a branch before work** | ```bash
git branch feature/new-feature
git reset --hard origin/main
git switch feature/new-feature
``` | Save work as a new branch, reset main. |
| **Accidentally staged wrong files** | ```bash
git restore --staged <file>
``` | Leaves file changes in working directory. |
| **Accidentally committed sensitive data** | ```bash
git reset --soft HEAD~1   # undo commit
git restore --staged secret.env
``` | For already-pushed commits, use tools like BFG Repo-Cleaner. |
| **Need to undo last commit but keep changes** | ```bash
git reset --soft HEAD~1
``` | Keeps files staged for editing. |
| **Need to undo last commit and discard changes** | ```bash
git reset --hard HEAD~1
``` | ⚠️ Irreversible; only safe locally. |
| **Want to undo a commit safely on shared branch** | ```bash
git revert <commit>
``` | Creates a new commit that undoes previous changes. |
| **Merge conflict** | ```bash
git status     # see conflicts
# edit conflicted files
git add <file>
git commit     # finish merge
``` | Use `git merge --abort` to cancel. |
| **Stuck in a rebase** | ```bash
git rebase --continue   # after fixing
git rebase --abort      # cancel
``` | Resolve conflicts like in merges. |
| **Accidentally deleted a branch** | ```bash
git checkout -b branch-name <commit-hash>
``` | If pushed to remote, fetch and recreate. |
| **Want to rename a branch** | ```bash
git branch -m old-name new-name
git push origin -u new-name
git push origin --delete old-name
``` | Works locally and remotely. |
| **Remote branch deleted, still showing locally** | ```bash
git fetch --prune
``` | Cleans up old remote-tracking branches. |
| **Remove untracked junk files** | ```bash
git clean -fd
``` | Adds `-x` to also remove ignored files (⚠️). |

---

✅ Keep this as a handy reference when things go wrong.
