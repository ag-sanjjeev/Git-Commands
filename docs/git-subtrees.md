## &#10162; Git Subtrees:

Git subtrees are features that similar to submodules but differs in a way to embed another Git repository as a subdirectory within the main project. The subtrees integrate the entire commit history of the other repositories into the main project's history. 

This doesn't have a separate `.git` directory for the subtrees.

### &#9780; Overview:
1. [How Subtrees Work](#-how-subtrees-work)
2. [Adding a Subtree](#-adding-a-subtree)
3. [Pulling Changes](#-pulling-changes)
4. [Pushing Changes](#-pushing-changes)
5. [Squash](#-squash)
6. [Onto](#-onto)
7. [Strategy](#-strategy)
8. [Comparison](#-comparison)

### &#10022; How Subtrees Work:

- The subtrees' files are merged into a subdirectory of the main project.
- Any changes made within the subtree directory are considered as a part of the main project history.
- Updating the subtree means merging changes from the external repository.

*Example:*

1. **Add Subtree:** `git subtree add --prefix=libs/library https://github.com/username/library.git main`
2. **Make Changes:** Edit files within the `libs/library` directory, if required.
3. **Commit Changes:** Commit those changes to main project by following commands `git add .` and `git commit -m "Updated library"`
4. **Pull Updates:** Update files if any changes made, `git subtree pull --prefix=libs/library https://github.com/username/library.git main`
5. **Push Changes:** Publish changes made in local subtree to the remote subtree repository by following commands, `git subtree push --prefix=libs/library https://github.com/username/library.git main`

### &#10022; Adding a Subtree:

Add subtree as part of the main project from a remote repository branch.

*Syntax:*

```bash
git subtree add --prefix=<prefix> <repository> <branch>
```

Where,
- `<prefix>` means the relative path that the subtree files should be placed within the main project (e.g., `libs/library`).
- `<repository>` means the URL of the remote repository to be added.
- `<branch>` means the branch name of remote repository to be include from.

*Example:*

To add the `main` branch of the `library` repository as a subtree in the `libs/library` directory.

```bash
git subtree add --prefix=libs/library https://github.com/username/library.git main
```

**Add commit message for adding subtree:**

To specify the commit message for the adding a subtree from remote repository.

```bash
git subtree add --prefix=libs/library https://github.com/username/library.git main --message="Added library as a subtree"
```

### &#10022; Pulling Changes:

To pull or fetch the changes from the specified branch of the remote repository and merges them into the subtree.

*Syntax:*

```bash
git subtree pull --prefix=<prefix> <repository> <branch>
```

*Example:*

```bash
git subtree pull --prefix=libs/library https://github.com/username/library.git main
```

### &#10022; Pushing Changes:

This allow to push changes made within the subtree directory back to the remote repository.

*Syntax:*

```bash
git subtree push --prefix=<prefix> <repository> <branch>
```

*Example:*

```bash
git subtree push --prefix=libs/library https://github.com/username/library.git main
```

### &#10022; Squash:

This option is used when adding and pulling from remote repository. It creates a single **squashed** commit in the main project history that contains all the changes from the subtree rather than preserving the every commits from the subtree repository. 

This can make the main project history cleaner.

*Example:*

```bash
git subtree add --prefix=libs/library --squash https://github.com/username/library.git main
```

### &#10022; Onto:

This option is used when pulling from remote repository. It specifies a branch in the local repository to merge onto before pulling from the remote repository. 

This allow for advanced merging options and maintain project easier.

*Example:*

```bash
git subtree pull --prefix=libs/library --onto=develop https://github.com/username/library.git main
```

### &#10022; Strategy:

This option is used when pulling from remote repository. It specifies the merge strategy to use such as `resolve`, `recursive`.

*Example:*

```bash
git subtree pull --prefix=libs/library --onto=develop https://github.com/username/library.git main --strategy recursive
```

```bash
git subtree pull --prefix=libs/library --onto=develop https://github.com/username/library.git main -s
```

### &#10022; Comparison:

| Feature        | Subtrees                               | Submodules                            |
|----------------|----------------------------------------|---------------------------------------|
| History        | Integrated into the main project       | Separate Git history                  |
| `.git` directory | No separate git directory | Each submodule has its own `.git` directory      |
| Complexity     | Generally easier to work with          | It can be more complex to manage      |
| Use Cases      | When need to integrated history as well as maintainable | When need a completely separate history |

---
[&#8682; To Top](#-git-subtrees)

[&#10094; Previous Topic](./git-submodules.md) &emsp; [Next Topic &#10095;](./advanced-commands.md)

[&#8962; Goto Home Page](../README.md)