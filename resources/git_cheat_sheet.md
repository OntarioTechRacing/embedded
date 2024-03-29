# Git / GitHub Cheat Sheet

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Overview](#1-Overview)
- [2 General](#2-general)
- [3 HEAD Location](#3-head-location)
    - [3.1 Quick Reversing HEAD](#3-head-location)
- [4 Submodule](#411-results-gitmodules)
    - [4.1 Add Submodule](#41-add-submodule)
        - [4.1.1 Results (`.gitmodules`)](#411-results-gitmodules)
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
$ git ... # Comment.
```
````

---

## 2 General

```shell
$ git commit -m "Add new xyz feature"
$ git push
```

---

## 3 HEAD Location

## 3.1 Quick Reversing HEAD

To revert HEAD to a previous commit without the commit ID (also to Force Revert
commits)

```shell
$ git reset --hard HEAD^ # Revert to 1 commit back, add `^` for each additional n commit to revert to.
```

- You would force push with `git push -f` for force the revert (HIGH RISK).

---

## 4 Submodule

### 4.1 Add Submodule

```shell
$ git submodule add <remote_origin> <destination_path>
```

- `<destination_path>` is optional.

When adding a Git submodule, the new submodule will automatically be
staged. To commit and push, standard procedure can be followed.

### 4.1.1 Results (`.gitmodules`)

Following a new Git submodule commit, multiple actions will be performed
automatically:

1. A new directory is created in the repository named after the submodule added.
2. A `.gitmodules` file is created in the Git repository.
    - Contains the references to the remote repositories acting as submodules.
3. `.git/config` is modified to include the added submodule.

### 4.2 Fetch Submodule Commits

```shell
$ cd repository/submodule # Enter submodule directory.
$ git fetch
```

### 4.3 Pull Submodule

```shell
$ git submodule update # --init --recursive
```

### 4.4 Update Submodule

```shell
$ git submodule update # --remote --merge
```

- If you do not use the `–remote` flag, a manual `git pull` within each
  submodule will be required.

### 4.5 Remove Submodule

```shell
$ git submodule deinit <submodule> # Update .git/config.
$ git rm <submodule> # Remove submodule files.
```

---
