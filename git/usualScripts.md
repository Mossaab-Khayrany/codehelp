# usual git commands

### clone repo

```bash
git clone git@github.com:OEC-IDF/litiges.git
```

### check all branches local and remote

```bash
git branch -a
```

### check all branches local and remote

```bash
git fetch origin
git reset --hard origin/$(git rev-parse --abbrev-ref HEAD)
```

This discards all local changes (staged, unstaged, untracked, ignored).
