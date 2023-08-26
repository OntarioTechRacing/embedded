# `CLion + STM32CubeMX` Developer Environment Setup

## Notes

- Currently, the debugger on macOS when using this setup does not work
    - Build and Run have had no documented issues so far however
    - Future TODO

---

## Software Installs

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

### [CLion](https://www.jetbrains.com/clion/download/)* for Windows, Linux & macOS

- **JetBrains's C and C++ IDE.**
- Students can register for
  the [Free Educational Licenses](https://www.jetbrains.com/shop/eform/students).

### [GNU ARM Toolchain](https://developer.arm.com/Tools%20and%20Software/GNU%20Toolchain)* for Windows, Linux & macOS

- **Toolchain for development on Arm based systems.**
- Also available on [Homebrew Version](https://formulae.brew.sh/formula/arm-none-eabi-gcc)

### [OpenOCD](https://openocd.org/)* for Windows, Linux & macOS

- Also available on [Homebrew Version](https://formulae.brew.sh/formula/open-ocd)

### [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html) (Recommended) for Windows, Linux & macOS

- **Complete STM32 microcontroller IDE.**

---

## Step-by-Step Setup

Official documentation:

- JetBrains
  Documentation: [STM32CubeMX projects](https://www.jetbrains.com/help/clion/2023.1/embedded-development.html)

1. Open up CLion `Settings`

2. Add the `Embedded Development Support` plugin for CLion
    - `Settings → Plugins`
      ![CLion Embedded Development Support plugin.png](pictures/stm32ide/CLion%20Embedded%20Development%20Support%20plugin.png?raw=true "CLion Embedded Development Support plugin.png")

3. Add the path for `OpenOCD` and `STM32CubeMX`
    - `Settings → Build, Execution, Deployment → Embedded Development`
      ![CLion Embedded Development OpenOCD and STM32CubeMX path setting.png](pictures/stm32ide/CLion%20Embedded%20Development%20OpenOCD%20and%20STM32CubeMX%20path%20setting.png?raw=true "CLion Embedded Development OpenOCD and STM32CubeMX path setting.png")
    - You can always click the `Test` button to see if the path is valid
    - For Windows the default paths are:
    ```
    C:\Users\**NAME_HERE**\Documents\OpenOCD-20230712-0.12.0\bin\openocd.exe
    C:\Program Files\STMicroelectronics\STM32Cube\STM32CubeMX\STM32CubeMX.exe
    ```
    - For macOS the default paths are:
    ``` 
    /opt/homebrew/Cellar/open-ocd/0.12.0/bin/openocd
    /Applications/STMicroelectronics/STM32CubeMX.app/Contents/Resources/STM32CubeMX
    ```

4. Add the path for `Arm GNU Toolchain` (`arm-none-eabi-gcc`)
    - `Settings → Build, Execution, Deployment → Toolchains`
      ![CLion Build Execution Deployment Toolchains.png](pictures/stm32ide/CLion%20Build%20Execution%20Deployment%20Toolchains.png?raw=true "CLion Build Execution Deployment Toolchains.png")
    - For Windows the default paths are:
    ```
    C:\Program Files (x86)\Arm GNU Toolchain arm-none-eabi\12.3 rel1\bin\arm-none-eabi-gcc.exe
    C:\Program Files (x86)\Arm GNU Toolchain arm-none-eabi\12.3 rel1\bin\arm-none-eabi-g++.exe
    ```
    - For macOS the default paths are:
    ``` 
    /Applications/ArmGNUToolchain/12.3.rel1/arm-none-eabi/bin/arm-none-eabi-gcc
    /Applications/ArmGNUToolchain/12.3.rel1/arm-none-eabi/bin/arm-none-eabi-g++
    ```
    - Note that for macOS you may see a warning
      stating `Your CMake run finished with errors more...`
        - Ignore this error for now, (future TODO)

5. Create (or open) a new CLion STM32CubeMX project
    - `File → New → Project → STM32CubeMX`
      ![CLion new STM32CubeMX project.png](pictures/stm32ide/CLion%20new%20STM32CubeMX%20project.png?raw=true "CLion new STM32CubeMX project.png")
    - Use the appropriate path if you are opening or creating a version controlled project

6. Configure your STM32 `.ioc` file in STM32CubeMX
    - If STM32CubeMX fails to open automatically you can find the newly created `untitled.ioc` on
      the left-hand `Project` file structure viewer
    - You can edit the `.ioc` at any later time, but you should at least select your
      target ST chip or board
    - By default, the target chip will be selected to `STM32F030F4Px`

7. Configure the `Project Manager`
    - `Project Name` = will be the name of your `.ioc`
    - `Toolchain / IDE` = `STM32CubeIDE`
    - `Generate Under Root` = `True`
      ![STM32CubeMX code generation settings.png](pictures/stm32ide/STM32CubeMX%20code%20generation%20settings.png?raw=true "CLion new STM32CubeMX project.png")
    - Verify that your path is correct, notice here I am making the project in `GitHub/untitled`
      repo
      directory

8. Generate code with the... `GENERATE CODE` button

9. Go back to CLion

10. Set the OpenOCD board file via `Select Board Configuration File` popup
    - Select the chip or board you are targeting, the default should be correct
    - Upon returning to CLion this popup should open automatically, if not we can select the board
      file in the following steps manually
      ![CLion Select Board Config File.png](pictures/stm32ide/CLion%20Select%20Board%20Config%20File.png?raw=true "CLion Select Board Config File.png")

11. Open the `Run / Debug Configurations → Edit Configurations...` (top right drop down)
    - By default, CLion should configure the OpenOCD configuration, the dropdown will be
      called `OCD **PROJECT_NAME_HERE**`
    - If this does not happen the dropdown will be labeled `Add Configuration...`
      ![CLion ioc configured.png](pictures/stm32ide/CLion%20ioc%20configured.png?raw=true "CLion ioc configured.png")

12. Verify `Run / Debug Configurations → Edit Configurations...`
    - If the OpenOCD configuration was not generated automatically, click the `+` button in the top
      left and `OpenOCD Download & Run`, then fill in the missing details shown below
    - `Target` = `**PROJECT_NAME_HERE**.elf`
    - `Executable binary` = `**PROJECT_NAME_HERE**.elf`
    - `Debugger` = `Bundled GDB`
    - `Board config file` = `**ST_TARGET_HERE_BOARD_FILE**.cfg`
        - If you did not select a OpenOCD board file previously you can select one manually now
            - Click `Assist...` and a popup with all board files should show up, select your target
              chip or board
    - You can also set the download and reset behaviour here
      ![CLion Edit Configurations.png](pictures/stm32ide/CLion%20Edit%20Configurations.png?raw=true "CLion Edit Configurations.png")

13. Dive in!
    - Use the project file structure view on the left-hand side to see the sorce code
    - Build, Run (flash ST) and Debug are shown in the top mid-to-right
      ![CLion diving in.png](pictures/stm32ide/CLion%20diving%20in.png?raw=true "CLion diving in.png")
