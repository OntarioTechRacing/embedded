# NXP S32 Design Studio Developer Environment Setup

The following documentation details how to set up NXP's
official [S32 Design Studio](https://www.nxp.com/design/design-center/software/development-software/s32-design-studio-ide:S32-DESIGN-STUDIO-IDE)
IDEs.

- 3 main versions are provided: S32, ARM and Power Architecture as shown below.

<details markdown="1">
  <summary>NXP S32 Design Studio Version Table (Picture)</summary>

![MATLAB NXP S32DesignStudio Versions.png](pictures/nxp/MATLAB%20NXP%20S32DesignStudio%20Versions.png)

</details>

---

<details markdown="1">
  <summary>Table of Contents</summary>

- [1 Initial Software Installs / Setup](#1-initial-software-installs--setup)
    - [1.1 S32 Design Studio for S32 Platform*](#11-s32-design-studio-for-s32-platform)
    - [1.2 S32 Design Studio for ARM Version*](#12-s32-design-studio-for-arm-version)
    - [1.3 S32 Software Development Kit for S32K1 (RTM) (Recommended)](#13-s32-software-development-kit-for-s32k1-rtm-recommended)

</details>

---

## 1 Initial Software Installs / Setup

> **_Note that majority, if not all, NXP software applications will require a
license key. Typically, it is generated on the same portal for downloads,
however for these applications, license keys may be sent via email._**

### 1.1 S32 Design Studio for S32 Platform*

[S32 Design Studio for S32 Platform](https://www.nxp.com/design/design-center/software/development-software/s32-design-studio-ide/s32-design-studio-for-s32-platform:S32DS-S32PLATFORM)
only for Windows and Linux.

- As of writing (2024-01-03), the recommended version is `3.5`.
  ![MATLAB NXP S32DesignStudio S32 Page.png](pictures/nxp/MATLAB%20NXP%20S32DesignStudio%20S32%20Page.png)

### 1.2 S32 Design Studio for ARM Version*

[S32 Design Studio for ARM Version](https://www.nxp.com/design/design-center/software/development-software/s32-design-studio-ide/s32-design-studio-for-arm:S32DS-ARM)
only for Windows and Linux.

- As of writing (2024-01-03), the recommended version is `1.3`.
  ![MATLAB NXP S32DesignStudio ARM Page.png](pictures/nxp/MATLAB%20NXP%20S32DesignStudio%20ARM%20Page.png)

### 1.3 S32 Software Development Kit for S32K1 (RTM) (Recommended)

[S32 Software Development Kit for S32K1 (RTM)](https://www.nxp.com/design/design-center/software/development-software/s32-sdk/s32-software-development-kit-for-s32k1:S32SDK-ARMK1)
only for Windows.

- General SDK which includes drivers required for design studio to work.
- **You can also install this manually on the `Extensions and Updates` window in
  S32 Design Studio for S32 Platform!**
    - Installing it directly on the IDE might help avoid compatability issues,
      but installing it separately might also save some time.
