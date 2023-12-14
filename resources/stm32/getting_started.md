# STM32 Getting Started

Getting started with STM32 microcontrollers for FSAE applications presents an step up from platforms
like Arduino, offering more advanced features and capabilities. While these microcontrollers share
similar programming concepts with Arduino, they come with a steep learning curve to implement
STM32s' superior processing power and flexibility.

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

-
- Nucleo-32 (compact size)
- Nucleo-64 (medium size)
- Nucleo-144 (largest with advanced features and connectivity)

Examples include the Nucleo-F401RE for high-performance applications, Nucleo-L432KC for
power-efficient designs, and Nucleo-G071RB for general-purpose use. Similar to Arduino boards in
user-friendliness and community support, STM32 Nucleo boards are also Arduino-compatible, allowing
them to use existing Arduino shields, which makes them accessible for Arduino enthusiasts looking
to upgrade to more powerful and feature-rich microcontrollers.

### 2.1 Nucleo-L432KC Pinout

![nucleol432kc_pinout.png](pictures%2Fnucleol432kc_pinout.png)

![pinout_legend.png](pictures%2Fpinout_legend.png)

## 3.0 Example Beginner Projects

### 3.1 Hello World: Onboard GPIO LED Blinking

Resources:

- [stm32_gpio.md](peripherals%2Fstm32_gpio.md)

Dev Envs:

- [stm32_ide_setup.md](..%2F..%2Fdevenvs%2Fstm32_ide_setup.md)

### 3.2 First Input: GPIO Push Button Input

Resources:

- [stm32_gpio.md](peripherals%2Fstm32_gpio.md)

### 3.3 Debug Expansion with Analog: Reading ADC with the Debugger

Resources:

- [stm32_adc.md](peripherals%2Fstm32_adc.md)

### 3.4 Always Reading: ADC with DMA

Resources:

- [stm32_dma.md](peripherals%2Fstm32_dma.md)

### 3.5 Reactive system: NVIC

### 3.6 Not Brainless Design: Scheduler

Resources:

- [stm32_scheduler.md](stm32_scheduler.md)
- [stm32_clocks.md](stm32_clocks.md)

### 3.7 Basic Communication: Arduino to STM32 USART

Resources:

Dev Envs:

- [arduino_prototyping.md](..%2F..%2Fdevenvs%2Farduino_prototyping.md)

### 3.8 Advanced Communications: CAN Messaging

Resources:

- [stm32_can_bus.md](peripherals%2Fstm32_can_bus.md)

Dev Envs:

- [can_bus_dev_tools.md](..%2F..%2Fdevenvs%2Fcan_bus_dev_tools.md)
