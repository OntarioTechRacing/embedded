# GitHub Workflow

---

<details markdown="1">
  <summary>Table of Contents</summary>

-

</details>

---

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models

## 1 Everything DevOps Conventions

All rules / conventions related to devops are listed below:

- Devops: [devops.md](..%2Fconventions%2Fdevops.md)
- Versioning: [versioning.md](..%2Fconventions%2Fversioning.md)

---

## 2 Git version control

Git version control (specifically hosted through GitHub), is a system that
tracks changes to files and coordinates work to multiple developers. It allows
developers to revert files into previous sates, track changes over time and
collaborate on projects efficiently. Git works by maintaining a historical
timeline of who modified what and when.

### 2.1 Repositories

A repository is a space setup on GitHub here project files are stored.

### 2.2 The Git Timeline

The git timeline is the concept of a single timeline which developers can
navigate through into different current and past "snapshots" in time.

### 2.3 Branches

In reference to the central git timeline, a branch can be seen as an individual
"branch" or "path" of the timeline.

In typical repositories the central timeline is named `main` (formerly `master`)
representing the central production timeline. All additional branches would be
breakaway "branches" or "paths" from this central timeline.

> See GitHub Docs:
> [About branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches)

Thus branches allow developers to work on different versions of a repository
simultaneously, without affecting the central timeline.

Branches are often used to represent individual features, bug files and
experimentation.

### 2.4 Commit

A commit is a "snapshot" of a repository at a specific point in time, identified
by a unique SHA or hash. Commits made by an author(s) contain a commit message.
Additionally, they can be configured to reference other git / GitHub features
such as issues.

Commits allow you to save versions of your project and document changes with
commit message. When jumping through a branch, you are jumping though commits.

### 2.5 Push

Push is the act of uploading your commits (new changes) from your local
repository to a remotely hosted `origin`, hosted on GitHub. It acts to publish
your commits to the branch, public to other developers on the branch.

### 2.6 Fetch

Fetch is the act of downloading / synchronizing the commit timeline on the
remote repository to your local repository. This timeline update does enact
changes actually merging those new changes from remote to your local repository.

### 2.7 Pull

Pull is the act of fetching changing and merging them to your local repository.
Unlike a fetch, it goes the extra step of combining the published commits with
your unpublished commits.

### 2.8 Issues

Issues are a way to track enhancements (features), tasks or bugs on GitHub. They
are identified by an incremental issue number (shared increments with pull
requests), in the form of `#n`. Issues can also be created with a reference
branch

Issues can be created by anyone involved in the project and are key to our
project management methodology.

### 2.9 Pull Requests

Pull requests are requests for pull into the main branch and any specific target
branch. Once an enhancement, tasks or bug fix have been implemented, the need to
be accepted into the main production branch. A pull request is a formal request
for approval and review, once accepted, it is merged or rebased into main.

---

## 3 GitHub projects

### 3.1 Scrum / Agile Methodology
