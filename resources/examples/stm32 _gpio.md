# Stm32 Gpio 

## What is GPIO ?

GPIO is short-form for General Purpose Input/Output pins, and these are generally used to control various external devices and sensors.

## What's the difference between GPIO and CAN ?

GPIO pins are similar to CAN bus, but instead of sending messages over the CAN bus, you can interact with the hardware using GPIO pins. 

## `.ioc` Configuration

1. Configure GPIO pins 

## Code

1. Variable Declaration
   
  ```C

  /* USER CODE BEGIN 0 */

  GPIO_PinState pin_state;

  /* USER CODE END 0 */

  ```

2. GPIO Initialization
   
  ```C

  /* USER CODE BEGIN 2 */

  // GPIO initialization for Pin A0 as output.
  HAL_GPIO_Init(GPIOA, GPIO_PIN_0);

  /* USER CODE END 2 */

  ```
3. GPIO Output

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

4. GPIO Input
   
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
