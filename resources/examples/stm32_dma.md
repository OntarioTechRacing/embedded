# STM32 DMA

## What is DMA?

DMA, which stands for Direct Memory Access, is a feature in STM32 microcontrollers that allows for efficient data transfer between peripherals and memory without involving the CPU. It essentially offloads data transfer tasks from the CPU, making the system more efficient and responsive.

Here's a simple explanation of how DMA works with STM32:

1. Instead of the CPU managing data transfer between peripherals (like ADC, USART, or SPI) and memory, the DMA controller takes over this task.

2. You configure the DMA controller to specify the source (peripheral) and destination (memory) addresses and the amount of data to transfer.

3. When a trigger condition is met (e.g., data ready from a sensor), the DMA controller automatically moves the data from the peripheral to the memory or vice versa.

4. This frees up the CPU to perform other tasks, making your STM32 microcontroller more efficient and responsive.

In summary, DMA in STM32 simplifies and accelerates data transfer between peripherals and memory by offloading the CPU, enhancing the overall system performance.

## `.ioc` Configuration

1. Pin Configuration:

    Configure your GPIO pins for the specific peripheral (e.g., ADC, USART, SPI) you want to use with DMA. This is usually the first step, as DMA is often associated with peripherals.

2. Configure the DMA:

   Select the "Peripherals" tab on the left panel.
   Choose the peripheral you want to use with DMA (e.g., USART, ADC, SPI).
   Enable the DMA request or stream associated with that peripheral.
   Configure the direction (e.g., peripheral-to-memory or memory-to-peripheral), data size, and other relevant settings.
3. Configure Memory-to-Memory Transfer (Optional):

    If you want to perform memory-to-memory transfers, you can configure a memory-to-memory DMA channel. This is useful for tasks like memory copying.

4. Assign DMA Channels and Streams:

   In the "Project Manager" tab, go to "Middleware & Hardware Abstraction Layer (HAL)" > "DMA Settings."
   Assign the available DMA channels and streams to specific peripherals and memory locations. This step specifies which DMA channel/stream is associated with a particular peripheral.


## `.c` Code

1. Define the source and destination buffers

```C
uint32_t sourceBuffer[10];
uint32_t destinationBuffer[10];
   ``` 

2. Function to configure and start a DMA transfer
```C
// Initialize the HAL DMA handle
    DMA_HandleTypeDef dmaHandle;
    
    // Configure the DMA handle with the desired settings
    dmaHandle.Instance = DMA1_Stream0;  // Replace with your specific stream
    dmaHandle.Init.Channel = DMA_CHANNEL_0;  // Replace with the appropriate channel
    dmaHandle.Init.Direction = DMA_MEMORY_TO_MEMORY;  // Set to DMA_PERIPH_TO_MEMORY if needed
    dmaHandle.Init.PeriphInc = DMA_PINC_DISABLE;
    dmaHandle.Init.MemInc = DMA_MINC_ENABLE;
    dmaHandle.Init.PeriphDataAlignment = DMA_PDATAALIGN_WORD;
    dmaHandle.Init.MemDataAlignment = DMA_MDATAALIGN_WORD;
    dmaHandle.Init.Mode = DMA_NORMAL;
    dmaHandle.Init.Priority = DMA_PRIORITY_HIGH;
    
    // Initialize the source and destination addresses
    dmaHandle.Instance->M0AR = (uint32_t)sourceBuffer;
    dmaHandle.Instance->PAR = (uint32_t)destinationBuffer;
    dmaHandle.Init.PeriphInc = DMA_PINC_ENABLE; // Enable if using peripheral-to-memory
    
    // Initialize and start the DMA transfer
    HAL_DMA_Init(&dmaHandle);
    HAL_DMA_Start(&dmaHandle, (uint32_t)sourceBuffer, (uint32_t)destinationBuffer, sizeof(sourceBuffer) / sizeof(sourceBuffer[0]));
    
    // Wait for the DMA transfer to complete (optional)
    HAL_DMA_PollForTransfer(&dmaHandle, HAL_DMA_FULL_TRANSFER, HAL_MAX_DELAY);


   ```

3. Main Function :

```C
int main(void) {
    // Initialize HAL and system clock
    
    // Configure and start the DMA transfer
    startDMA();
    
    // Your main application code here
    
    while (1) {
        // Your application code
    }
}
   ``` 


