## &#10162; Git Attributes:

Git attributes are similar to git ignore. It describes how to be handle specific files and files patterns by Git. It allow to define metadata associated with files, line-ending, diffing, merging, and more.

Git attributes are defined in a `.gitattributes` file inside the root of the Git repository (or in a subdirectory to apply attributes to a specific directory scope).

### &#9780; Overview:
1. [How it Works](#-how-it-works)
2. [Text and Binary](#-text-and-binary)
3. [End of Line](#-end-of-line)
4. [Delta Compression](#-delta-compression)
5. [Linguistic Language](#-linguistic-language)
6. [Export Ignore](#-export-ignore)

### &#10022; How it Works:

*Syntax:*

```.gitattributes
<pattern> <attribute1> <attribute2> ...
```

Where,
- `<pattern>` denotes a file pattern as used in `.gitignore`.
- `<attribute>` denotes the attribute to set for that files.


### &#10022; Text and Binary:

These attributes decides Git whether a file should be treated as text or binary. Additionally, Git handles line endings differently for text files.

```.gitattributes
*.txt text        # All .txt files are text
*.jpg binary      # All .jpg files are binary
```


### &#10022; End of Line:

This attribute decides Git to handles line endings for files. For Windows `CRLF`, For Linux and macOS `LF`.

```.gitattributes
*.txt eol=lf     # Normalize line endings to LF for .txt files
*.bat eol=crlf   # Normalize line endings to CRLF for .bat files
```

**Shorthand Definition:**

```.gitattributes
*.txt crlf       # Use CRLF line endings for .txt files
*.txt -crlf      # Disable CRLF conversion for .txt files
```

### &#10022; Delta Compression:

Delta compression for the files, Which is usually beneficial for text files, but might not be effective for binary files such as `.jpg`, `.png`, `.gz` and so on.

```.gitattributes
*.gz -delta     # Disable delta compression for .gz files
```

### &#10022; Linguistic Language:

This tells Git which language the file is written in. This is used by some Git hosting platforms for syntax highlighting and other features for the repositories.

```
*.php linguist-language=PHP
*.js linguist-language=JS
```

### &#10022; Export Ignore:

It prevents file patterns and files that being included when exporting the repository changes.

```
.env export-ignore
```

---
[&#8682; To Top](#-git-attributes)

[&#10094; Previous Topic](./git-ignore.md) &emsp; [Next Topic &#10095;](./basic-repository-operations.md)

[&#8962; Goto Home Page](../README.md)