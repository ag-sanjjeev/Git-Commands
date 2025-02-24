## &#10162; Branch Operations:

It describes about basic Git operation from creating an empty repository to view commit history log.

### &#9780; Overview:
1. [Create Branch](#-create-branch)
2. [List Branches](#-list-branches)
3. [Switch Branch](#-switch-branch)
4. [Move or Rename Branch](#-move-or-rename-branch)
5. [Branching Strategies](#-branching-strategies)
	- [Feature Branches](#-feature-branches)
	- [Gitflow](#-gitflow)
6. [Merge Branch](#-merge-branch)
7. [Merge Conflicts](#-merge-conflicts)
8. [Rebase](#-rebase)
9. [Undo Rebase](#-undo-rebase)
10. [Delete a Branch](#-delete-a-branch)
11. [Create an Empty Branch](#-create-an-empty-branch)

### &#10022; Create Branch:

New branch in a git repository, allows to work on copy of the current branch as an isolation.

Create a new branch from root of current branch by git branch command:

*Syntax:*

```bash
git branch <branch_name>
```

*Example:*

```bash
git branch feature/new-login
```

### &#10022; List Branches:

List all local branches in the repository. This will tells current checked-out branch will be marked with an asterisk (\*).

*Example:*

```bash
git branch 
```

*Alternative:*

```bash
git branch --list
```

**To list branches with latest commit on each branch:**

```bash
git branch -v
```

**To list all local and remote branches:**

This command will display all local branches and all remote origin branches prefixed with `remotes/<origin-name>/`.

```bash
git branch -a 
```

**To list only remote branches:**

```bash
git branch -r 
```

### &#10022; Switch Branch:

Switches current working branch to a different branch.

*Syntax:*

```bash
git checkout <branch_name>
```

*Example:*

```bash
git checkout feature/new-login
```

**Create and Switch Branch:**

*Syntax:*

```bash
git checkout -b <branch_name>
```

*Example:*

```bash
git checkout -b feature/new-login
```

### &#10022; Move or Rename Branch:

To rename the current branch into specified name, use `branch` command with `-M` flag.

*Syntax:*

```bash
git branch -M <new-branch-name>
``` 

*Example:*

Renames the current branch to `master`

```bash
git branch -M master
```

### &#10022; Branching Strategies:

It is important to follow or use strategies when working with different branch in a git repository. It has different approaches to using branches.

1. [Feature Branches](#-feature-branches)
2. [Gitflow](#-gitflow)

### &#10022; Feature Branches:

It is useful for handling various and more features in a git repository. It is recommended to use separate new branch for each new features or bug fixes are developed. It allows and encourage parallel development, isolates changes and facilitates code review in later.

*Steps:*

1. Create a new branch from the main branch (e.g., `main`, `master` or `develop`).
2. Work on the `feature/fix` or `feature/<name>` in the new branch.
3. Commit changes regularly.
4. Merge the `feature` branch back into the main branch when it is completed and tested.

### &#10022; Gitflow:

It is similar to feature branch strategy, but overall branch management strategies. It is mostly recommended to used for a more structured and complex branching git repository for managing regular releases.

*List of Key Branches used:*
- `main`: Stable branch for stable release history.
- `develop`: Indicates for ongoing development.
- `feature` branches: For developing specific features.
- `release` branches: For preparing different releases.
- `hotfix` branches: For fixing bugs in production.

### &#10022; Merge Branch:

It integrates/combine the changes made from one branch into another branch.

- First, switch branch to targeted branch before merge.
- Second, use merge command with specified `branch-name` to merge on targeted branch.
- Third, Resolve the conflict if any.
- Fourth, Commit the changes.

*Syntax:*

This merges `<branch-name>` to current targeted branch.

```bash
git merge <branch_name>
```

*Example:*

In this example, consider current branch is `main` branch, `git merge feature/new-login` merges the `feature/new-login` branch into `main`.

```bash
git merge feature/new-login
```

### &#10022; Merge Conflicts:

It occurs when Git cannot automatically integrate/combine changes from two branches. For example, It will occurs when the same lines of code on a file were modified in both branches.

So, it requires to check and edit manually the conflicted files and choose the correct changes. Stage the resolved files and commit changes.

### &#10022; Rebase:

It is similar to git merge command. But it integrates/combine changes from one branch into another branch by rewriting the commit history of the targeted branch. It creates a overall cleaner and more linear commit history.  However, it rewrites history, so it should be used carefully and cautiously, especially in the git repository with shared branches.

- First, switch branch to targeted branch before rebase.
- Second, use rebase command with specified `branch-name` to merge on targeted branch.
- Third, Resolve the conflict if any.
- Fourth, Commit the changes.

*Syntax:*

This merges `<branch-name>` to current targeted branch with rewritten commit history.

```bash
git rebase <branch_name>
```

*Example:*

In this example, consider current branch is `main` branch, `git merge feature/new-login` merges the `feature/new-login` branch into `main`. Also, it rewritten the commit history of `main` branch.

```bash
git rebase feature/new-login
```

**WARNING:** Avoid `rebase` command on public branches. Because, those branches that other developers might be working on.

### &#10022; Undo Rebase:

After rebase on the repository, undo the rebase operation might cause problem with work flow.
So, use with caution.

**Simple Method:**

When do rebase, git saves starting point of the branch to ORIG_HEAD. This command might works, when there is no commits made after rebase. 

```bash
git reset --hard ORIG_HEAD
```

**Another Method:**

First, check `HEAD` count by using `reflog` command to get head count value such as `HEAD@{1}` or `HEAD@{2}` or the value required to be move on.

suppose, the old commit was `HEAD@{2}` before rebase. then the reset command is,

*Use with caution due to flag:hard*

```bash
git reset --hard HEAD@{2}
```

### &#10022; Delete a Branch:

To delete a specific branch from the local repository, which is fully merged to upstream.

*Syntax:*

```bash
git branch -d <branch_name>
```

If the branch has changes with unmerged, then Git will refuse to delete it. To delete a branch by force, that is irrespective of merge status. 

*Syntax:*

```bash
git branch -D <branch_name>
```

This is short form of following command:

```bash
git branch -d -f <branch-name>
```

**Caution:** Deleting a branch by force can lead to data loss.

**Delete Remote Branch:**

*Syntax:*

```bash
git push origin --delete <branch_name>
```

### &#10022; Create an Empty Branch:

To create an empty branch with specific commit without history:

step 1: checkout to branch or commit:

```bash
git checkout <branch_name/hash>
```

step 2: create clean empty branch

```bash
git checkout --orphan <new_branch_name>
```

This will create empty branch with clean working directory. But it has all files and directories as same as available onwards from the last commit that where checked out from. That files and directories are in stagging area.

step 3: commit as a fresh commit

```bash
git commit -m 'Alpha release'
```

---
[&#8682; To Top](#-branch-operations)

[&#10094; Previous Topic](./basic-repository-operations.md) &emsp; [Next Topic &#10095;](./remote-repository.md)

[&#8962; Goto Home Page](../README.md)