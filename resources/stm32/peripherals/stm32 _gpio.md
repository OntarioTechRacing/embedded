# STM32 Gpio

## What is GPIO ?

GPIO is short-form for General Purpose Input/Output pins, and these are used to control digital
signals (high and low signals).

- GPIO can be configured as `output`, `input` or `input with external interrupt`
- In most cases, GPIO pins can have 1 of 3 pull up/down configurations:
    1. `no pull-up and no pull-down`
    2. `pull-up`
    3. `pull-down`

    - For example, `pull-up` means that when the pin is shorted to ground, the MCU will detect that
      as an input signal

## `.ioc` Configuration

1. Configure GPIO pins

## Code

1. GPIO state variable declaration

    ```C
    /* USER CODE BEGIN 0 */
    
    GPIO_PinState pin_state;
    
    /* USER CODE END 0 */
    ```

2. GPIO output

    ```C
    /* USER CODE BEGIN 3 */
    
    // Set Pin A0 high. This can be used to turn on an LED or activate any other device connected to Pin A0.
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0, GPIO_PIN_SET);
    
    // Delay for some time. This allows you to see the effect of turning the Pin high for a specific duration.
    HAL_Delay(1000); // Delay for 1 second.
    
    // Set Pin A0 low. This can be used to turn off an LED or any other devices connected to Pin A0.
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_0, GPIO_PIN_RESET);
    
    /* USER CODE END 3 */
    ```

3. GPIO input

    ```C
    /* USER CODE BEGIN 4 */
    
    // Read input from Pin B0.
    pin_state = HAL_GPIO_ReadPin(GPIOB, GPIO_PIN_0);
    
    // Check the state of the pin and do something based on the state.
    if (pin_state == GPIO_PIN_SET) {
    // If Pin B0 is high, then whatever the code inside the if statement will execute. 
    } else {
    // If Pin B0 is low, then whatever the code inside the else statement will execute.
    }
    
    /* USER CODE END 4 */
    ```
