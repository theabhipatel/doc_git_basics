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
```

### See Commit History

```bash
git log --oneline
git log --oneline --graph --decorate --all
```

---

## 📌 2. Branching

### Check local Branches

```bash
git branch
```

### Create & Switch Branch

```bash
git checkout -b feature-branch
```

### Switch to Branch

```bash
git checkout main
```

### Merge Branch

```bash
git checkout main
git merge feature-branch
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

## 📌 6. Collaboration

### Create a Pull Request (PR)

- **PR (Pull Request)** is used on **GitHub/Bitbucket**.

### Create a Merge Request (MR)

- **MR (Merge Request)** is used on **GitLab** (same as PR, just naming difference).

---

## 📌 7. Stashing

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

## 📌 8. Tags & Releases

### Create Tag

```bash
git tag v1.0.0
```

### Push Tags

```bash
git push origin --tags
```

---

## 📌 9. Advanced Tips

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
