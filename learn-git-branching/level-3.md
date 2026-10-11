# Learn Git Branching — Level 3 Notes


## Topics Completed 

1. **Moving Work Around**
2. **Cherry-pick**
3. **Interactive Rebase**
4. **Staging Changes in Git**
5. **Unstaging Changes in Git**
6. **Restoring Changes with `git restore`**


## 1. Important Git Concepts Learned

### 1. Moving Work Around
**Purpose:** Helps you understand how commits can be moved or applied between different branches.

- Git branches point to commits.
- You can move between branches to work on different features.
- Git provides commands to apply selected commits to another branch.

### 2. Cherry-pick (`git cherry-pick`)
**Purpose:** Applies the changes from a specific commit to your current branch.

```bash
git cherry-pick <commit-hash>
```

- Applies the changes introduced by the selected commit.
- Creates a new commit on the current branch.
- Useful when you want one particular change without merging an entire branch.
- The new commit normally has a different commit hash from the original.

### 3. Interactive Rebase (`git rebase -i`)
**Purpose:** Allows you to edit, reorder, combine, or remove commits during a rebase.

```bash
git rebase -i HEAD~3
```

- Opens an interactive list of recent commits.
- `pick` keeps a commit as it is.
- `reword` lets you change a commit message.
- `squash` combines a commit with the previous commit.
- `drop` removes a commit from the rebased history.
- Useful for cleaning up local commit history before sharing it.

**Important:** Interactive rebase can rewrite commit history. Be careful when using it on commits that other people already use.

---

## Cherry-pick vs Interactive Rebase

| Cherry-pick | Interactive Rebase |
|---|---|
| Applies selected commit changes to the current branch | Reworks a sequence of commits |
| Creates new commit(s) for the selected changes | Can reorder, combine, edit, or remove commits |
| Useful for selecting specific changes | Useful for organizing commit history |

## What I Learned

- How to apply a specific commit using `git cherry-pick`.
- How to work with commits across branches.
- How interactive rebase works.
- How to edit commit messages and combine commits.
- Why keeping a clear commit history is useful.

### 4. Staging Changes (`git add`)
**Purpose:** Moves changes into the staging area so they can be included in the next commit.

```bash
git add filename
git add .
```

- `git add filename` stages a specific file.
- `git add .` stages changes in the current directory and its subdirectories.
- Staging lets you choose which changes to include in a commit.

### 5. Unstaging Changes (`git restore --staged`)
**Purpose:** Removes changes from the staging area without discarding the changes in your working files.

```bash
git restore --staged filename
```

- Moves the selected file out of the staging area.
- Keeps your file changes in the working directory.
- Useful when you accidentally stage the wrong file.

### 6. Restoring Changes (`git restore`)
**Purpose:** Discards unstaged changes in a file and restores its contents to the last committed version.

```bash
git restore filename
```

- Discards unstaged changes in the selected file.
- Does not create a new commit.
- Use carefully because discarded changes may be difficult to recover.

**Important:** `git restore filename` can discard your unstaged work. Check your changes before running it.

## Staging vs Unstaging vs Restoring

| Command | Purpose |
|---|---|
| `git add filename` | Stages changes |
| `git restore --staged filename` | Unstages changes but keeps your edits |
| `git restore filename` | Discards unstaged edits in the file |

##  Practice Commands

```bash
git status
git add filename
git restore --staged filename
git restore filename
git diff
git diff --staged
```

- `git status` shows staged and unstaged changes.
- `git diff` shows unstaged changes.
- `git diff --staged` shows staged changes.

**Learning Resource:** [Learn Git Branching](https://learngitbranching.js.org/)
