# STM32 Scheduler

## `.ioc` Configuration

1. Activate timer
2. Set a channel for `PWM Generation CH1`
3. Set the `prescaler` = `8000-1`
    - This may / will require calculations using the base clocks configured for the MCU
4. Set the `Counter Period` = `60000-1`
    - This current example will be showing a clock set for easy real time scheduling

## Code

1. HAL TIM start

   ```C
   /* USER CODE BEGIN 2 */
   
   // Timer 16 (Scheduler).
   HAL_TIM_Base_Start(&htim16); // Using TIM16 with PWM in this example.
   
   /* USER CODE END 2 */
   ```

2. main while loop implementation

   ```C
   uint32_t timer_val;
   
   /* USER CODE BEGIN WHILE */
   
   while (1) {
     timer_val = __HAL_TIM_GET_COUNTER(&htim16); // Using TIM16 with PWM in this example.
     if ((timer_val % 1000) == 0) { // Run every 0.1 seconds = 100 ms.
       // Do something ...
     }
   
   /* USER CODE END WHILE */
   ```
