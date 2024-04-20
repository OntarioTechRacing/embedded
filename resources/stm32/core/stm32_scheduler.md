# STM32 Scheduler

## .ioc Configuration

1. Activate a timer
2. Set the `prescaler` to match your target counter period, for example = `8000-1`
    - This may / will require calculations using the base clocks configured for the MCU
3. Set the `Counter Period` to match your target counter period, for example = `60000-1`
    - This current example will be showing a clock set for easy real time scheduling

## Code

The following examples use Timer 16 as an example. Your timer selection should be case-by-case
dependant.

1. Timer value variable declaration

   ```C
   /* USER CODE BEGIN 0 */
   
   uint16_t timer_val; // Scheduler timer value.
   
   /* USER CODE END 0 */
   ```

    - Note here that we are using `uint16_t`, this is MCU and timer dependant.
    - Always check the data sheet for more info on the return types of each timer and their
      behaviour

2. HAL TIM start

   ```C
   /* USER CODE BEGIN 2 */
   
   // Timer 16 (Scheduler).
   HAL_TIM_Base_Start(&htim16); // Using TIM16 in PWM mode in this example.
   
   /* USER CODE END 2 */
   ```

3. main while loop implementation

   ```C
   uint32_t timer_val;
   
   /* USER CODE BEGIN WHILE */
   
   while (1) {
     timer_val = __HAL_TIM_GET_COUNTER(&htim16); // Get the timer value.
     if ((timer_val % 1000) == 0) { // Run every 0.1 seconds = 100 ms.
       // Do something ...
     }
   
   /* USER CODE END WHILE */
   ```
