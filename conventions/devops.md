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
    - [3.4 Merge / Rebase Branch](#34-merge--rebase-branch)
- [4 Documentation](#4-documentation)
- [5 GitHub Setup](#5-github-setup)
    - [5.1 Additional GitHub Repository Setup](#51-additional-github-repository-setup)
        - [5.1.1 `.github/`*](#511-github)
        - [5.1.2 `CODEOWNERS`*](#512-codeowners)
    - [5.2 Organization & Team Permissions](#52-organization--team-permissions)
    - [5.3 Labels](#53-labels)
    - [5.4 Issues & Pull Requests (PR)](#54-issues--pull-requests-pr)
        - [5.4.1 Create](#541-create)
            - [5.4.1.1 Name and Description](#5411-name-and-description)
            - [5.4.1.2 Labels](#5412-labels)
            - [5.4.1.3 Create Issue Reference Branch](#5413-create-issue-reference-branch)
            - [5.4.1.4 Assignment](#5414-assignment)
        - [5.4.2 Conversation](#542-conversation)
        - [5.4.3 Close](#543-close)
            - [5.4.3.1 Close Completed](#5431-close-completed)
            - [5.4.3.2 Close Inactive](#5432-close-inactive)
    - [5.5 Milestones](#55-milestones)
    - [5.6 Projects](#56-projects)
        - [5.6.1 Iteration Cycles](#561-iteration-cycles)

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

## 3.4 Merge / Rebase Branch

Use pull requests and merge / rebase up the branches to add changes to main.

Always try to rebase from pull requests when going to main.

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

## 5.4 Issues & Pull Requests (PR)

Issues define problems, features, tasks and all general TODOs.

Pull requests are used for merging, rebasing and closing branches.

### 5.4.1 Create

Create an issue using the GitHub website or GitHub CLI on the applicable
repository.

> See GitHub Docs:
> [Creating an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue)

#### 5.4.1.1 Name and Description

Use appropriate naming and description.

The name should be simple and concise, use the description for full
documentation of the issue.

#### 5.4.1.2 Labels

Apply the appropriate default label(s).

#### 5.4.1.3 Create Issue Reference Branch

For best practices, when creating an issue, create a new reference branch. The
closing pull request should also reference the issue (see further).

> See GitHub Docs:
> [Creating a branch to work on an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-a-branch-for-an-issue)

#### 5.4.1.4 Assignment

If you are the primary responsible developer for the issue and/or pull request,
assign yourself as the assigned.

### 5.4.2 Conversation

Keep the conversation related to the specific issue / pull request at hand. If
you need to reference another issue / pull request, reference directly for
convenience and clarity.

> See GitHub Docs:
> [Assigning issues and pull requests to other GitHub users](https://docs.github.com/en/issues/tracking-your-work-with-issues/assigning-issues-and-pull-requests-to-other-github-users)

### 5.4.3 Close

Closing is required upon reaching a state of "no further activity" (complete or
inactive). There are 2 reasons for closure: complete and inactive.

#### 5.4.3.1 Close Completed

Closing is required upon completion and when all elements within the entire
conversation have been resolved.

All completed items must be closed with a commit directly referencing the issue,
and ideally be closed with a pull request of the issue branch if available.

> See GitHub Docs:
> [Linking a pull request to an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)

#### 5.4.3.2 Close Inactive

Closing is required upon reaching an inactive point, when it is no longer valid
to continue contributing and should no longer be worked on.

Examples of these situations include, but are not limited to:

1. Duplicate
   > See GitHub Docs:
   > [Marking issues or pull requests as a duplicate](https://docs.github.com/en/issues/tracking-your-work-with-issues/marking-issues-or-pull-requests-as-a-duplicate)
2. No longer required for development
3. Can no longer be supported

All inactive items must be closed by a final comment in the issue conversation
stating the reason for closure and documenting the final results of closure as
needed.

## 5.5 Milestones

Name `vM.m.P name`, ideally milestones should line up with iteration planning
and/or end of months.

- `M.m.P` is standard MAJOR.MINOR.PATCH semantic versioning.
- `name` is general milestone name.
    - ie: Pre-PCB, Validation, etc.

## 5.6 Projects

### 5.6.1 Iteration Cycles

Projects follow an iteration cycles of `2 weeks` starting from Monday, January
1st.
