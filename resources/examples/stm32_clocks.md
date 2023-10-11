# STM32 Clock Configuration using STM32CubeMX

Why is clock configuration important?

1. **Performance & Power Consumption:** STM32s can run at various clock speeds. To put it real
   simple, faster clock speeds allow for faster code execution, but at the cost of higher power
   consumption.
2. **Peripheral Functionality:** Many peripherals (ie: UART, SPI and I2C) require specific clock
   frequencies to function correctly.
3. **Optimized Power Modes:** Different clock configurations are required for entering/exiting
   low-power modes, ensuring efficient energy usage when the MCU is idle.
4. **Stability:** Incorrect clock settings can make the microcontroller unstable or non-functional.

## `.ioc` Configuration

- Clocks are configured in the `.ioc` file via STM32CubeMX

![Clock_Configuration.png](pictures%2Fclock_configuration.png)

1. Navigate to the `Clock Configurations` tab located near the top of the window

    - Within the clock tab, the flow chart runs left to right, going from source to peripheral /
      source
    - Across the entire flowchart you will see boxes representing clock values and prescalers
        - Clock values with units in round brackets `()`
        - Prescalers which act as multipliers and dividers are denoted by `X` and `/` respectively

2. Set the clock source via the PLL Source Mux

    - The typical clock sources are HSE, HSI, LSE or LSI
        - External, internal, high-frequency or low-frequency oscillators
    - Most STM32s will have an internal oscillator (HSI or LSI), but for precision tasks, you might
      have an external crystal (HSE or LSE)

3. Configure the PLL (Phase-Locked Loop)

    - The PPL is a circuit that can multiply the oscillator frequency
    - The PPL is typically the main prescaler that precedes all other prescalers and peripherals
        - For example, if you have an 8 MHz external crystal, and you want your microcontroller to
          run at 72 MHz, you'd use the PLL to multiply the 8 MHz by X 9

4. Resolving clock issues

    - If any boxes turn pink / red, this means improper clock configuration is detected
    - You can manually fix the flagged boxes, you can also click on the "**Resolve Clock Issues**"
      box to try CubeMX will automatically try fixing the issue
