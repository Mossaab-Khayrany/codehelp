# How to Safely Move a Feature Branch from Prod to Dev

This is a step-by-step guide to fix a feature branch that was mistakenly created from `prod` instead of `dev`.

---

## 1. Backup your current feature branch

```bash
# Check current branch
git branch --show-current

# Optional: see status
git status

# Commit any uncommitted changes (recommended)
git add -A
git commit -m "WIP: <short description>"

# Create a local backup branch
git branch backup/<feature-branch-name>
```

*Optional:* you can push this backup to remote for extra safety:
```bash
git push origin backup/<feature-branch-name>
```

---

## 2. Switch to dev and update

```bash
# Stash uncommitted changes if needed
git stash push -m "WIP from <feature-branch-name> before branching from dev"

# Checkout dev branch
git checkout dev

# Pull latest changes from remote
git pull origin dev
```

---

## 3. Create a new feature branch from dev

```bash
git checkout -b <feature-branch-name>-from-dev
```

---

## 4. Apply your stashed changes (if any)

```bash
git stash pop
```

Resolve any conflicts if Git reports them.

---

## 5. Commit your work on the new branch

```bash
git add -A
git commit -m "Feature: <short description> (rebased on dev)"
```

---

## 6. Rename the branch (optional)

If the branch name has a typo or you want to match your original naming convention:

```bash
# If the old prod-based branch still exists, delete it locally
git branch -D <feature-branch-name>

# Rename the current branch
git branch -m <feature-branch-name>
```

---

## 7. Push the clean branch to remote

```bash
git push -u origin <feature-branch-name>

# Optional: delete old typo branch from remote if it exists
git push origin --delete <old-typo-branch-name>
```

---

✅ End result: your feature branch is now based on `dev`, all your work is preserved, and the branch is correctly named for collaboration.