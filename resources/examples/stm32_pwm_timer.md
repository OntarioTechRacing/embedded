# STM32 PWM Timer Generation using STM32CubeMX

Why are PWM Timers important?

1. **Controlled Power Delivery:** The best way to control the average amount of power delivered, used by sending pulses are regular clock intervals. 
   

## `.ioc` Configuration

- Clocks are configured in the `.ioc` file via STM32CubeMX

![ioc_file_home_page.png](pictures%2Fioc_file_home_page.png)

1. Navigate to the `Pinout & Configuration ` tab located near the top of the window.

    - On the right, you can see a picture of the STM32 microcontrollers with all the basic peripherals initialized.
    - On the left, you can see a menu that outlines different pinout capabilities.

2. Click on `Timers` to reveal the drop-down within the menu on the left.


3. Click on the timer you wish to use for the PWM output.

    - Use timer 1 if it is not being utilized for a different purpose.

4. Select Channel1 to be the PWM Generation CH1 under the modes tab.
    - Select the clock source based on your needs. 
    - Ensure all other channels and features are disabled unless otherwise needed for the project.
    - A pin should be auto-selected to be the clock output and will appear green on the STM32 peripheral diagram.

5. Configure the clock based on the project requirements under the configuration tab.
    - Formulas for the different configuration and duty cycles can be found online. 

6. Once you have generated the code, use the following command to start the timer: 

```C
HAL_TIM_PWM_Start(&htim1, TIM_CHANNEL_1);
```
7. To set a specific frequeny for the PWM, use the following code: 

```C
htim1.Instance = TIM1;
    htim1.Init.Prescaler = 79; // Prescaler
    htim1.Init.CounterMode = TIM_COUNTERMODE_UP;
    htim1.Init.Period = 999; // Period for 1 kHz frequency
    htim1.Init.ClockDivision = TIM_CLOCKDIVISION_DIV1;
    htim1.Init.RepetitionCounter = 0;
    htim1.Init.AutoReloadPreload = TIM_AUTORELOAD_PRELOAD_DISABLE;
    if (HAL_TIM_PWM_Init(&htim1) != HAL_OK)
    {
        Error_Handler();
    }
```
Note: Use the following formula to calculate your values:
Timer Frequency = System Clock Frequency / ((Prescaler - 1) * (Period + 1))

