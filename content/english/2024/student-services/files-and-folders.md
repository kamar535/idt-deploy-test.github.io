---
title: Files and folders
weight: 3
---

On a computer, information is stored on the hard drive as files. A folder
(directory) used to collect files that are related in some way. In addition to
files, a folder in turn contain other folders.

## Tree structure

Files and folders form a tree structure. The tree starts at the **root** and each
folder forms its own branch in the tree. The tree is usually depicted upside down with the root
at the top as in this example with the **root** (1) at the top.

![](/images/2024/student-services/files-and-folders/file-tree-example.png?width=300px)

In the folder **root** (1) you find the  files **jacob** (2) and **monkey** (3) and the folders
**buddies** (4) and **animals** (7).

In the folder **buddies** (4) you find the files **emily** (5) and **jacob** (6).

In the folder **animals** (7) you find the files **cat** (8) and **monkey** (9).

Without the tree structure, all files would have to have a unique name. With the
help of the 
tree structure, we can use the same name for different files as long as they are in
different folders. The file **jacob** (2) located in the folder **root** (1) has the same
name as the file **jacob** (6) located in the folder **buddies** (4). The files
have the
same name but are separate files. Similarly, the file  **monkey** (3) which is located
in the folder **root** (1) the same name as the file **monkey** (9) located in the folder
**animals** (7).

## Path

Each file has a unique **path** in the tree structure. The path starts at the
root and for each folder (branch) the symbol `\` is added. The folder
**animals** (7) has the following path.

``` text
root\animals
```

The fill **emily** (5) has the following path. 

``` text
root\buddies\emily
```

The file **jacob** (2) has the same name as the file **jacob** (6), but the
files has unique paths. The file **jacob** (2) has the following path.

``` text
root\jacob
```

The file **jacob** (6) has the following path. 

``` text
root\buddies\jacob
```
