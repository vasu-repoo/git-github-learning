# Learn Git Branching — Level 1 **Completed**

**Website:** https://learngitbranching.js.org/

## Topics Completed
1. Introduction to Git Commits
2. Branching in Git
3. Merging in Git
4. Introduction to Rebase

# Learn Git Branching — Level 1 Notes

## 1. Important Git Commands

### 1. `git commit`
**Purpose:** Saves the staged changes as a new commit in the repository's history.

```bash
git add .
git commit -m "Add new feature"
```

- `git add` stages changes.
- `git commit` saves the staged snapshot.
- Each commit has a unique hash.

### 2. `git branch`
**Purpose:** Lists, creates, or manages branches.

```bash
git branch                 # List local branches
git branch feature         # Create a new branch
git branch -d feature      # Delete a merged branch
```

A branch lets you work on changes separately from other development work.

### 3. `git checkout`
**Purpose:** Switches branches or restores files, depending on the command used.

```bash
git checkout main
git checkout -b feature
```

- The first command switches to `main`.
- The second creates `feature` and switches to it.

### 4. `git switch`
**Purpose:** Switches between branches. It is a modern, more focused alternative to `git checkout` for branch operations.

```bash
git switch main
git switch -c feature
```

- `git switch main` switches to `main`.
- `git switch -c feature` creates and switches to `feature`.

### 5. `git merge`
**Purpose:** Combines the changes from one branch into the current branch.

```bash
git switch main
git merge feature
```

This merges `feature` into `main`. You must be on the branch that should receive the changes.

### 6. `git rebase`
**Purpose:** Reapplies commits from your current branch onto another base commit, creating a different commit history.

```bash
git switch feature
git rebase main
```

This reapplies the commits from `feature` on top of `main`.

**Note:** Rebase can change commit hashes. Avoid rebasing shared commits that other people may already depend on unless your team agrees.

---

## 2. Merge vs Rebase

| Git Merge | Git Rebase |
|---|---|
| Combines branch histories | Replays commits onto a new base |
| May create a merge commit | Usually creates a more linear history |
| Preserves existing commits | Rewritten commits get new hashes |

## 3. What I Learned

- Commits save staged changes.
- Branches allow independent development.
- Checkout and switch can change the current branch.
- Merge combines branch changes.
- Rebase reapplies commits onto a new base.

## 4. Practice Commands

```bash
git status
git branch
git switch -c practice
git add .
git commit -m "Practice Git commands"
git switch main
git merge practice
git log --oneline --graph --all
```

**Learning resource:** [Learn Git Branching](https://learngitbranching.js.org/)
