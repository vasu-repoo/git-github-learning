# Learn Git Branching — Level 4 Notes

## Topics Completed — Level 4

1. **Git Describe**
2. **Juggling Commits**
3. **Git Tags**

## 1. Important Git Concepts Learned

### 1. Git Describe (`git describe`)
**Purpose:** Helps identify a commit using a nearby tag and additional commit information.

```bash
git describe
git describe <commit-hash>
```

- Identifies a commit relative to the nearest reachable tag.
- The output commonly includes the tag name, number of commits since the tag, and an abbreviated commit hash.
- Useful for understanding where a commit is located in relation to a tagged release.

### 2. Juggling Commits
**Purpose:** Helps move, rearrange, and manage commits while maintaining a useful Git history.

- Git allows you to move between branches and commits.
- You can use tools such as cherry-pick and rebase to rearrange changes.
- Understanding commit history helps you apply changes to the correct branch.
- Always inspect your history before rewriting commits.

**Useful commands:**

```bash
git cherry-pick <commit-hash>
git rebase -i HEAD~3
```

### 3. Git Tags (`git tag`)
**Purpose:** Assigns a recognizable name to a specific commit, often to mark a software release.

```bash
git tag
git tag v1 C1
git show v1
git tag -d v1.0
```

- `git tag` lists existing tags.
- `git tag v1.0` creates a lightweight tag at the current commit.
- `git show v1.0` displays information about the tagged commit.
- `git tag -d v1.0` deletes the local tag.

**Sharing tags with GitHub:**

```bash
git push origin v1.0
git push origin --tags
```

- `git push origin v1.0` pushes one specific tag.
- `git push origin --tags` pushes local tags that have not been pushed to that remote.

## 2. Git Describe vs Git Tags

| Git Describe | Git Tags |
|---|---|
| Describes a commit relative to a reachable tag | Names a specific commit |
| Helps identify a commit's position in history | Often marks releases such as `v1.0` |
| Produces descriptive commit information | Creates and manages labels for commits |

## 3. What I Learned

- How `git describe` identifies commits relative to tags.
- How to manage and rearrange commits.
- How Git tags mark important commits.
- How to create, inspect, delete, and push tags.
- Why tags are useful for versioning and releases.

## 4. Practice Commands And All The Problems Present there

```bash
git describe
git tag
git tag v1 C1
git show v1.0
git push origin v1.0
```

## 5. Practice Question

**Question:** What is the difference between a Git tag and a Git branch?

**Answer:** A tag normally marks a specific commit, such as a release, while a branch is a movable reference that advances as new commits are made.

**Learning Resource:** [Learn Git Branching](https://learngitbranching.js.org/)
