# Ontario Tech Racing: Embedded Software - Development Environment Documentation

- Required / mandatory items (header 2 on markdown) marked with a `*`.
- Certain industry standard or very helpful items marked with `(Recommended)`.
    - Please follow recommendations unless you actually know what you are doing.
- Certain opinionated suggestions marked with `(Suggested)`.

---

# Initial Setup

## Accounts

### [GitHub](https://github.com/)*

- Students can register for the [GitHub Student Developer Pack](https://education.github.com/pack).

## Resources

- [Mbed](https://os.mbed.com/) for board pin-outs and documentation.
    - Particularly nice for STM32 Nucleo board pin-outs.
- [CAN Timing Calculator](http://www.bittiming.can-wiki.info/) for CAN bus clock configuration.

---

# General Development Environment

## Software

### [AnyDesk](https://anydesk.com)*

- **Remote access tool for Ontario Tech Racing's computer resources.**

### [Homebrew](https://brew.sh/) for macOS*

- **Package manager for macOS.**

### [Git](https://git-scm.com/downloads)*

- **Ontario Tech Racing: Embedded Software department's choice for version control.**

### [GitHub Desktop](https://desktop.github.com/) (Recommended)

- **Basically just Git with a GUI.**

---

# CAN Communication

## Software

### [Vector CANdb++](https://www.vector.com/int/en/products/products-a-z/software/candb/)*

- **All-in-one DBC creation, modification and visualization.**

### [BusMaster](https://rbei-etas.github.io/busmaster/)*

- **Open source tool for data bus simulations, analysis and testing.**

## Drivers

### [PEAK CAN Tool](https://www.peak-system.com/Drivers.523.0.html)

- **Drivers for PEAK CAN Tools.**

---

# (ARM Architecture) STM32 Development Environment

## Software

### [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html)* for Windows, Linux & macOS

- **Graphical STM32 microcontroller configuration manager and code generator.**
- Following documentation written for version `6.9.1`.

**Installation**

Requirements for macOS:

1. [Xcode](https://developer.apple.com/support/xcode/) (Homebrew Xcode packages will work as well).
2. [Rosetta](https://support.apple.com/en-us/HT211861) for computers with Apple Silicon.

Install Steps:

1. Download [STM32CubeMX](http://www.st.com/stm32cubemx).
    - You may be promoted for login, make your own account or get the team account from the lead.
2. Extract (unzip) the download.
3. Install according to OS:
    - **Windows:**
        1. Run `SetupSTM32CubeMX-6.9.1-Win.exe` for the installation wizard.
    - **Linux:**
        1. Allow for executable permissions:
            ```console
            $ chmod 777 SetupSTM32CubeMX-6.9.1
            ```
        2. Run `SetupSTM32CubeMX-6.9.1`.
    - **macOS:**
        1. Run `SetupSTM32CubeMX-6.9.1.app` for the application wizard.

        - If stopped by macOS, open the `Privacy & Security` in System Settings to allow
          running `SetupSTM32CubeMX-6.9.1.app`.
        - If wizard never opens or errors, try:
            ```console
            $ sudo xattr -cr ~/SetupSTM32CubeMX-6.9.1.app.
            ```

### [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) (Recommended) for Windows, Linux & macOS

- **Complete STM32 microcontroller IDE.**

### [GNU ARM Toolchain](https://developer.arm.com/Tools%20and%20Software/GNU%20Toolchain) (Recommended) for Windows, Linux & macOS

- **Toolchain for development on Arm based systems.**
- Also available on [Homebrew Version](https://formulae.brew.sh/formula/arm-none-eabi-gcc)

### [OpenOCD](https://openocd.org/) (Recommended) for Windows, Linux & macOS

- Also available on [Homebrew Version](https://formulae.brew.sh/formula/open-ocd)

### [CLion](https://www.jetbrains.com/clion/download/) (Recommended) for Windows, Linux & macOS

- **JetBrains's C and C++ IDE.**
- Students can register for
  the [Free Educational Licenses](https://www.jetbrains.com/shop/eform/students).

## Workflow

- JetBrains
  Documentation: [STM32CubeMX projects](https://www.jetbrains.com/help/clion/2023.1/embedded-development.html)

---

# (ARM Architecture) NXP Development Environment

---

# (RISC-V Architecture) ESP32 Development Environment

---

# Electronic Design Automation & PCB Development Environment

## Software

### [Altium Designer](https://www.altium.com/products/downloads)* for Windows

- PCB and Electronic Design Automation (EDA) software package for printed circuit boards.
- Students can register for
  the [Altium Education Student License](https://www.altium.com/education/student-licenses).

### [KiCad](https://www.kicad.org/) (Suggested) for Windows, Linux & macOS

---

# Ultra-Quick Prototyping

## Software

### [Arduino IDE](https://www.arduino.cc/en/software)*

- **Complete IDE for Arduino (and many additional) boards.**

---

# Supportive Hardware, Physical UI & Enclosure Development Environment

## Software

### [Siemens NX]()* for Windows

### [SolidWorks]() (Suggested) for Windows

### [AutoDesk Fusion 360]() for Windows & macOS
