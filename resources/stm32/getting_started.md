# Ontario Tech Racing: Embedded Software - Getting Started with STM32

Getting started with STM32 microcontrollers for FSAE applications presents a step up from platforms
like Arduino, offering more advanced features and capabilities. While these microcontrollers share
similar programming concepts with Arduino, they come with a steep learning curve to implement
STM32s' superior processing power and flexibility.

---

## 0.0 List of Contents

- [1.0 Intro to STM32](#10-intro-to-stm32)
- [2.0 The Nucleo Board](#20-the-nucleo-board)
    - [2.1 Nucleo-L432KC Pinout](#21-nucleo-l432kc-pinout)
    - [2.2 STM32L432KC Block Diagram](#22-stm32l432kc-block-diagram)
- [3.0 Developing Software for STM32](#30-developing-software-for-stm32)
    - [3.1 GitHub Version Control](#31-github-version-control)
    - [3.2 Integrated Development Environment](#32-integrated-development-environment)
- [4.0 Example Beginner Projects](#40-example-beginner-projects)
    - [4.1 Hello World: Onboard GPIO LED Blinking](#41-hello-world-onboard-gpio-led-blinking)
    - [4.2 First Input: GPIO Push Button Input](#42-first-input-gpio-push-button-input)
    - [4.3 Debug Expansion with Analog: Reading ADC with the Debugger](#43-debug-expansion-with-analog-reading-adc-with-the-debugger)
    - [4.4 Always Reading: ADC with DMA](#44-always-reading-adc-with-dma)
    - [4.5 Reactive system: NVIC](#45-reactive-system-nvic)
    - [4.6 Basic Communication: Arduino to STM32 USART](#46-basic-communication-arduino-to-stm32-usart)
    - [4.7 Not Brainless Design: Scheduler](#47-not-brainless-design-scheduler)
    - [4.8 Advanced Communications: CAN Messaging](#48-advanced-communications-can-messaging)

---

## 1.0 Intro to STM32

The STM32 is a family of 32-bit microcontrollers based on ARM Cortex-M processors, developed by
STMicroelectronics. What sets it apart from other microcontrollers, like those in the Arduino
series, is its advanced features: STM32 offers higher processing power, greater memory capacity, and
more peripherals, like built-in USB controllers, ADCs (analog-to-digital converters), and
communication interfaces.

---

## 2.0 The Nucleo Board

STM32 Nucleo boards are a series of development boards designed around the STM32 microcontrollers.
These boards come in different sizes, mirroring the STM32 microcontroller's diversity:

- Nucleo-32 (compact size)
- Nucleo-64 (medium size)
- Nucleo-144 (largest with advanced features and connectivity)

Examples include the Nucleo-F401RE for high-performance applications, Nucleo-L432KC for
power-efficient designs, and Nucleo-G071RB for general-purpose use. Similar to Arduino boards in
user-friendliness and community support, STM32 Nucleo boards are also Arduino-compatible, allowing
them to use existing Arduino shields, which makes them accessible for Arduino enthusiasts looking
to upgrade to more powerful and feature-rich microcontrollers.

Our department currently uses the *
*[Nucleo-L432KC](https://www.st.com/en/evaluation-tools/nucleo-l432kc.html)** as our primary
development Nucleo. The primary reasons are:

1. CAN support
2. Variety of peripherals
3. Hits all the bare minimum needed specs
4. Small form factor & wide PCB hat board availability

### 2.1 Nucleo-L432KC Pinout

![nucleol432kc_pinout.png](pictures%2Fnucleol432kc_pinout.png)

![pinout_legend.png](pictures%2Fpinout_legend.png)

- Pictures from [os.mbed.com](https://os.mbed.com/platforms/ST-Nucleo-L432KC/)

Notice that the board uses Arduino style connector names (A0, D1, ...). When actually programming
all pin references will be to the MCU pin (PA_1, PB_3, ...). The first "PA" of PA_1 means peripheral
port A and "1" means pin 1.

### 2.2 STM32L432KC Block Diagram

Block diagrams are a simplified graphical representation of a system, breaking down complex
structures into individual components connected by lines that indicate relationships or flows. They
depict the functional workings of a system, highlighting how different parts interact without
delving into detailed specifics. Similar to flowcharts, block diagrams are essential for
conceptualizing, designing, and troubleshooting systems.

![nucleol432kc_block_diagram.jpg](pictures%2Fnucleol432kc_block_diagram.jpg)

- Picture from [ST STM32L432KC Datasheet](https://www.st.com/resource/en/datasheet/stm32l432kc.pdf)

---

## 3.0 Developing Software for STM32

### 3.1 GitHub Version Control

[nucleol432kc_template](https://github.com/OntarioTechRacing/nucleol432kc_template)

### 3.2 Integrated Development Environment

- Recommended for beginners: [stm32_cubeide_setup.md](..%2F..%2Fdevenvs%2Fstm32_cubeide_setup.md)
- Advanced: [stm32_clion_setup.md](..%2F..%2Fdevenvs%2Fstm32_clion_setup.md)

---

## 4.0 Example Beginner Projects

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.1 GPIO Output</summary>

### 4.1 Hello World: Onboard GPIO LED Blinking

Resources:

- [stm32_gpio.md](peripherals%2Fstm32_gpio.md)

Dev Envs:

- [stm32_ide_setup.md](..%2F..%2Fdevenvs%2Fstm32_ide_setup.md)

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.2 GPIO Input</summary>

### 4.2 First Input: GPIO Push Button Input

Resources:

- [stm32_gpio.md](peripherals%2Fstm32_gpio.md)

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.3 ADC + Debugger</summary>

### 4.3 Debug Expansion with Analog: Reading ADC with the Debugger

Resources:

- [stm32_adc.md](peripherals%2Fstm32_adc.md)

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.4 ADC + DMA</summary>

### 4.4 Always Reading: ADC with DMA

Resources:

- [stm32_dma.md](peripherals%2Fstm32_dma.md)

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.5 NVIC with GPIO Input</summary>

### 4.5 Reactive system: NVIC

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.6 USART</summary>

### 4.6 Basic Communication: Arduino to STM32 USART

Resources:

Dev Envs:

- [arduino_prototyping.md](..%2F..%2Fdevenvs%2Farduino_prototyping.md)

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.7 Scheduler</summary>

### 4.7 Not Brainless Design: Scheduler

Resources:

- [stm32_scheduler.md](core/stm32_scheduler.md)
- [stm32_clocks.md](core/stm32_clocks.md)

</details>

---

<details>
  <summary style="font-size: 18px; font-weight: 500; cursor: pointer;">4.8 CAN</summary>

### 4.8 Advanced Communications: CAN Messaging

Resources:

- [stm32_can_bus.md](peripherals%2Fstm32_can_bus.md)

Dev Envs:

- [can_bus_dev_tools.md](..%2F..%2Fdevenvs%2Fcan_bus_dev_tools.md)

</details>
