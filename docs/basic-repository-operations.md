## &#10162; Basic Repository Operations:

It describes about basic Git operation from creating an empty repository to view commit history log.

### &#9780; Overview:
1. [Initialize Repository](#-initialize-repository)
2. [Staging Area](#-staging-area)
3. [Restore](#-restore)
4. [Commit Changes](#-commit-changes)
5. [Check Status](#-check-status)
6. [View Commit Log](#-view-commit-log)
7. [Checkout](#-checkout)

### &#10022; Initialize Repository:

It creates a new Git repository in the current directory with `.git` hidden directory. Which store all information about new repository changes and changes history.

*To initialize an empty git repository:*

```bash
git init
```

*To initialize an empty git repository with initial branch name:*

```bash
git init --initial-branch=main
```

*Short Parameter for initial branch name:*
```bash
git init -b main
```

*Setting Configuration for default branch name:*

```bash
git config --global init.defaultBranch main
```

### &#10022; Staging Area:

It is required to move files on `staging area`, before committing changes. It tell Git which files or changes that want to be included in the next commit.

The staging area acts as a temporary place, Where files moved on it and wrapped as single commit history rather than moving individual files.

*Add specific file:*

```bash
git add filename.extension
```

```bash
git add path/filename.extension
```

*Add multiple files:*

Provide space between files to add into staging area.

```bash
git add file1 path/file2
```

*Add all files with specified extension:*

Add asterisk before the extension. Which tells files that ends with followed text.

```bash
git add *.ext
```

*Add all files to stagging area:*

```bash
git add .
```

```bash
git add -A
```

```bash
git add --all
```

*Add all files from a directory:*

```bash
git add directory-name/*
```

### &#10022; Restore:

**Unstage the specific changes:**

To unstages a specific file. It removes the file from the staging area (index), but the working directory remain unchanged.

*Syntax:*

```bash
git restore --staged <file>
``` 

*Example:*

```bash
git restore --staged index.php
```

**Unstage all changes:**

It will remove all files in the staging area (index), but the working directory remains unchanged.

```bash
git restore --staged . 
```

**Discard changes in a specific file:**

It discards and removes any uncommitted changes in working directory for specified files.

```bash
git restore <file>
```

**Discard changes in all files:**

```bash
git restore . 
```

**Restore a file to a specific commit history:**

It bring the specified file state on the specified commit history. 

```bash
git restore --source=<commit_hash> <file> 
```

**Restore all files to a specific commit:**

```bash
git restore --source=<commit_hash> . 
```

**Restore staged changes to the working directory:**

It will bring files from staged area to working tree.

```bash
git restore --staged --worktree .
```

### &#10022; Commit Changes:

A commit is a snapshot or history of file changes in the project at a specific point in time. 

When commit a changes, It required a descriptive message that explaining what about the changes.

This will preserve log generate hash for all changes made on files. And it is helpful to review specific commit in later or switch between commits by hash.

*commit changes:*

This will open default code/text editor or inline terminal to describe commit message.

```bash
git commit
```

*commit changes with inline message:*

```bash
git commit -m 'descriptive message'
```

### &#10022; Check Status:

It helps to check the current state of the working directory. It shows status of modified, staged, tracked and untracked files changes in different area.

```bash
git status
```

### &#10022; View Commit Log:

It helps to see the history of all commits made in the current repository with details of author, date, hash and commit message. This helps to track the project evolution.

*Complete Log Information:*

```bash
git log
```

*Log in one line:*

```bash
git log --oneline
```

*Formatted one line Log:*

```bash
git log --pretty=format:'%h %s'
```

*Check commits minimal Log with count:*

```bash
git shortlog
```

*Check commits count by user:*

```bash
git shortlog -s 
```

### &#10022; Checkout:

Git give possibilities of move to specific commit history by checkout command. It requires commit hash or tag name to move to that reference.

*Syntax:*

```bash
git checkout <commit_hash>
```

```bash
git checkout <tag_name>
```

---
[&#8682; To Top](#-basic-repository-operations)

[&#10094; Previous Topic](./introduction.md) &emsp; [Next Topic &#10095;](./branch-operations.md)

[&#8962; Goto Home Page](../README.md)