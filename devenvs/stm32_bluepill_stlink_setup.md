# Download and Install [drivers](https://www.st.com/en/development-tools/stsw-link009.html)*
    1. Click "Get Latest" beside STSW-LINK009 under "Get Software"
	![ST-Link Drivers](/pictures/stm32ide/STM32_STLink_Drivers.png)
    2. Create or login to ST account
    3. Download zip file for drivers
    4. Extract zip file and run either dpinst_amd64.exe or 
	dpinst_x86.exe, depending on whether you are on a 64-bit machine or 32-bit machine. 

# Debug and Program STM32 Blue Pill with ST-Link 
    1. Using female-to-female jumper wires, connect serial wire debug pins to respective pins on the ST-Link USB Dongle
    (GND to GND, SWCLK to SWCLK, SWDIO to SWDIO, 3.3V to 3.3V)
    2. Open an STM32CubeIDE Project and under "Run Configurations", select STLink for "Debug Probe" and SWD for "Interface"
	![STM32CubeIDE Run Config for SWD](/pictures/stm32ide/STM32CubeIDE_RunConfig_SWD.png)


