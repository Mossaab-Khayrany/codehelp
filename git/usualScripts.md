# usual git commands

### clone repo

```bash
git clone git@github.com:OEC-IDF/litiges.git
```

### check all branches local and remote

```bash
git branch -a
```

### reset local repo and discard changes

```bash
git reset --hard origin/30thDev
```

Resets your local branch (index + working tree) to exactly the commit that is on the remote.
Any commits you made locally after the push are discarded.

```bash
git clean -fd
```

Removes any untracked files or folders that were created after your push.

```bash
git clean -fdx
```

remove ignored files you added (e.g., generated files)
