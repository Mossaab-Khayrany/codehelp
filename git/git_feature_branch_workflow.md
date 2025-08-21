# Git Feature Branch Workflow (Multi-Dev Safe)

This is a quick reference for working on a feature branch with multiple developers.

---

## 1. Check your remote

```bash
git remote -v
```

- Default remote is usually `origin`.
- If your remote has a different name, replace `origin` with that name in the commands below.

---

## 2. Save your local changes

```bash
git status
```

- If you have uncommitted changes, commit them:

```bash
git add .
git commit -m "Your commit message"
```

---

## 3. Sync with the remote feature branch

```bash
git pull origin feature/inscriptions-stage
```

- If no conflicts, Git merges automatically.
- If conflicts occur:

```bash
# Fix the conflicted files
git add <conflicted-files>
git commit
```

Optional: check what’s new on remote before pulling:

```bash
git fetch origin
# Shows commits on remote that you don't have locally
git log HEAD..origin/feature/inscriptions-stage --oneline
```

---

## 4. Push your changes

```bash
git push origin feature/inscriptions-stage
```

---

## 5. Optional: Safer Workflow (Recommended for multi-dev)

1. Create a local sub-branch off the feature branch:

```bash
git checkout -b my-work feature/inscriptions-stage
```

2. Work on your sub-branch and commit regularly.
3. Pull updates from the main feature branch before merging:

```bash
git checkout feature/inscriptions-stage
git pull origin feature/inscriptions-stage
git checkout my-work
git rebase feature/inscriptions-stage
```

4. Push your sub-branch and create a PR/MR to merge into the feature branch.

This avoids stepping on each other’s commits directly on the feature branch.

---

## Key Tips

- Always commit your changes before pulling.
- Always pull before pushing to avoid overwriting others’ work.
- Use sub-branches for personal work if multiple developers collaborate heavily.
- Check your remote name (`git remote -v`) to avoid mistakes.
