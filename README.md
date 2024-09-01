# Tasmota Modbus Bridge Firmware

This repository provides the necessary steps to flash and configure Tasmota for use as a Modbus TCP bridge. 

## Flashing the Firmware

1. **Flash the Factory Bin**  
   To flash the factory bin file, use the [ESP Web Tools](https://esp.huhn.me).  
   - Select the single partition option.
   - Ensure the start address is set to `0x0`.
   - A detailed guide can be found [here](https://blog.spacehuhn.com/espwebtool).

## Configuring Tasmota as a Modbus TCP Bridge

Once the firmware is successfully flashed, follow these steps to configure your Tasmota device:

1. **Set Up GPIO Pins**  
   Note config device to function as a Modbus bridge. Refer to the image below for correct GPIO configuration:  
   ![image](https://github.com/user-attachments/assets/3c34e77a-ae0b-4214-97ac-918c0b1ebb5d)


2. **Configure Tasmota Device Settings**  
   Open the web console of your Tasmota device and copy-paste the following commands:

   ```shell
   ModbusSerialConfig 8N1
   ModbusBaudrate 9600
   Rule1 on System#Boot do ModbusTCPStart 502 endon
   Rule1 1
   SaveData 1
   ```
