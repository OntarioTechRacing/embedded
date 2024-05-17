# Git and GitHub Cheat Sheet

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Overview](#1-Overview)
- [2 General](#2-general)
- [3 Reset HEAD](#3-reset-head)
  - [3.1 Flags](#31-flags)
  - [3.2 Reset to Commit](#32-reset-to-commit)
  - [3.3 Reset to Origin Branch HEAD](#33-reset-to-origin-branch-head)
  - [3.4 Note on Pushing Resets](#34-note-on-pushing-resets)
- [4 Submodule](#411-results-gitmodules)
    - [4.1 Add Submodule](#41-add-submodule)
        - [4.1.1 Results (.gitmodules)](#411-results-gitmodules)
    - [4.2 Fetch Submodule Commits](#42-fetch-submodule-commits)
    - [4.3 Pull Submodule](#43-pull-submodule)
    - [4.4 Update Submodule](#44-update-submodule)
    - [4.5 Remove Submodule](#45-remove-submodule)

</details>

---

## 1 Overview

### 1.1 Format

Commands are written in the following format.

````
```shell
git ... # Comment.
```
````

---

## 2 General

```shell
git commit -m "Add new xyz feature"
git push
```

---

## 3 Reset HEAD

## 3.1 Flags

`--soft`: Does not touch the index file or the working tree, but resets the head
to <commit>. Changes from <commit> onwards are preserved in the working 
directory and as staged changes.

`--mixed`: Resets the index but not the working tree (i.e., the changed files 
are preserved but not marked for commit) and reports what has not been updated.
This is the default action if no mode is specified.

`--hard`: Resets the index and working tree. Any changes to tracked files in the
working tree since <commit> are discarded.

`--merge`: Resets the index and updates the files in the working tree that are
different between <commit> and HEAD, but keeps those which are different between
the index and working tree (i.e., which have changes which have not been added).
If a merge conflict arises, it needs to be resolved manually.

`--keep`: Resets index entries and updates files in the working tree that are
different between <commit> and HEAD. If a file that is different between
<commit> and the index has unstaged changes, reset is aborted.

## 3.2 Reset to Commit

To revert HEAD to a previous commit without the commit ID (also to Force Revert
commits).

```shell
git reset --hard HEAD^  # Reset to 1 commit back, add `^` for each additional commit.
git reset --hard <commit_hash>  # Reset to specific commit hash.
```

## 3.3 Reset to Origin Branch HEAD

This resets the current branch's tip to the specified branch. In other words, it
makes the current branch point to the same commit as the target branch.

```shell
git reset --hard origin/<branch>  # Target to match head to remote branch.
git reset --hard <branch>  # Target to match head to local branch.
```

## 3.4 Note on Pushing Resets

You would need to force push with `git push -f` for force the revert, however 
this is very high risk for loss of work.

---

## 4 Submodule

### 4.1 Add Submodule

```shell
git submodule add <remote_origin> <destination_path>
```

- `<destination_path>` is optional.

When adding a Git submodule, the new submodule will automatically be
staged. To commit and push, standard procedure can be followed.

### 4.1.1 Results (.gitmodules)

Following a new Git submodule commit, multiple actions will be performed
automatically:

1. A new directory is created in the repository named after the submodule added.
2. A `.gitmodules` file is created in the Git repository.
    - Contains the references to the remote repositories acting as submodules.
3. `.git/config` is modified to include the added submodule.

### 4.2 Fetch Submodule Commits

```shell
cd repository/submodule # Enter submodule directory.
git fetch
```

### 4.3 Pull Submodule

```shell
git submodule update # --init --recursive
```

### 4.4 Update Submodule

```shell
git submodule update # --remote --merge
```

- If you do not use the `–remote` flag, a manual `git pull` within each
  submodule will be required.

### 4.5 Remove Submodule

```shell
git submodule deinit <submodule> # Update .git/config.
git rm <submodule> # Remove submodule files.
```

---
