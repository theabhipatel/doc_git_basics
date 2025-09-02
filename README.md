# Git & Version Control Deep Dive 🚀

This guide covers **Git fundamentals + advanced workflows**.

---

## 📌 1. Git Basics

### Clone a Repo

```bash
git clone <repo_url>
```

### Check Repo Status

```bash
git status
```

### Stage & Commit Changes

```bash
git add <file>   # stage a file
git add .  # stage all files
git commit -m "message"

---
# Other use cases

git add .                         # stage all tracked + untracked changes in current dir
git add -p                        # interactively stage hunks (choose parts of changes)
git restore --staged file.txt     # unstage file, keep changes in working directory
git commit -m "Add user signup"   # commit with a single-line message
git commit -m "Add signup form" -m "Includes validation & error handling."
                                  # commit with title + detailed description
```

### See Commit History

```bash
git log --oneline
git log --oneline --graph --decorate --all
```

---

## 📌 2. Branching

### Check  Branches

```bash
git branch         # local
git branch -r      # only remote branches
git branch -a      # local + remote
```

### Create & Switch Branch

```bash
git checkout -b feature-branch   # old way
git switch -c feature-branch     # modern way
```

### Switch to Branch

```bash
git checkout main    # old way
git switch main      # modern way
```

### Merge Branch

```bash
git checkout main
git merge feature-branch
```

### Delete Branch

```bash
# 🗑️ Deleting branches
git branch -d feature-x       # delete local branch (safe, refuses if unmerged)
git branch -D feature-x       # force delete local branch (even if unmerged)
git push origin --delete feature-x   # delete remote branch on origin
```

---

## 📌 3. Pull & Push

### Pull Updates

```bash
git pull origin main
```

### Push Changes

```bash
git push origin feature-branch
```

---

## 📌 4. Undo Changes

### Undo Last Commit (keep changes staged)

```bash
git reset --soft HEAD~1
```

### Undo Last Commit (keep changes in working dir)

```bash
git reset --mixed HEAD~1

# default  behaviour is same as --mixed
git reset  HEAD~1
```

### Undo Last Commit (discard changes)

```bash
git reset --hard HEAD~1
```

---

## 📌 5. Rebasing

### Start Rebase

```bash
git checkout feature-branch
git rebase main
```

### Abort Rebase

```bash
git rebase --abort
```

### Continue After Fixing Conflicts

```bash
git add <file>
git rebase --continue
```

---

## 📌 6. Working with Remote

```bash

# 🌍 Remotes
git remote -v                        # list remotes with URLs
git remote add origin <url>          # add a new remote called origin
git remote rename origin upstream   # rename remote from origin → upstream
git remote set-url origin <url>     # change the URL of origin remote

```


---

## 📌 7. Collaboration

### Create a Pull Request (PR)

- **PR (Pull Request)** is used on **GitHub/Bitbucket**.

### Create a Merge Request (MR)

- **MR (Merge Request)** is used on **GitLab** (same as PR, just naming difference).

---

## 📌 8. Stashing

### Save Work Temporarily

```bash
git stash
```

### List Stashes

```bash
git stash list
```

### Apply Last Stash

```bash
git stash apply
```

### Apply Last Stash and remove from stash

```bash
git stash pop
```

### Comparison

```bash
git stash          # save current changes
git stash list     # shows saved stashes
git stash apply    # reapplies changes but stash still in the list
git stash pop      # reapplies changes AND removes the stash
```

---

## 📌 9. Tags & Releases

### Create Tag

```bash
git tag v1.0.0
```

### Push Tags

```bash
git push origin --tags
```

---

## 📌 10. Advanced Tips

- `git cherry-pick <commit>` → Apply a specific commit from another branch.
- `git reflog` → View all HEAD changes (useful for recovery).
- `git bisect` → Debug by binary searching commits.

---

## ✅ Best Practices

- Commit often, but keep commits small & meaningful.
- Always pull before pushing to avoid conflicts.
- Use branches for features, hotfixes, and experiments.
- Write descriptive PR/MR titles and commit messages.

---
