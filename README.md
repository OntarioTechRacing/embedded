# Ontario Tech Racing: Embedded Software

![OTR Logo.png](OTR%20Logo.png)

---

## 0.0 List of Contents

- [1.0 Introduction: _What and Why ES?_](#10-introduction-what-and-why-es)
- [2.0 Conventions: _How We Code_](#20-conventions-how-we-code)
    - [2.1 Conventions for this Documentation Repo](#21-conventions-for-this-documentation-repo)
- [3.0 Developer Environments: _How We Code_](#30-developer-environments-how-we-code)
    - [3.1 Dev Env Documentation Conventions](#31-dev-env-documentation-conventions)
- [4.0 Workflow: _How We Code_](#40-workflow-how-we-code)
- [5.0 GitHub: _How We Version Control_](#50-github-how-we-version-control)
    - [5.1 GitHub Practices & Guidelines](#51-github-practices--guidelines)
        - [5.1.a General](#51a-general)
        - [5.1.b New Repos](#51b-new-repos)
        - [5.1.c Commits](#51c-commits)
        - [5.1.d Pushing Commits](#51d-pushing-commits)
        - [5.1.e Getting Changes to `main`](#51e-getting-changes-to-main)
        - [5.1.f Repo Documentation](#51f-repo-documentation)
- [6.0 Reference / Example Documentation: _How We
  Research_](#60-reference--example-documentation-how-we-research)
- [7.0 Datasheets: _How We Organize_](#70-datasheets-how-we-organize)
- [999.0 Archive & Tech Support](#9990-archive--tech-support)

---

## 1.0 Introduction: _What and Why ES?_

👋 **Welcome to the Embedded Software Department Documentation Repository!**

Embedded Software (ES) is the department in charge of regions covering Embedded Systems, higher
level programming and rapid systems prototyping.

Our department covers many aspects of engineering, primarily:

- 🤖 **Mechatronics Engineering** (embedded systems, control systems, electromechanical machines)
- ⚡ **Electrical Engineering** (circuits, electronics, digital systems, semiconductors)
- 💻 **Software Engineering** (version control, algorithms, data structures, networking)
- ⚙️ **Mechanical Engineering** (enclosures, vibrations)
- _And much more!_

Our primary projects fall within **6 main categories**:

1. 🔭 **Sensors**
    - Collect and forward sensor data
2. 📈 **Telemetry**
    - Process, visualize and interpret data
3. 🚀 **Controls**
    - Control systems, command and manage control loops
4. ⚡ **Hardware**
    - Design, build, test and integrate PCBs
5. 🎮 **Interfaces**
    - Design interfaces primarily for driver(s)
6. 🕹️ **Equipment**
    - Build equipment for testing, simulation, manufacturing, etc

Due to the nature of our department, we also work mostly with the following departments:

- **Hardware and Electronics (HE)**
    - Designing and building our PCBs, completing the hardware for our projects
- **Electric Drivetrain (EDT)**
    - Engineering all high voltage and drivetrain aspects of our team
- **Vehicle Dynamics (VD)**
    - Data processing for design validation, testing and optimization

---

## 2.0 Conventions: _How We Code_

Conventions are guidelines or standards (usually) agreed-upon for writing code, such as naming,
formatting, and commenting practices. They are crucial for promoting readability, maintainability,
and uniformity across a codebase, facilitating easier collaboration and debugging.

All department convention guides can be found in [conventions](conventions).

### 2.1 Conventions for this Documentation Repo

- All general documentation is in markdown
- All written human language is Canadian English
- Line length is 80 unless a link or extended single text is clipping
- Indent is 4 spaces
- Write in full sentences ending with a `.` or some punctuation unless it is a point form
- Headers are numbered the format
    ```
    # N.0 Header 1 Example Name Here
    ## N.N Header 2 Example Name Here
    ### N.N.a Header 3 Example Name Here
    #### N.N.a.N Header 4 Example Name Here
    ```
    - N is decimal numbering
    - a is lower case alphabetical numbering
    - Headers are named with standard `Title Formatting`
- Links, images, etc are very helpful use them appropriately to make good documentation
- Use header links when possible to make referencing easy
- Include a listed version of a table of contents for long documentations such as this one
- Point form is with a `- text`
- Bold is with `**text**`
- Italics is with `_text_`
- Emojis are allowed, but be sensible in usage
- If code blocks are used do your best to declare the language for clean formatting

---

## 3.0 Developer Environments: _How We Code_

Developer environments (dev envs or devenvs), are the tools, platforms, and settings used for
coding. They provide a
tailored and efficient workspace that enhances productivity and supports the specific needs of
different development tasks.

All developer environment setup documentation can be found in [devenvs](devenvs).

### 3.1 Dev Env Documentation Conventions

Speaking of conventions, here are the basic conventions used for quick readability for dev envs.

1. **Required / mandatory items**: `*`
2. **Industry standard or very helpful**: `(Recommended)`
    - Please follow recommendations unless you actually know what you are doing
3. **Opinionated suggestions**: `(Suggested)`
4. **OS specific**: `only for ...`
    - If the key phrase above is not included assume the listed dev env software works on all major
      OS (Windows, macOS, Linux)

---

## 4.0 Workflow: _How We Code_

Workflows is the process and practices used for project management and the technical process for
completing projects. Key points are to facilitate team collaboration, maintaining quality and
consistency of our work.

All workflow documentation can be found in [workflow](workflow).

---

## 5.0 GitHub: _How We Version Control_

Version control is a system that records changes to a file or set of files over time, allowing
multiple people to work collaboratively on (usually) software development. It's crucial for managing
code changes, resolving conflicts, and maintaining a history of project evolution, enhancing
teamwork and project tracking.

- _Technically this section be under a conventions or workflow type header, but since it is so
  important it has its own_

**We use GitHub for all software version control. Often even related project files such as `stl`,
`png`, etc required for documentation is included.**

- Templates for `.gitignore` files in [gitignores](gitignores)
- Repo beginner templates for STM32:
    - [nucleol432kc_template](https://github.com/OntarioTechRacing/nucleol432kc_template)

### 5.1 GitHub Practices & Guidelines

#### 5.1.a General

1. Follow professional standards
    - Use a `.gitignore`
    - Don't push irresponsible code
2. Add a `.github` as a project gets more complex as needed, it is not strictly required
    - If added it should include a standardized `CODEOWNERS`
3. Add to the Organization, don't hide things to your personal
    - [https://github.com/OntarioTechRacing](https://github.com/OntarioTechRacing)
4. Organizational access role security must always be maintained

#### 5.1.b New Repos

1. All new repos should be **private** unless cleared and agreed to by team leadership
2. All repos should use appropriate naming, if arbitrary use snake case

#### 5.1.c Commits

1. Name your commits starting with a present tense verb
    - Examples:
        - "Add cool feature xyz"
        - "Refactor rename variable sneaky"
        - "Clean up formatting"

#### 5.1.d Pushing Commits

1. **Never force push**
    - Unless you absolutely know what you are doing
    - If you're force pushing you already messed up another practice guideline earlier

#### 5.1.e Getting Changes to `main`

1. Never push directly to main, especially in code repos
    - Only in emergencies you should always pull request
2. Always **pull request** to add changes to main
3. Always **maintain linear history** on the main branch
4. Always **rebase changes** from pull requests to avoid issues
    - Unless you know what you are doing, but you should really never need to

#### 5.1.f Repo Documentation

1. Always add a `README.md` to your repo
2. Document all important aspects of the project or code in the repo on the main README
3. Include a directory `documentation` for reference files such as `png`s
4. Include a directory `testing` for all reference testing scripts or files

---

## 6.0 Reference / Example Documentation: _How We Research_

- All resources and reference documentation can be found in [resources](resources)

---

## 7.0 Datasheets: _How We Organize_

- All datasheets are stored on
  the [OTR Embedded Software Google Drive](https://drive.google.com/drive/folders/0AHPA2ZoOBCtSUk9PVA)

---

## 999.0 Archive & Tech Support

- [case_studies.md](resources%2Fcase_studies.md)
- [ace_5030_pc_readme.md](resources%2Face_5030_pc_readme.md)
