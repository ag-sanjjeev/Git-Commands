## &#10162; Remote Repository:

A remote repository is another repository which is running on different location or server. It is a copy version of local project or local repository. It allows and give feasibilities to back up the project code, collaborate with others and deploy the project.

### &#9780; Overview:
1. [Add Remote](#-add-remote)
2. [Show Remote](#-show-remote)
3. [Manipulate Remote](#-manipulate-remote)
4. [Fetch Remote](#-fetch-remote)
5. [Pull Remote](#-pull-remote)
6. [Clone Repository](#-clone-repository)
7. [Push Remote](#-push-remote)
8. [Fork Repository](#-fork-repository)

### &#10022; Add Remote:

It mentions remote repository and connects the local repository to a remote repository.

*Syntax:*

It adds `remote_url` with specified name of `remote_name` to the current repository.

```bash
git remote add <remote_name> <remote_url>
```

*Example:*

Where `origin` is commonly used name for the primary remote. But it allows to set and use any name for it.

```bash
git remote add origin https://github.com/username/repository-name.git
```

### &#10022; Show Remote:

To show linked remote reference in the current repository.

*Syntax:*

```bash
git remote show <remote_name>
```

*Example:*

```bash
git remote show origin
```

### &#10022; Manipulate Remote:

**Rename Remote Name:**

*Syntax:*

```bash
git remote rename <old> <new>
```

*Example:*

```bash
git remote rename origin github
```

**Get Remote URL:**

```bash
git remote get-url [--push] [--all] <name>
```

**Set Remote URL:**

```bash
git remote set-url [--push] <name> <newurl> [<oldurl>]
```

```bash
git remote set-url --add <name> <newurl>
```

```bash
git remote set-url --delete <name> <url>
```

**Remove Remote Reference:**

*Syntax:*

```bash
git remote remove <remote_name>
```

*Example:*

```bash
git remote remove origin
```

### &#10022; Fetch Remote:

It downloads/fetch changes from a remote repository to the current local repository. But it does not merge automatically those changes into the current local branch.

*Syntax:*

```bash
git fetch <remote_name>
```

*Example:*

```bash
git fetch origin
```

*Note:* This will updates the local repository of the remote branches like `origin/main` and `origin/develop`). But the local branches remain unchanged like `main` and `develop`. This is useful to lookout or see what changes are made on the remote and available before deciding whether to merge that.

### &#10022; Pull Remote:

It downloads/pull changes from a remote repository to the current local repository. And it merge automatically those changes into the current local branch.

This is similar to fetch command and followed by merge command.  It updates the local branch/branches with the latest changes available from the remote.

*Syntax:*

It it important to specify the branch name if necessary, before pull from remote. Otherwise, It will merge all changes for all branches.

```bash
git pull <remote_name> <branch_name>
```

*Example:*

It will pull and merge only main branch change from remote.

```bash
git pull origin main
```

**Git Pull with Rebase:**

```bash
git pull --rebase origin main
```

**Note:** 

- Git pull will run like git fetch then git merge.
- Git pull with rebase flag will run like git fetch then git rebase.

### &#10022; Clone Repository:

It downloads a clone or a copy of the remote repository into your local device. It creates a local copy of the remote repository at the specified URL.


*Syntax:*

```bash
git clone <remote_url>
```

*Example:*

```bash
git clone https://github.com/username/remote-repository.git
```

**Clone a specific branch:**

By default, Git clones the `main` or `master` branch. It allows to clone specific branch rather than `main` or `master`.

*Syntax:*

```bash
git clone -b <branch_name> <remote_url>
```

```bash
git clone --branch <branch_name> <remote_url>
```

*Example:*

```bash
git clone -b develop https://github.com/username/remote-repository.git
```

**Clone with required commits:**

By default, it clones entire commits for specified branch. But it creates a shallow clone with a history truncated to the specified number of commits. It limits number of commits to be cloned. This can be useful for very large repositories contains large commit histories. It reduces the download size and clone time.

*Syntax:*

```bash
git clone --depth <depth> <remote_url>
```

*Example:*

```bash
git clone --depth 1 https://github.com/username/remote-repository.git
```

**Clone without working tree:**

It clones the repository with wouldn't check out to any working tree. This is useful, if requires only the `.git` directory and but not the actual files.

*Syntax:*

```bash
git clone --no-checkout <remote_url>
``` 

*Example:*

```bash
git clone --no-checkout https://github.com/username/remote-repository.git
```

**Clone Quietly:**

It hides and suppress all progress and their status messages during the clone. But default behavior is `--progress` flag used, it will show progress during the clone operation.

*Syntax:*

```bash
git clone --quiet <remote_url>
```

*Example:*

```bash
git clone --quiet https://github.com/username/remote-repository.git
```

**Clone repository with shallow submodules:**

It clones the repository and its submodules. But it make the submodules shallow as well.

*Example:*

```bash
git clone --shallow-submodules https://github.com/username/remote-repository.git
```

**Clone repository with submodules:**

It clones the repository and initialize their all submodules recursively. 

*Example:*

```bash
git clone --remote-submodules https://github.com/username/remote-repository.git
```

**Clone local repository:**

It clones repository from a local path.

*Example:*

```bash
git clone --local /path/to/local/repo /path/to/new/clone
```

**Clone under specified directory name:**

It specifies the directory where the remote repository should be cloned. If it is not specified, Git will create a directory with the same name as the remote repository.

*Example:*

```bash
git clone https://github.com/username/remote-repository.git my-project
```

### &#10022; Push Remote:

It gives possibilities to uploads the local commits and changes to a remote repository.

*Syntax:* 

It it important to specify the branch name if necessary, before push to remote. Otherwise, It will sent all changes for all branches of the local repository. 

```bash
git push <remote_name> <branch_name>
```

*Example:*

It will sent only main branch commits and change to remote.

```bash
git push origin main
```

**Force Push:**

If the push operation to the remote is aborted due to certain issues. Then use push command with force.

Use with **Caution!**

Forcing a push can overwrite others' work on the remote repository. It can't be undone.

*Example:*

```bash
git push --force-with-lease origin develop
```
or 

```bash
git push --force origin develop
```  

### &#10022; Fork Repository:

It is done on remote repository and associated account. It creates a copy of a remote repository under your own account.

It allows others to contribute to the project without directly modifying the original remote repository. This is common in collaborated and open-source projects.


---
[&#8682; To Top](#-remote-repository)

[&#10094; Previous Topic](./branch-operations.md) &emsp; [Next Topic &#10095;](./git-tags.md)

[&#8962; Goto Home Page](../README.md)