# STM32 CAN Bus

## `.ioc` Configuration

1. Activate CAN
2. CAN bit time calculations 💀

## Code

1. Variable declaration

   ```C
   /* USER CODE BEGIN 0 */
   
   CAN_TxHeaderTypeDef can_tx_header;
   CAN_RxHeaderTypeDef can_rx_header;
   uint8_t can_tx_data[8];
   uint8_t can_rx_data[8];
   uint32_t can_tx_mailbox = 0;
   
   /* USER CODE END 0 */
   ```

2. HAL CAN start

   ```C
   /* USER CODE BEGIN 2 */ 
   
   can_tx_header.StdId = 0x301; // Example CAN ID.
   can_tx_header.RTR = CAN_RTR_DATA; // Data frame.
   can_tx_header.IDE = CAN_ID_STD; // Standard ID.
   can_tx_header.DLC = 8; // Data Length Code.
   
   /* USER CODE BEGIN 2 */ 
   ```

3. CAN filter

   ```C
   /* USER CODE BEGIN CAN1_Init 2 */
   
   // CAN1 filter config START //
   CAN_FilterTypeDef canfilterconfig;
   canfilterconfig.FilterActivation = CAN_FILTER_ENABLE;
   canfilterconfig.FilterBank = 18;
   canfilterconfig.FilterFIFOAssignment = CAN_FILTER_FIFO0;
   canfilterconfig.FilterIdHigh = 0x0000;
   canfilterconfig.FilterIdLow = 0x0000;
   canfilterconfig.FilterMaskIdHigh = 0x0000;
   canfilterconfig.FilterMaskIdLow = 0x0000;
   canfilterconfig.FilterMode = CAN_FILTERMODE_IDMASK;
   canfilterconfig.FilterScale = CAN_FILTERSCALE_32BIT;
   canfilterconfig.SlaveStartFilterBank = 20;
   HAL_CAN_ConfigFilter(&hcan1, &canfilterconfig);
   // CAN1 filter config END //
   
   /* USER CODE END CAN1_Init 2 */
   ```

4. CAN message sending

   ```C
   can_tx_header.StdId = 0x123; // Example CAN ID.
   can_tx_header.RTR = CAN_RTR_DATA; // Data frame.
   can_tx_header.IDE = CAN_ID_STD; // Standard ID.
   can_tx_header.DLC = 8; // Data Length Code.
   
   // Split uint16 to uint8 for CAN message sending.
   can_bit_bang[0] = (uint8_t) (calculated_speed & 0xFF00) >> 8;
   can_bit_bang[1] = (uint8_t) (calculated_speed & 0x00FF);
   can_tx_data[0] = 1;
   can_tx_data[1] = 2;
   can_tx_data[7] = 8;
   HAL_CAN_AddTxMessage(&hcan1, &can_tx_header, can_tx_data, &can_tx_mailbox);
   ```

5. CAN receive interrupt handling

   ```C
   /* USER CODE BEGIN 4 */

   // CAN interrupt START //
   void can1_Service_Rx(CAN_RxHeaderTypeDef pHeader, uint8_t aData[]) {
     switch (pHeader.StdId) {
       case 0x123: // Example CAN ID.
         // Do something...
         break;
       default:
         break;
     }
   }
   
   void HAL_CAN_RxFifo0MsgPendingCallback(CAN_HandleTypeDef *hcan) {
     while (0 < HAL_CAN_GetRxFifoFillLevel(hcan, CAN_RX_FIFO0)) {
       HAL_CAN_GetRxMessage(hcan, CAN_RX_FIFO0, &can_rx_header, can_rx_data);
       can1_Service_Rx(can_rx_header, can_rx_data);
     }
   }
   // CAN interrupt END //
   
   /* USER CODE END 4 */
   ```

## Bit Banging
   
```C
// CAN bit banging (16 -> 8).
uint8_t can_bit_bang[2]; // uint16_t value to 2 uint8_t values to fit CAD data array.

can_tx_header.StdId = 0x123; // Example CAN ID.
can_tx_header.RTR = CAN_RTR_DATA; // Data frame.
can_tx_header.IDE = CAN_ID_STD; // Standard ID.
can_tx_header.DLC = 8; // Data Length Code.

// Split uint16 to uint8 for CAN message sending.
can_bit_bang[0] = (uint8_t) ((calculated_speed & 0xFF00) >> 8);
can_bit_bang[1] = (uint8_t) (calculated_speed & 0x00FF);

// Load into transmit data array.
can_tx_data[0] = can_bit_bang[0];
can_tx_data[1] = can_bit_bang[1];

// Send message.
HAL_CAN_AddTxMessage(&hcan1, &can_tx_header, can_tx_data, &can_tx_mailbox);
```
