## &#10162; Git Ignore:

`.gitignore` file is a text file in the root directory of the Git repository. It tells Git to ignore track for changes further to specified files and directories. 

This is important for preventing Git from adding those files and directories that shouldn't be tracked under version control such as build artifacts, credentials, sensitive data, system files and temporary files.

### &#9780; Overview:
1. [How it works](#-how-it-works)
2. [Ignore Specific Files](#-ignore-specific-files)
3. [Ignore Specific Directories](#-ignore-specific-directories)
4. [Wildcard Patterns](#-wildcard-patterns)
5. [Comments](#-comments)
6. [Testing Ignored Files](#-testing-ignored-files)
7. [Global Ignore File](#-global-ignore-file)

### &#10022; How it Works:

Git uses patterns defined in the `.gitignore` file to determine which files and directories to ignore. These patterns can be specific filenames, directory names, or wildcard patterns.

### &#10022; Ignore Specific Files:

It ingores files that specified in the `.gitignore` file.

```.gitignore
file.txt                  # Ignores file.txt in the same directory as .gitignore found
path/another/file.txt     # Ignores file.txt in the path/another/ directory
```

### &#10022; Ignore Specific Directories:

```.gitignore
temp/     # Ignores the entire temp directory and its contents
```

### &#10022; Wildcard Patterns:

- `*`: Matches any sequence of characters that starts and ends with (except `/`).

```.gitignore
*.txt       # Ignores all files ending with .txt extension
temp*       # Ignores all files starting with name as "temp"
```

- `?`: Matches any single character.

```
temp?.txt    # Ignores temp1.txt, temp2.txt, etc.
```

- `[]`: Matches any single character from the group of characters within the brackets.

```
temp[123].txt   # Ignores temp1.txt, temp2.txt, and temp3.txt
```

- `!`: Exceptional pattern. This is useful for ignoring most of the files in a directory but not a few specified files.

```
*.log        # Ignores all .log files
!event.log   # Except for event.log
```

- `/`: Used to specify paths relative to the `.gitignore` file.

```
/temp.txt            # Ignores temp.txt file only in the root directory
subdir/temp.txt      # Ignores temp.txt file in the subdir/ directory
subdir/*             # Ignores everything likes files and subdirectories inside subdir/
subdir/*/temp.txt    # Ignores temp.txt files in any subdirectory under subdir/
```

- `**`: Matches zero or more directories.

```
**/temp.txt         # Ignores temp.txt file in all subdirectories
/path/**/temp.txt   # Ignores temp.txt file in any subdirectory under /path/ directory
```

### &#10022; Comments:

To specify comments inside `.gitignore` file that starts with hash (\#) symbol.

```
# This is a comment
```

### &#10022; Testing Ignored Files:

To test if a file will be ignored or not. It shows which rule is causing a file to ignore.

```bash
git check-ignore -v <file> 
```

### &#10022; Global Ignore File:

To create a global `.gitignore` file that applies to all Git local repositories in the device. This is useful for ignoring files certains files that never want to be tracked regardless of the repositories.

It it possible by set rules in separate file and configure it by following command. 

```bash
git config --global core.excludesfile ~/.gitignore_global
```

---
[&#8682; To Top](#-git-ignore)

[&#10094; Previous Topic](./introduction.md) &emsp; [Next Topic &#10095;](./git-attributes.md)

[&#8962; Goto Home Page](../README.md)