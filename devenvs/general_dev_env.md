# General Developer Environment

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Initial Software Installs / Setup](#1-initial-software-installs--setup)
    - [1.1 GitHub*](#11-github)
        - [1.1.1 GitHub Desktop (Recommended)](#111-github-desktop-recommended)
    - [1.2 Git*](#12-git)
    - [1.3 AnyDesk (Recommended)](#13-anydesk-recommended)
    - [1.4 Homebrew*](#14-homebrew)
- [2 Hardware & Equipment](#2-hardware--equipment)
    - [2.1 Saleae Logic Analyzer](#21-saleae-logic-analyzer)
    - [2.2 SEGGER JLink](#22-segger-jlink)
    - [2.3 STLINK](#23-stlink)
    - [2.4 Tag-Connect](#24-tag-connect)
    - [2.5 PEAK PCAN-USB](#25-peak-pcan-usb)
- [999 Resources](#999-resources)

</details>

---

## 1 Initial Software Installs / Setup

### 1.1 GitHub*

[GitHub](https://github.com/).

- Students can register for
  the [GitHub Student Developer Pack](https://education.github.com/pack).

#### 1.1.1 GitHub Desktop (Recommended)

[GitHub Desktop](https://desktop.github.com/).

- Basically just Git with a GUI.

### 1.2 Git*

[Git](https://git-scm.com/downloads).

- Version control.

### 1.3 AnyDesk (Recommended)

[AnyDesk](https://anydesk.com).

- Remote access tool for Ontario Tech Racing's computer resources.

### 1.4 Homebrew*

[Homebrew](https://brew.sh/) only for macOS.

- Package manager for macOS.
- Only required if you have macOS.

---

## 2 Hardware & Equipment

### 2.1 Saleae Logic Analyzer

- Logic analyzer for all the things.
- For FSAE and budget restrictions, the recommendation
  is: [Saleae Logic 8](https://cad.saleae.com/products/saleae-logic-8).
    - Requires software: [Saleae Logic 2](https://www.saleae.com/downloads/).

### 2.2 SEGGER JLink

- JTAG/SWD Debugger, for debug and program flashing.
- For FSAE and budget restrictions, the recommendations
  are: [J-Link EDU](https://www.segger.com/products/debug-probes/j-link/models/j-link-edu/)
  and/or [J-Link EDU Mini](https://www.segger.com/products/debug-probes/j-link/models/j-link-edu-mini/).
    - Requires
      software: [JLink Software](https://www.segger.com/downloads/jlink#J-LinkSoftwareAndDocumentationPack).

### 2.3 STLINK

- STM32 in-circuit debugger and programmer.
- For FSAE and budget restrictions, the recommendations
  are: [STLINK-V3SET](https://www.st.com/en/development-tools/stlink-v3set.html).
    - Requires
      software: [STM32CubeProgrammer](https://www.st.com/en/development-tools/stm32cubeprog.html).
    - Another good software
      resource: [STM32 ST-LINK Utility](https://www.st.com/en/development-tools/stsw-link004.html).

### 2.4 Tag-Connect

- Super compact pogo pin and contact interface.
- Recommended: TC2030 / TC2030.
- [Tag-Connect Solutions for Debuggers & Programmers](https://www.tag-connect.com/debugger-cable-selection-installation-instructions).

### 2.5 PEAK PCAN-USB

[PCAN-USB](https://www.peak-system.com/PCAN-USB.199.0.html?&L=1).

- For CAN communication testing, mostly used with BUSMASTER software.
- [PEAK APIs found here](https://www.peak-system.com/Software.68.0.html?&L=1).
- See [can_bus_dev_tools.md](..%2Fdevenvs%2Fcan_bus_dev_tools.md).

---

## 999 Resources

- [Mbed](https://os.mbed.com/) for board pin-outs and documentation.
    - Particularly nice for STM32 Nucleo board pin-outs.
- [CAN Timing Calculator](http://www.bittiming.can-wiki.info/) for CAN bus clock
  configuration.
