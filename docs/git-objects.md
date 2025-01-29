## &#10162; Git Objects:

Git works with objects. It stores all of its data as `objects` within the `.git` directory of the current repository. These are identified by a hash of their content. There are three main types of Git objects such as blobs, trees and commits.

### &#9780; Overview:
1. [Blobs](#-blobs)
2. [Trees](#-trees)
3. [Commits](#-commits)
4. [Relation Between Objects](#-relation-between-objects)

### &#10022; Blobs:

Blobs store the `content` of a file. It wouldn't store the filename or any other metadata. But it store just a raw data.

Consider a file `index.html` with some HTML code. Initially, Git will store that content as a blob.  If the file is modified then Git will create a new blob for the new content. Which store the updated content.

### &#10022; Trees:

Trees holds relationship and represent directories and their files and subdirectories. A tree object contains a list of entries. Each entry is either a blob (representing a file) or another tree (representing a subdirectory).

### &#10022; Commits:

Commits is a snapshots of the project at a specific point of time. A commit object links together a tree which represents the state of the files at the moment, a commit message, the author details, and the date information. Importantly, the commits point to their parent commit(s) as well and creating a history of changes.

### &#10022; Relation Between Objects:

1. Git creates blobs to store the content changes of those files.
2. Git organizes these blobs into trees, which represents the directory structure.
3. When commit a changes, Git creates a commit object that points to the specific tree, Which represents the state of the files at the moment. The commit also holds information about author, date, message and links to previous commits.

---
[&#8682; To Top](#-git-objects)

[&#10094; Previous Topic](./remote-repository.md) &emsp; [Next Topic &#10095;](./git-reset.md)

[&#8962; Goto Home Page](../README.md)