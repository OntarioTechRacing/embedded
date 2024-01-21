# DevOps Conventions

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Background](#1-background)
- [2 Git Setup](#2-git-setup)
    - [2.1 Repositories](#21-repositories)
        - [2.1.1 Permissions](#211-permissions)
        - [2.1.2 Naming](#212-naming)
    - [2.2 Branches](#22-branches)
    - [2.3 Common / Required files](#23-common--required-files)
        - [2.3.1 `.gitignore`*](#231-gitignore)
        - [2.3.2 `README.md`*](#232-readmemd)
        - [2.3.3 `documentation/`](#233-documentation)
        - [2.3.4 `tests/`](#234-tests)
- [3 Getting to `main`](#3-getting-to-main)
    - [3.1 History](#31-history)
    - [3.2 Commits](#32-commits)
    - [3.3 Pushes](#33-pushes)
        - [3.3.1 Force Pushes](#331-force-pushes)
    - [3.4 Merging Branches / Pull Requests](#34-merging-branches--pull-requests)
- [4 Documentation](#4-documentation)
- [5 GitHub Setup](#5-github-setup)
    - [5.1 Additional GitHub Repository Setup](#51-additional-github-repository-setup)
        - [5.1.1 `.github/`*](#511-github)
        - [5.1.2 `CODEOWNERS`*](#512-codeowners)
    - [5.2 Organization & Team Permissions](#52-organization--team-permissions)
    - [5.3 Labels](#53-labels)
    - [5.4 Issues](#54-issues)
    - [5.5 Milestones](#55-milestones)
    - [5.6 Projects](#56-projects)

</details>

---

## 1 Background

DevOps are crucial for maintaining version control and managing production. The
following conventions are outlined to maintain good engineering practices, clear
documentation and formatting.

## 2 Git Setup

Version control is done through git.

### 2.1 Repositories

Each project is version controlled through one repo.

#### 2.1.1 Permissions

All new repos should be **private** unless cleared and agreed to by team
leadership.

#### 2.1.2 Naming

All repos should use appropriate naming, if arbitrary default to snake_case.

### 2.2 Branches

`main` is always the production / final release branch.

### 2.3 Common / Required files

#### 2.3.1 `.gitignore`*

Always include one in the main directory.

- Recommended templates: [gitignores](..%2Fgitignores).

#### 2.3.2 `README.md`*

Always include one in the main directory for complete repository documentation.

#### 2.3.3 `documentation/`

If reference documentation files such as pictures are required, use this
directory.

#### 2.3.4 `tests/`

If reference tests scripts or files are required, use this directory.

## 3 Getting to `main`

Never push directly to main unless working alone.

## 3.1 History

Always maintain linear history on the main branch, and try to keep linear
history on lower branches.

## 3.2 Commits

Name your commits starting with a present tense verb or technical adverb.

- Examples:
    - `Add cool feature xyz`.
    - `Refactor rename variable sneaky`.
    - `Clean up formatting`.

## 3.3 Pushes

Make sure to fetch and pull to prevent merge errors before pushing.

### 3.3.1 Force Pushes

Never force push unless you absolutely know what you are doing.

- If you're force pushing you already messed up another practice guideline
  earlier.

## 3.4 Merging Branches / Pull Requests

Use pull requests and merge / base up the branches to add changes to main.

Always try to rebase from pull requests.

## 4 Documentation

## 5 GitHub Setup

Git origin, org, projects, etc are all set up through GitHub on
the [OntarioTechRacing organization](https://github.com/OntarioTechRacing).

### 5.1 Additional GitHub Repository Setup

#### 5.1.1 `.github/`*

Add this standard directory and files at the root as a project gets more
complex.

#### 5.1.2 `CODEOWNERS`*

Always add for project managers, devops, etc.

## 5.2 Organization & Team Permissions

Organizational access role security must always be maintained.

## 5.3 Labels

Use default labels.

## 5.4 Issues

## 5.5 Milestones

Name `vM.m.P name`, ideally milestones should line up with iteration planning
and/or end of months.

- `M.m.P` is standard MAJOR.MINOR.PATCH semantic versioning.
- `name` is general milestone name.
    - ie: Pre-PCB, Validation, etc.

## 5.6 Projects

Projects follow an iteration cycle of 2 weeks starting from January 1st.
