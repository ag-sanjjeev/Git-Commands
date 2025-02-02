## &#10162; Git Reset:

It is a command that might allows to move the branch pointer or the staging area back to the previous commit. There are three types of reset commands in git.

Use with **Caution!**

Use git reset commands with caution. To avoid accidentally losing work, use it carefully. Prefer to double-check before about to reset and executing the command.

### &#9780; Overview:
1. [Hard Reset](#-hard-reset)
2. [Soft Reset](#-soft-reset)
3. [Mixed Resets](#-mixed-resets)
4. [Resets with Merge](#-resets-with-merge)
5. [Resets with Keep](#-resets-with-keep)
6. [Allowed Commit References](#-allowed-commit-references)

### &#10022; Hard Reset:

It resets the branch pointer, the staging area (index) and the working directory to the specified commit history. It will reset and move to the specific commit history. Therefore, any changes in the working directory will be ignored and lost. Use with **Caution!**.

*Syntax:*

```bash
git reset --hard <commit-hash>
```

*Example:*

```bash
git reset --hard 6c83140
```

### &#10022; Soft Reset:

It resets only the branch pointer to the specified commit history. It will leave the staging area (index) and the working directory. It will move to specified commit history and It wouldn't affect the stagging area as well as working directory.

*Syntax:*

```bash
git reset --soft <commit-hash>  
```

*Example:*

```bash
git reset --soft 6c83140  
```

### &#10022; Mixed Resets:

This is the default mode of reset command. If the mode flag is not specified as `--hard`, `--soft` or `--merge`, Then it will be treated as `--mixed`. It will resets and move the branch pointer and the staging area (index) to the specified commit. But it leaves the working directory. It wouldn't affect the working directory.

**With Flag:**

*Syntax:*

```bash
git reset --mixed <commit-hash>
```

*Example:*

```bash
git reset --mixed 6c83140
```

**Without Flag:**

*Syntax:*

```bash
git reset <commit-hash>
```

*Example:*

```bash
git reset 6c83140
```

### &#10022; Resets with Merge:

It resets the branch pointer and staging area like `--mixed` reset. Additionally, it tries to restore the working tree as a clean state by checking out the paths affected by the reset. If the operation of cleaning working tree is not possible, then it will abort the reset.

*Syntax:*

```bash
git reset --merge <commit-hash>
```

*Example:*

```bash
git reset --merge 6c83140
```

### &#10022; Resets with Keep:

It resets the branch pointer and staging area like `--mixed` reset. But when moving to the HEAD, It resets the staging area (index) entries to be the same as the HEAD. And it wouldn't affect the working directory.

*Syntax:*

```bash
git reset --keep <commit-hash>
```

*Example:*

```bash
git reset --keep 6c83140
```

### &#10022; Allowed Commit References:

Git can accepts following references:

- A full commit hash (e.g., `6c83140c5317bdd62ff382d51a41396f1ec9e37d`).
- A minimal commit hash (e.g., `6c83140`).
- A branch name (e.g., `main`). This will be useful to move the current branch to the tip of the specified branch.
- A tag name (That is identified as name and that will reference to the specific commit).
- A relative references (e.g., `HEAD^`, `HEAD~2`, `HEAD@{1 day ago}`).


**Undo the last commit (and keep changes in the working directory):**

```bash
git reset --soft HEAD^
```

```bash
git reset --soft HEAD~1
```

**Undo the last two commits (and keep changes in the working directory):**

```bash
git reset --soft HEAD~2
```

**Reset to a specific commit (and lose all changes since then):**

```bash
git reset --hard <commit-hash>
```

**Unstage a file (remove it from the staging area):**

```bash
git reset HEAD <file>
```

---
[&#8682; To Top](#-git-reset)

[&#10094; Previous Topic](./git-objects.md) &emsp; [Next Topic &#10095;](./git-submodules.md)

[&#8962; Goto Home Page](../README.md)