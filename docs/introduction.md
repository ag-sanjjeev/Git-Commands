## &#10162; Introduction:
Git is a distributed version control system. It is used to track changes and preserve history of changes for computer files.

### &#9780; Overview:
1. [Need for git](#-need-for-git)
2. [Associated Files](#-associated-files)
3. [Help Commands](#-help-commands)
4. [Configurations](#-configurations)
5. [Git LFS](#-git-lfs)
6. [Security Practices](#-security-practices)
7. [Show Tree Structure](#-show-tree-structure)

### &#10022; Need for git:
- Distributed means each developer can have the copy of all the files associated with repository unlike older version control system.
- It encourage and support to team collaboration.
- Version control system means preserve history of all changes made on each file as a version.
- It helps to navigate back and forth different versions of file changes.

### &#10022; Associated Files:

- `.git` directory: 
	- This is the root of every Git repository. 
	- It is a hidden directory that contains all the necessary files for track changes. 
	- Do not modify this directory directly, otherwise may lose data.

- `.gitignore` file: 
	- This file tells Git, which directories, files and extension to ignore from including to repository as well as tracking changes. 
	- It is possible to exclude directories and files like temporary files, build or outputs directory, or sensitive data from being tracked. 
	Example:
    ```.gitignore
    # Ignore all files that end with extension .txt
    *.txt

    # Ignore the node_modules directory
    node_modules/

    # Ignore files starting with .
    .env 
    ```

- `.gitattributes` file:
	- This file tells Git about attributes for specific files or patterns. 
	- It is possible to control about How to handles certain files by Git, such as:
		- Text vs binary files: This will affects Git line endings.
		- Diffing strategies: Customize behavior of compares files by Git.
		- Large file storage (LFS): It helps to handle large files efficiently.

- `.gitmodules` file: 
	- This file is used to specify the other Git repositories as submodule within the project.
	- It stores information about the submodules such as their paths and remote origin URLs.

### &#10022; Help Commands:

To view built-in documetations and help related files for git. use help command. 

**Show list of commands:**

```bash
git --helps
```

**Show documetation for specific command:**

*Syntax:*

```bash
git <command> --help
```

```bash
git help <command>
```

*Example:*

```bash
git log --help
```

```bash
git help log
```

### &#10022; Configurations:

Git configurations allows to customize how Git works on the current device. 

**Configurations Levels:**

Git has three levels of configuration:

1. **System:** It applies configurations to all users on the device. Those configurations stored in `/etc/gitconfig` or the equivalent in different devices. 

2. **Global:** It applies to the current user. Those configurations stored in `~/.gitconfig` or the equivalent in different devices. This is the most common level for per user/personal settings.

3. **Local:** It applies only to the current repository. Those configurations stored in `.git/config` within the repository. This is recommended for repository-specific settings.

**Viewing Configuration:**

```bash
git config --list               # Lists all configurations from all levels
git config --show-origin --list # Lists all configurations with origin file
git config --get <key>          # Gets specific configuration key
git config --get-all <key>      # Gets all value of specific configuration key (if it has multiple)
```

**Setting Configuration:**

```bash
git config --system <key> <value>  # Sets a system level configuration
git config --global <key> <value>  # Sets a global level configuration
git config --local <key> <value>   # Sets a local level configuration
```

**Common Configuration Options and Examples:**

1. User Information:

```bash
git config --global user.name "Author Name"
git config --global user.email "example@host"
```

2. Default Branch:

```bash
git config --global init.defaultBranch main  # Sets global level configuration for default branch name for new repositories
```

3. Set Aliases:

```bash
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.lg "log --graph --pretty=format:'%C(yellow)%h%Creset - %s %C(green)(%cr)%Creset %C(bold red)<%an>%Creset'"
```

Use `git co` for `git checkout`, `git ci` for `git commit`, `git st` for `git status`, and `git lg` for git log with format as alias/shortcuts.

4. Autostash When Rebase:

```bash
git config --global rebase.autostash true  # Automatically stash changes to stash list during rebase operation
```

### &#10022; Git LFS:

- When working with large repositories in Git, Which causes unique challenges due to the huge volume of data. To efficiently handle large repositories, Git LFS will be helpful.

- Git is designed to efficiently handle and track text-based files. Large binary files like images, videos, packages can bloat the repository. Which makes the repository to be slow when clone, fetch, and push.

- Git LFS stores large binary files separately and replaces them with pointers in the repository. This keeps the repository size manageable.

### &#10022; Security Practices:

**Authentication:**

- *SSH Keys:* are more secure than passwords for authenticating with remote repositories. Use SSH keys instead of passwords. Generate a strong SSH key pair and add those public key to remote repository hosting provider settings.

**Exclude Sensitive Data:**

- *.gitignore* used to ignore the files and directories that are not be tracked and prevent those data to be exported to remote repository.

**Hooks:**

- The hooks are helpful to automate certain thing based on the events such as before commit and after commit, during merge events and so on. That give possible to write custom automated tasks to perform before and after events. 
- For example, to avoid secret credentials to be committed, then use `pre-commit` hooks with tools like `detect-secret` or `git-secrets` that prevents commit when files contains any credentials with it.  

**Search and Remove Certain Data or Files:**

- This will be helpful to search and remove for already been committed files that contains certain secret credentials. To perform these task with `filter-branch` command. Which will rewrite commit history and hash. Finally, It cause problems for other collaborators.

1. Search for data:

```bash
git grep "sensitive_data"
```

2. Search for data in all branches:

```bash
git grep --all "sensitive_data"
```

3. Search for data with formatted:

```bash
git log --all --grep="sensitive_data" --pretty=format:%H
```

4. Search for sensitive data in a file in all branches:

```bash
git filter-branch --tree-filter 'sed -i "/sensitive information/ d" filename' -- --all
```

5. Replace sensitive data in a file in all branches:

```bash
git filter-branch --force --tree-filter "sed -i 's/old_text/new_text/g'" --prune-empty --all HEAD
```

6. For example remove password from all files:

```bash
git filter-branch --force --tree-filter "sed -i 's/password='test'/password='***'/g'" --prune-empty --all HEAD
```

7. For example remove password from specified file:

```bash
git filter-branch --force --tree-filter "sed -i 's/password='test'/password='***'/g' Configuration.php" HEAD
```

```bash
git filter-branch --force --tree-filter "sed -i Configuration.php 's/password='test'/password='***'/g'" HEAD
```

8. To avoid missing file error when replace sensitive data:

If the file is not exist on some commits that through a no file exist error. To avoid these kind of scenario, then use the below command:

```bash
git filter-branch --force --tree-filter "sh -c 'if [ -f Configuration.php ]; then sed -i 's/old_text/new_text/g' Configuration.php; fi'" HEAD
```

### &#10022; Show Tree Structure:

- list files and folders as tree in a repository:

```bash
ls -R | grep ":$" | sed -e 's/:$//' -e 's/[^-][^\/]*\//--/g' -e 's/^/   /' -e 's/-/|/'
```

- list files including some ignored files:

```
find . -print | grep -v '/\.' | grep -v -f <(git ls-files -c) | sed 's/[^/]*\//  |-- /g'
```

```
find . -print | grep -v '/\.' | grep -v -f <(git ls-files -c) | grep -v -f <(git ls-files -o -i --exclude-standard) | sed 's/[^/]*\//  |-- /g'
```

- list all files in a directory as tree view with hidden files and directories:

```
find . -print | sed 's/[^/]*\//  |-- /g'
```

---
[&#8682; To Top](#-introduction)

[&#10094; Previous Topic](../README.md) &emsp; [Next Topic &#10095;](./git-ignore.md)

[&#8962; Goto Home Page](../README.md)