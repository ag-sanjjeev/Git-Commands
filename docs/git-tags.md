## &#10162; Git Tags:

Git tags are treated like labels in a git repositories. It attach to specific commits in the Git commit history. It is useful to mark important points of commit history. Unlike branches, tags are generally immutable.

### &#9780; Overview:
1. [Types of Tags](#-types-of-tags)
2. [Creating Tags](#-creating-tags)
3. [Setting a Tag](#-setting-a-tag)
4. [Checkout a Tag](#-checkout-a-tag)
5. [Pushing a Tag](#-pushing-a-tag)
6. [Deleting a Tag](#-deleting-a-tag)
7. [Listing Tags](#-listing-tags)
8. [Show Tag Information](#-show-tag-information)

### &#10022; Types of Tags:

There two types of tag can be identified based on the usage.
- **Annotated Tags:** It store metadata or complete information about the specific point such as the tag name, email, date, and message. It is recommended type of tag for releases.

- **Lightweight Tags:** It is simple pointers for a commit. It wouldn't store any additional information. It is useful for quick and informal markers to mark important points in the development.

### &#10022; Creating Tags:

By default, Git tag adds the tag to `HEAD` points, usually the tip of the current branch.  

**Creating an Annotated Tag:**

*Syntax:*

```bash
git tag -a <tag_name> -m "<tag_message>"
```

Where,
- `<tag_name>` might be v1.0 or release-20231027 and so on.
- `<tag_message>` might be a long and complete description of the release.

*Example:*

```bash
git tag -a v1.0 -m "First release of the project"
```

**Creating a Lightweight Tag:**

*Syntax:*

```bash
git tag <tag_name>
```

*Example:*

```bash
git tag beta-test
```

### &#10022; Setting a Tag:

It is possible to set a tag to a different commit by specifying the commit hash.

**Annotated Tag:**

*Syntax:*

```bash
git tag -a <tag_name> -m "<tag_message>" <commit_hash>
```

**Lightweight Tag:**

*Syntax:*

```bash
git tag <tag_name> <commit_hash>
```

### &#10022; Checkout a Tag:

Git tags useful to check out a tag that points to the specific commit. So, it allows to view the state of the project at that point in commit history. This will put the repository point in "detached HEAD" state.

*Syntax:*

```bash
git checkout <tag_name>
```

### &#10022; Pushing a Tag:

Git Tags are not automatically pushed to remote repositories when pushing branches. It is required to push those tags explicitly.

**Pushing a single tag:**

```bash
git push origin <tag_name>
```

**Pushing all tags:**

```bash
git push origin --tags
```

### &#10022; Deleting a Tag:

It deletes the tag that are assigned to the specific commit. It would not affect a commit history.

**Deleting a Local Tag:**

*Syntax:*

```bash
git tag -d <tag_name>
```

**Deleting a Remote Tag:**

*Syntax:*

```bash
git push origin --delete tag <tag_name>
```

### &#10022; Listing Tags:

**Listing all tags:**

```bash
git tag # Lists all tags
```

```bash
git tag --list
```

**Listing tags that starts with something:**

```bash
git tag -l "v*"
```

### &#10022; Show Tag Information:

This will show the commit that the tag pointed to, along with the tag message if it is an annotated tag.

```bash
git show <tag_name>
```

---
[&#8682; To Top](#-git-tags)

[&#10094; Previous Topic](./remote-repository.md) &emsp; [Next Topic &#10095;](./git-objects.md)

[&#8962; Goto Home Page](../README.md)