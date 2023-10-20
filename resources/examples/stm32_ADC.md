# STM32 ADC

## What is ADC?

In STM32 microcontrollers, ADC stands for Analog-to-Digital Converter. It's a hardware component that converts analog signals (e.g., voltages) into digital values that can be processed by the microcontroller. This allows the STM32 to interact with and make sense of real-world analog data, such as sensor readings or external signals.

## `.ioc` Configuration

1. Pin Configuration:

    Go to the "Pinout & Configuration" tab. Select the pins you want to use for your ADC input channels. These pins should be configured as "Analog" in the "Mode" column.

2. ADC Configuration:

    Go to the "Peripherals" tab and click on "Analog ADC1."
Configure the ADC settings, including the resolution, conversion mode, sampling time, and other parameters, depending on your requirements.
Set up the reference voltage source for the ADC (e.g., VREF+ and VREF-).
Configure the trigger source for ADC conversions if necessary.
Enable or disable the DMA request if you want to use DMA for data transfer.

3. Clock Configuration:

    Go to the "RCC Configuration" tab and configure the clock source and prescaler for the ADC.

4. Configuration of the NVIC (Nested Vector Interrupt Controller):

    Go to the "Configuration" tab.
Enable the ADC interrupts if you plan to use them for handling ADC conversions.


## `.c` Code

1. Start the ADC conversion inside your main loop
```C
HAL_ADC_Start(&hadc1);
   ``` 

2. Inside your while loop

```C
while (1) {
    // Wait for the ADC conversion to complete
    HAL_ADC_PollForConversion(&hadc1, HAL_MAX_DELAY);
    
    // Read the ADC converted value
    uint32_t adcValue = HAL_ADC_GetValue(&hadc1);
    
    // Your application code to process the ADC value
    // You can use adcValue for your specific application.
  }
}
   ```

3. Configuring the ADC (Analog-to-Digital Converter) using the STM32 HAL (Hardware Abstraction Layer) library.

```C
if (HAL_ADC_Init(&hadc1) != HAL_OK) {
    Error_Handler();
  }
  
  sConfig.Channel = ADC_CHANNEL_0; // Replace with your chosen ADC channel
  sConfig.Rank = 1;
  sConfig.SamplingTime = ADC_SAMPLETIME_3CYCLES;
  if (HAL_ADC_ConfigChannel(&hadc1, &sConfig) != HAL_OK) {
    Error_Handler();
  }
}
   ``` 

4. Error Handling 
```C
void Error_Handler(void) {
  // Handle ADC initialization errors here
  while (1) {
    // Error handling code
  }
}

#ifdef USE_FULL_ASSERT
void assert_failed(uint8_t* file, uint32_t line) {
  // User-defined assert_failed() function
  // You can customize error handling here
}
#endif
   ``` 
