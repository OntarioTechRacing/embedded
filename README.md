# Ontario Tech Racing: Embedded Software

![OTR Logo.png](OTR%20Logo.png)

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Introduction: _Welcome_](#1-introduction-welcome)
- [2 Conventions: _How We Code_](#2-conventions-how-we-code)
    - [2.1 Conventions for this Documentation Repo](#21-conventions-for-this-documentation-repo)
- [3 Developer Environments: _How We
  Code_](#3-developer-environments-how-we-code)
    - [3.1 Dev Env Documentation Conventions](#31-dev-env-documentation-conventions)
- [4 Workflow: _How We Code_](#4-workflow-how-we-code)
- [5 GitHub: _How We Version Control_](#5-github-how-we-version-control)
- [6 Reference / Example Documentation: _How We
  Research_](#6-reference--example-documentation-how-we-research)
- [7 Datasheets: _How We Organize_](#7-datasheets-how-we-organize)
- [999 Archive & Tech Support](#999-archive--tech-support)

</details>

---

## 1 Introduction: _Welcome_

👋 **Welcome to the Embedded Software Department Documentation Repository!**

If you are new to our department, please first visit
the [welcome_to_es repository](https://github.com/OntarioTechRacing/welcome_to_es).

---

## 2 Conventions: _How We Code_

Conventions are guidelines or standards (usually) agreed-upon for writing code,
such as naming, formatting, and commenting practices. They are crucial for
promoting readability, maintainability and uniformity across a codebase,
facilitating easier collaboration and debugging.

All department convention guides can be found in [conventions](conventions).

### 2.1 Conventions for this Documentation Repo

- All general documentation is in markdown.
- All written human language is Canadian English.
- Line length is 80 unless a link or extended single text is clipping.
- Indent is 4 spaces.
- Write in full sentences ending with a `.` or applicable punctuation.
- Headers are numbered the format.
    ```
    ---
    
    # N Header 1 Example Name Here
    
    ## N.N Header 2 Example Name Here
    
    ### N.N.N Header 3 Example Name Here
    
    #### N.N.N.N Header 4 Example Name Here
    
    ---
    ```
    - N is decimal numbering.
    - Headers are named with standard `Title Formatting`.
    - The general recommendation is to use horizontal ines on `Header 1` to
      improve readability, however this is not required.
- Links, images, etc are very helpful use them appropriately to make good
  documentation.
- Use header links when possible to make referencing easy.
- Include a listed version of a table of contents for long documentations such
  as this one.
- Point form is with a `- text`.
- Bold is with `**text**`.
- Italics is with `_text_`.
- Horizontal line is with `---`
- Emojis are allowed, but be sensible in usage.
- If code blocks are used do your best to declare the language for clean
  formatting.
- For each directory and major subdirectory that needs to reference pictures,
  include a `pictures` directory to store all files.
- For "**Table of Contents**" use the following:
    ```
    ---
    
    <details markdown="1">
      <summary>Table of Contents</summary>
        
    - [N Header 1 Example Name Here](#n-header-1-example-name-here)
        - [N.N Header 2 Example Name Here](#nn-header-2-example-name-here)
            - [N.N.N Header 3 Example Name Here](#nnn-header-3-example-name-here)
                - [N.N.N.N Header 4 Example Name Here](#nnnn-header-4-example-name-here)
    
    </details>
    
    ---
  
    ...
    ```

---

## 3 Developer Environments: _How We Code_

Developer environments (dev envs or devenvs), are the tools, platforms, and
settings used for coding. They provide a tailored and efficient workspace that
enhances productivity and supports the specific needs of different development
tasks.

All developer environment setup documentation can be found
in [devenvs](devenvs).

### 3.1 Dev Env Documentation Conventions

Speaking of conventions, here are the basic conventions used for quick
readability for dev envs.

1. **Required / mandatory items**: `*`.
2. **Industry standard or very helpful**: `(Recommended)`.
    - Please follow recommendations unless you actually know what you are doing.
3. **Opinionated suggestions**: `(Suggested)`.
4. **OS specific**: `only for ...`.
    - If the key phrase above is not included assume the listed dev env software
      works on all major OS (Windows, macOS, Linux).

---

## 4 Workflow: _How We Code_

Workflows is the process and practices used for project management and the
technical process for completing projects. Key points are to facilitate team
collaboration, maintaining quality and consistency of our work.

All workflow documentation can be found in [workflow](workflow).

---

## 5 GitHub: _How We Version Control_

Version control is a system that records changes to a file or set of files over
time, allowing multiple people to work collaboratively on (usually) software
development. It's crucial for managing code changes, resolving conflicts, and
maintaining a history of project evolution, enhancing teamwork and project
tracking.

- _Technically this section be under a conventions or workflow type header, but
  since it is so important it has its own._

**We use GitHub for all software version control. Often even related project
files such as `stl`, `png`, etc required for documentation is included.**

- Templates for `.gitignore` files in [gitignores](gitignores).
- Repo beginner templates for STM32:
    - [nucleol432kc_template](https://github.com/OntarioTechRacing/nucleol432kc_template).

**GitHub Practices & Guidelines can be found
in [devops.md](conventions%2Fdevops.md)**

---

## 6 Reference / Example Documentation: _How We Research_

- All resources and reference documentation can be found
  in [resources](resources).

---

## 7 Datasheets: _How We Organize_

- All datasheets are stored on
  the [OTR Embedded Software Google Drive](https://drive.google.com/drive/folders/0AHPA2ZoOBCtSUk9PVA).

---

## 999 Archive & Tech Support

- [case_studies.md](resources%2Fcase_studies.md).
- [ace_5030_pc_readme.md](resources%2Face_5030_pc_readme.md).
