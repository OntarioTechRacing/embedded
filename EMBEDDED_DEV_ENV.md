# Embedded Software Development Environment

- Required / mandatory items (header 2 on markdown) marked with a `*`.

---

# Accounts

## [GitHub](https://github.com/)*

- Students can register for the [GitHub Student Developer Pack](https://education.github.com/pack).

---

# Software

## [AnyDesk](https://anydesk.com)*

- Remote access tool.

## [Git](https://git-scm.com/downloads)*

- Version control.

## [Homebrew](https://brew.sh/) (macOS)*

- Package manager for macOS.

## [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html)

- Graphical STM32 microcontroller configuration manager and code generator.
- Following documentation written for version `6.9.1`.

### Installation

Requirements for macOS:

1. [Xcode](https://developer.apple.com/support/xcode/) (Homebrew Xcode packages will work as well).
2. [Rosetta](https://support.apple.com/en-us/HT211861) for computers with Apple Silicon.

Installation:

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

## [GNU ARM Toolchain](https://developer.arm.com/Tools%20and%20Software/GNU%20Toolchain)

## [OpenOCD](https://openocd.org/)

## [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) (Recommended)

- Complete STM32 microcontroller IDE.

## [GitHub Desktop](https://desktop.github.com/) (Recommended)

---

# Workflow
