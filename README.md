## Git Fundations
First I may not talk about what we usually do with git, but I will briefly review what git does when we use git commands
### Git Storage
how Git stores information comparing it to a key-value store where data is the value and the hash of the data is the key. This system is also known as content-addressable storage, which is when the content to generate the key.
- you can then use the key to retrieve the content
- the key it's called a SHA1, is cryptographic hash function given a piece of data.
- it produces a 40-digit hexadecimal number and this value should always be the same if the given input is the same

### Git Blobs and Trees
In the .git directory, how git stores project information and its metadata into blob, tree, and commits objects, with each object storing different parts of the project like its content and folder structure. Deleting the .git directory, the information and history of the project are gone, but not the files of the project.

### Git Commit
Commits, which is an object that stores the current contents of the project in a new commit with a log message from the user describing the changes, there's three types of object will create when we do git commit 
- Tree
- Blob
- Commit

[here](https://github.com/nnja/advanced-git/blob/master/exercises/Exercise1-SimpleCommit.md) for exercice to know more about what we are talking about
```
% tree .git/objects
.git/objects
├── 58
│   └── 1caa0fe56cf01dc028cc0b089d364993e046b6
├── 98
│   └── 0a0d5f19a64b4b30a87d4206aade58726b60e3
├── 99
│   └── b2172e47a9367ff4cb3fc9c093090087688807
├── info
└── pack
```

- the Tree
```
% git cat-file -t 581ca         
tree
% git cat-file -p 581ca
100644 blob 980a0d5f19a64b4b30a87d4206aade58726b60e3	hello.txt
```
- the Blob
```
% git cat-file -t 980a0
blob
% git cat-file -p 980a0
Hello World!
```
- the Commit
```
% git cat-file -t 99b21
commit
% git cat-file -p 99b21
tree 581caa0fe56cf01dc028cc0b089d364993e046b6
author Rezha Erlangga <reza@machtwatch.co.id> 1642390839 +0700
committer Rezha Erlangga <reza@machtwatch.co.id> 1642390839 +0700

Initial commit
```

## Git Areas and Stashing
### Working Area (Working Tree)
The working area is where files that are not handled by git. These files are also referred to as "untracked files." Because kind of just in your local directory.
The working area it's where you can add new content, modify and delete content
### Staging Area (Cache)
Staging area is files that are going to be a part of the next commit, which lets git know what changes in the file are going to occur for the next commit
### Repository
The repository contains all of a project's commits. And the commits is a snapshop of what your working and staging area look like at the time of the commit
### Stashing
git stash which is saving work that is not committed to a git repo and is also safe from destructive operations. find more about git stash command [here](https://git-scm.com/docs/git-stash)

[here](https://github.com/nnja/advanced-git/blob/master/exercises/Exercise2-StagingAndStashing.md) for exercice to know more about Staging and Stahsing
