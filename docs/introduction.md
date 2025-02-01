## &#10162; Introduction:
Git is a distributed version control system. It is used to track changes and preserve history of changes for computer files.

### &#9780; Overview:
1. [Need for git](#-need-for-git)
2. [Associated Files](#-associated-files)

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

---
[&#8682; To Top](#-introduction)

[&#10094; Previous Topic](../README.md) &emsp; [Next Topic &#10095;](./git-ignore.md)

[&#8962; Goto Home Page](../README.md)