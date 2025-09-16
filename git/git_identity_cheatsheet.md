# Git Identity & Re-Commit Cheatsheet

A quick reference for checking your Git user identity and fixing commits if you used the wrong email or name.

---

## 🔍 Check Git User Identity

### Check global identity
```bash
git config --global user.name
git config --global user.email
```

### Check local (repo-specific) identity
```bash
git config --local user.name
git config --local user.email
```

### See effective identity Git will use
```bash
git config user.name
git config user.email
```

---

## ✏️ Set/Update Identity

### Globally
```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### Locally (only for this repo)
```bash
git config user.name "Your Name"
git config user.email "your@email.com"
```

---

## 🔄 Fix Last Commit (Wrong Identity)

If you committed with the wrong name/email but **haven’t pushed yet**:
```bash
git commit --amend --reset-author --no-edit
```

If you already pushed, rewrite and force push:
```bash
git commit --amend --reset-author --no-edit
git push --force
```

---

## 🧹 Fix Multiple Past Commits (Advanced)

Rewrite history (changes *all* commits):
```bash
git filter-branch --commit-filter '
  if [ "$GIT_COMMITTER_EMAIL" = "wrong@email.com" ];
  then
    GIT_COMMITTER_NAME="Correct Name";
    GIT_COMMITTER_EMAIL="correct@email.com";
    GIT_AUTHOR_NAME="$GIT_COMMITTER_NAME";
    GIT_AUTHOR_EMAIL="$GIT_COMMITTER_EMAIL";
    git commit-tree "$@";
  else
    git commit-tree "$@";
  fi' HEAD
```

Then force push:
```bash
git push --force --tags origin 'refs/heads/*'
```

*(⚠️ Be careful: history rewrite affects collaborators!)*

---
