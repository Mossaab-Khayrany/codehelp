# Git Workflow: From Cloning to Safe Feature Branch Push

This guide shows the exact commands sequence to go from **cloning** a repository → **creating a feature branch** → **removing local `main`** → **pushing your new branch safely**.

---

## 1. Clone the repository
```bash
git clone <repo-url>
cd <repo-folder>
```

- This copies the entire repo locally.  
- You will be checked out on the default branch (usually `main`).

---

## 2. Make sure the base branch is up to date
```bash
git checkout main
git pull origin main
```

- Ensures your local `main` matches the remote production branch.

---

## 3. Create a feature branch from `main`
```bash
git checkout -b feature/batiment-data-correction
```

- Creates a new local branch starting from `main`.  
- Switches to the new branch immediately.

---

## 4. (Optional) Delete local `main`
```bash
git branch -d main        # safe delete
# or, if Git warns about unmerged changes:
git branch -D main        # force delete
```

- This deletes only the **local** `main`.  
- The remote `main` (`origin/main`) is unaffected.

---

## 5. Make changes on your feature branch
```bash
# edit files...
git add .
git commit -m "Fix batiment data"
```

- Work is isolated in `feature/batiment-data-correction`.  
- `main` remains untouched.

---

## 6. Push your feature branch to GitHub
```bash
git push -u origin feature/batiment-data-correction
```

- Creates a new branch on GitHub.  
- `-u` sets it as the tracking branch for future `git push`/`git pull`.

---

## 7. Open a Pull Request
- On GitHub, select your branch (`feature/batiment-data-correction`).  
- Click **Compare & Pull Request**.  
- Choose the base branch (`main` or `dev`) for review and merging.

---

✅ **Result:**  
- Your feature branch is independent of production (`main`).  
- You safely push changes for review.  
- Production is updated only after PR approval and merge.
