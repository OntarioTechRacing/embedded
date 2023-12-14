# Ontario Tech Racing: Embedded Software

![OTR Logo.png](OTR%20Logo.png)

---

## 0.0 List of Contents

- [1.0 Introduction: _What and Why ES?_](#10-introduction-what-and-why-es)
- [2.0 Conventions, Workflows & Developer Environments: _How We
  Code_](#20-conventions-workflows--developer-environments-how-we-code)
    - [2.1 Conventions](#21-conventions)
    - [2.2 Developer Environments](#22-developer-environments)
    - [2.3 Workflow](#23-workflow)

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

## 2.0 Conventions, Workflows & Developer Environments: _How We Code_

### 2.1 Conventions

Conventions are guidelines or standards (usually) agreed-upon for writing code, such as naming,
formatting, and commenting practices. They are crucial for promoting readability, maintainability,
and uniformity across a codebase, facilitating easier collaboration and debugging.

All department convention guides can be found in [conventions](conventions).

### 2.2 Developer Environments

Developer environments, are the tools, platforms, and settings used for coding. They provide a
tailored and efficient workspace that enhances productivity and supports the specific needs of
different development tasks.

All developer environment setup documentation can be found in [devenvs](devenvs).

- Required / mandatory items (header 2 on markdown) marked with a `*`
- Certain industry standard or very helpful items marked with `(Recommended)`
    - Please follow recommendations unless you actually know what you are doing
- Certain opinionated suggestions marked with `(Suggested)`
- Certain OS specific software will be denoted by the key phrase `only for ...`, if this phrase is
  not included assume it works on all major OS (Windows, macOS, Linux)

|                           Hyperlink                            |                Requirement Type                |
|:--------------------------------------------------------------:|:----------------------------------------------:| 
|           [EMBEDDED_DEV_ENV.md](EMBEDDED_DEV_ENV.md)           |                       *                        |
|     [can_bus_dev_tools.md](devenvs%2Fcan_bus_dev_tools.md)     | (Recommended), * for **FSAE Embedded Systems** |
| [cad_mechanical_design.md](devenvs%2Fcad_mechanical_design.md) |   (Recommended), * for **Embedded Hardware**   |
|        [eda_pcb_design.md](devenvs%2Feda_pcb_design.md)        |   (Recommended), * for **Embedded Hardware**   |
|       [stm32_ide_setup.md](devenvs%2Fstm32_ide_setup.md)       |      (Recommended), * for **STM32 Devs**       |
|   [arduino_prototyping.md](devenvs%2Farduino_prototyping.md)   |                  (Suggested)                   |

### 2.3 Workflow

Workflows is the process and practices used for project management and the technical process for
completing projects. Key points are to facilitate team collaboration, maintaining quality and
consistency of our work.

All workflow documentation can be found in [workflow](workflow).

## 2. Datasheets

- All datasheets are stored on
  the [OTR Embedded Software Google Drive](https://drive.google.com/drive/folders/0AHPA2ZoOBCtSUk9PVA)

## 3. GitHub Repo Setup

- Templates for `.gitignore` files in [gitignores](gitignores)
- Templates for STM32:
    - [nucleol432kc_template](https://github.com/OntarioTechRacing/nucleol432kc_template)

## 4. Reference / Example Documentation

- [resources](resources)

## 5. Archival & Tech Support

- [case_studies.md](resources%2Fcase_studies.md)
- [ace_5030_pc_readme.md](resources%2Face_5030_pc_readme.md)
