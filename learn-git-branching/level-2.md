# Learn Git Branching — Level 2 Notes


## Topics Completed 


1. **Introduction to Git Commits**
2. **Branching in Git**
3. **Merging in Git**
4. **Introduction to Rebase**



## 1. Important Git Concepts Learned

### 1. Detaching HEAD
**Purpose:** Allows you to check out a specific commit instead of following a branch.

```bash
git checkout <commit-hash>
```

- `HEAD` normally points to the current branch.
- In detached HEAD state, `HEAD` points directly to a specific commit.
- Useful for inspecting or testing an older commit without switching a branch.

### 2. Relative References (`^`)
**Purpose:** Allows you to refer to commits relative to the current commit.

```bash
git checkout main^
git checkout HEAD^
```

- `^` refers to the first parent of a commit.
- `HEAD^` means the parent of the current commit.
- `HEAD^^` means two commits before the current commit along the first-parent path.

### 3. Relative References (`~`)
**Purpose:** Moves backward through a commit's first-parent history.

```bash
git checkout HEAD~1
git checkout HEAD~2
```

- `HEAD~1` refers to the first parent.
- `HEAD~2` refers to the first parent's parent.
- Useful for navigating to earlier commits.

### 4. Moving Branches (`git branch -f`)
**Purpose:** Force-moves a branch reference to a specified commit.

```bash
git branch -f main HEAD~2
```

- Moves `main` to the commit two steps behind `HEAD`.
- It does not automatically switch your current branch.
- Use carefully because moving a branch can change which commits it references.

### 5. Reversing Changes with `git reset`
**Purpose:** Moves the current branch reference to an earlier commit and changes the current working state.

```bash
git reset HEAD~1
```

- Moves the current branch back by one commit.
- In the usual mixed-reset mode, the changes from that commit remain in your working directory but become unstaged.
- Primarily used for local history that has not been shared.

### 6. Reversing Changes with `git revert`
**Purpose:** Creates a new commit that reverses the changes introduced by an earlier commit.

```bash
git revert <commit-hash>
```

- Preserves the existing commit history.
- Adds a new commit that undoes the selected commit's changes.
- Often safer for changes that have already been pushed and shared.

---

## 2. Git Reset vs Git Revert

| Git Reset | Git Revert |
|---|---|
| Moves the branch reference backward | Creates a new reversing commit |
| Can rewrite local history | Preserves existing history |
| Commonly used for local commits | Often used for shared commits |

## 3. What I Learned

- How to inspect a specific commit using detached HEAD.
- How to navigate commit history using `^` and `~`.
- How to move a branch using `git branch -f`.
- How `git reset` moves a branch reference backward.
- How `git revert` undoes changes by creating a new commit.

## 4. Practice Commands

```bash
git checkout HEAD~1
git checkout main
git branch -f main HEAD~2
git reset HEAD~1
git revert <commit-hash>
```

## 5. Practice Question
<img width="1151" height="667" alt="Screenshot (98)" src="https://github.com/user-attachments/assets/84f167b6-b95b-4401-b4ea-589ddbac339a" />

**Learning Resource:** [Learn Git Branching](https://learngitbranching.js.org/)

