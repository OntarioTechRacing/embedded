# Ontario Tech Racing: Embedded Software - NXP S32K1xx MATLAB & Simulink Developer Environment Setup

The following documentation details how to set up MATLAB and Simulink for NXP S32K1xx embedded
development.

---

## Software Installs

### [MATLAB + Add-ons (Listed below)](https://www.mathworks.com/downloads/)* only for Windows

- Some MATLAB packages are only supported for Windows

1. Simulink
2. Embedded Coder
3. Simulink Coder
4. Stateflow
5. NXP Support Package S32K1xx

---

## Step-by-Step Setup

1. Open up MATLAB Add-Ons → Add-On Manager
    - Right-click on the previously installed NXP Support Package S32K1xx and select Open Folder
      ![MATLAB Open NXP Support Package Files.png](pictures%2Fnxp%2FMATLAB%20Open%20NXP%20Support%20Package%20Files.png)
2. Run the `NXP_Support_Package_S32K1xx.m` file
    - If you're new to MATLAB, it's under EDITOR → Run
      ![MATLAB NXP Support Package Script.png](pictures%2Fnxp%2FMATLAB%20NXP%20Support%20Package%20Script.png)
3. The Support Package window should open
    - As of writing (`2023-12-26`), the window for setting up version `4.3` looks like this:
      ![MATLAB NXP Opened install guide.png](pictures%2Fnxp%2FMATLAB%20NXP%20Opened%20install%20guide.png)
4. Follow Steps 1 and 2 to complete
   the `NXP Model-Based Design Toolbox for S32Kxx Automotive Microprocessors Family`
    - After completing each sub-step, the clickable button should turn green
    - The web page for both download `Files` and `License Keys` tabs window should look something
      like this:
      ![MATLAB NXP MBD Page.png](pictures%2Fnxp%2FMATLAB%20NXP%20MBD%20Page.png)
5. Complete Step 1
    - After complete installation you should
      see `NXP Model-Based Design Toolbox for S32Kxx Automotive Microprocessors Family` on the
      Add-On Manager window
      ![MATLAB NXP MBD Installed.png](pictures%2Fnxp%2FMATLAB%20NXP%20MBD%20Installed.png)
6. Full complete setup
    - All sub-step buttons should now be Green
    - Note: Convert `ZIP to MLTBX` may not be required depending on the download process
      ![MATLAB NXP Completed install guide.png](pictures%2Fnxp%2FMATLAB%20NXP%20Completed%20install%20guide.png)

---

## Step-by-Step Initial setup

1. Open up MATLAB and Simulink
2. Open up the `NXP Model-Based Design Toolbox for S32K1xx MCUs` tool box tab
3. Open the `Embedded Coder` app
   ![MATLAB NXP Toolbox Example.png](pictures%2Fnxp%2FMATLAB%20NXP%20Toolbox%20Example.png)
4. Build your model, in this example the "GPIO on S32K144 LED & Button" block is used
5. `Generate Code` or `Build` (generate and flash) to generate code and/or flash the generated code
   ![MATLAB NXP Embedded Coder Build Example.png](pictures%2Fnxp%2FMATLAB%20NXP%20Embedded%20Coder%20Build%20Example.png)
