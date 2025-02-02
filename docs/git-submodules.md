## &#10162; Git Submodules:

Git submodules is a feature that allow to embed another Git repository as a module or a subdirectory within the main project. This is useful feature when the project depends on some other projects such as libraries, plug-ins, shared components, etc.

### &#9780; Overview:
1. [How Submodule Works](#-how-submodule-works)
2. [Add a Submodule](#-add-a-submodule)
3. [Initialize a Submodule](#-initialize-a-submodule)
4. [Update a Submodule](#-update-a-submodule)
5. [Submodule Recursive](#-submodule-recursive)
6. [Commit Submodule Changes](#-commit-submodule-changes)
7. [Update Main Project](#-update-main-project)
8. [Clone with Submodules](#-clone-with-submodules)
9. [Pull Changes in Submodules](#-pull-changes-in-submodules)
10. [Publishing Submodules Changes](#-publishing-submodules-changes)
11. [Deleting Submodules](#-deleting-submodules)
12. [Key Considerations](#-key-considerations)

### &#10022; How Submodule Works:

- In main project repository also referred as "superproject", It stores a reference of submodule with specific commit of their repository.
- The submodules' files are checked out into a subdirectories of the superproject.
- Any changes made within the submodule directory to be committed and pushed separately to the submodule's own repository.
- When updating the submodule in the superproject means updating the reference of the specific commit of the submodule.

### &#10022; Add a Submodule:

It will add another repository as a submodule inside the superproject.

*Syntax:*

```bash
git submodule add <url> <path>
```

Where,
- `<url>` is referred to an URL of the submodule repository.
- `<path>` is referred to the path where the submodule should be placed inside the superproject.

*Example:*

This adds the `library` repository as a submodule inside the `libs/library` directory of the superproject.

```bash
git submodule add https://github.com/username/library.git libs/library
```

### &#10022; Initialize a Submodule:

After adding a submodule, It required to initialize it. This registers the submodule in the `.gitmodules` file, which can be tracked by superproject.

*Example:*

```bash
git submodule init
```

### &#10022; Update a Submodule:

It required to update the submodule to checkout the correct commit.

*Example:*

```bash
git submodule update
```

### &#10022; Submodule Recursive:

Submodule can be initialized and updated at same time by recursive. The `--recursive` flag is important, if the submodules themselves have another/other submodules.

*Example:*

```bash
git submodule update --init --recursive
```

### &#10022; Commit Submodule Changes:

If any changes made within the submodule directory, that need to be commit those changes within the submodule itself.

*Example:*

```bash
# Go into the submodule directory
cd libs/library  
# Add changes to stagging area
git add .
# Commit those changes with message
git commit -m "Submodule updates"
# push changes to remote if required
git push origin main
```

### &#10022; Update Main Project:

After committing and pushing changes in the submodule, To reflect those submodule commits then update to superproject.

*Example:*

```bash
# Stage the updated submodule reference in the root of superproject
git add libs/library
# Commit those submodule changes in superproject
git commit -m "Updated submodule"
# push changes to remote if required
git push origin main
```

### &#10022; Clone with Submodules:

To clone a repository with their submodule, then use the `--recursive` flag.

*Syntax:*

```bash
git clone --recursive <superproject_url>
```

Or after cloning, use init and update commands

*Example:*

```bash
git submodule update --init --recursive
```

### &#10022; Pull Changes in Submodules:

To fetches and updates the submodule with submodule remote origin.

*Example:*

```bash
git submodule update --remote 
```

### &#10022; Publishing Submodules Changes:

To publish changes of submodule, then commit changes within submodule directory. After commit it to superproject.

Remember: The superproject only stores a reference of a specific commit of the submodule but not the changes. To maintain and preserve the changes, then it requires to push those changes to remote submodules repository.

*Example:*

```bash
# Go into the submodule directory
cd libs/library  
# Add changes to stagging area
git add .
# Commit those changes with message
git commit -m "Submodule updates"
# Change directory to root of superproject
cd ..
# Stage the updated submodule reference in the root of superproject
git add libs/library
# Commit those submodule changes in superproject
git commit -m "Updated submodule"
# push changes to remote if required
git push origin main
```

### &#10022; Deleting Submodules:

**Caution:** It need to edit `.gitmodules` and remove the submodule directory from it.

### &#10022; Key Considerations:

- `.gitmodules` file stores the configuration for the submodules. It should be committed to version control.
- Submodule URLs should be relative URLs in `.gitmodules` if possible. To make the project easily portable.
- Updating Submodules requires attention. Especially when pulling changes from others. It is recommended and safest approach to use `git submodule update --remote`.

---
[&#8682; To Top](#-git-submodules)

[&#10094; Previous Topic](./git-reset.md) &emsp; [Next Topic &#10095;](./git-subtrees.md)

[&#8962; Goto Home Page](../README.md)