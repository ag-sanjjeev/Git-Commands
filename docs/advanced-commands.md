## &#10162; Advanced Commands:

### &#9780; Overview:
1. [Git Blame](#-git-blame)
2. [Git Cherry-Pick](#-git-cherry-pick)
3. [Git Reflog](#-git-reflog)
4. [Git Revert](#-git-revert)
5. [Git Stash](#-git-stash)

### &#10022; Git Blame:

It shows the information about who made changes to each line of a file and when. It is useful for tracking changes made by the author and when it was done. It gives feasibility to track origin of the code.

*Syntax:* 

```bash
git blame <file>
```

### &#10022; Git Cherry-Pick:

It applies and merges the changes from a specific commit to the current branch. It is useful for selectively incorporating changes rather than merging entire branch.

*Syntax:*

```bash
git cherry-pick <commit-hash>
```

**Flags:**

- To avoid auto merge use flag `-n` or `--no-commit`. This will stage the changes but not create a commit. This allows to edit the changes before committing.
- To append attribute to commit message use flag `-x` when cherry-picking a merge commit.
- To specify the strategy of merge use flag `--strategy <strategy>`.

### &#10022; Git Reflog:

It shows a log of all commits made to the repository references such as branches, HEAD and actions even if those changes haven't been committed yet. It useful to see and recover the lost commits or understand workflow of the project.

*Example:*

```bash
git reflog
```

**Flags:**

- Show dates rather than HEAD count, use flag `--relative-date`.
- Show abbreviated commit hashes, use flag `--abbrev-commit`.

### &#10022; Git Revert:

It creates a new commit for undo the changes introduced by checking out to a previous commit.  This maintains and preserves the history of the original commit, unlike `git reset`.

*Syntax:* 

```bash
git revert <commit-hash>
```

**Flags:**

- Stage the reverted changes but not create a commit, use flags `-n` or `--no-commit`

### &#10022; Git Stash:

It temporarily shelves changes that have made to the working directory and staging area. It allows to switch between a different branch or commit or work without committing the unfinished changes.

**Stash Changes:**

*Example:*

```bash
git stash
```

**Stash Changes with message:**

Stashes changes and includes untracked files with message.

```bash
git stash push -u -m "stash message"
```

**Show Stash List:**

Lists your stashed changes.

*Example:*

```bash
git stash list
```

**Apply Recent Stash:**

It applies the most recent stashed changes.

*Example:*

```bash
git stash apply
```

**Pop Stash:**

It applies the most recent stashed changes and removes the stash entry from stash list.

*Example:*

```bash
git stash pop
```

**Delete a Stash:**

It removes a specific stash entry from stash list.

*Example:*

```bash
git stash drop <stash-id>
```

**Clear All Stash:**

It clear and removes all stashed entries from stash list.

*Example:*

```bash
git stash clear
```

---
[&#8682; To Top](#-advanced-commands)

[&#10094; Previous Topic](./git-subtrees.md) 

[&#8962; Goto Home Page](../README.md)