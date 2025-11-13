# Custom-STM32F1  
Repository for the custom PCB project using the STM32F103 (LQFP48).  
Includes schematic, layout, firmware, and debug setup for LED blink + UART debug interface.

## 📂 Contents  
- `Circuit/` – PCB schematic, layout files, Gerber export  
- `Core/` – STM32CubeIDE project files (Blink + UART debug)  
- `Drivers/` – HAL drivers and peripheral sources  
- `Debug/` – UART test logs and debug configuration  

## 🧩 Features  
- MCU: STM32F103C8T6 (LQFP48)  
- 3.3 V LDO regulator (e.g., RT9193-33GB)  
- 8 MHz crystal oscillator  
- On-board LED on PC13  
- SWD programming header (PA13 = SWDIO, PA14 = SWCLK)  
- UART debug header (PA9 = TX, PA10 = RX)  
- Boot0 jumper for flash/bootloader mode  
- RESET button with 10 kΩ pull-up  

## 🛠 Hardware Setup  
1. Connect 5 V input to board, 3.3 V regulator supplies MCU.  
2. LED: anode → 3.3 V via 330 Ω resistor, cathode → PC13.  
3. SWD header pins: 3.3 V, SWDIO (PA13), SWCLK (PA14), GND.  
4. UART header pins: TX (PA9), RX (PA10), GND → USB-UART adapter.  
5. Ensure BOOT0 = GND for normal boot from flash.  

## 🔧 Firmware Setup & Usage  
1. Open STM32CubeIDE and load the project in `Core/`.  
2. Build the project (LED blink + UART debug functionality).  
3. Connect ST-Link V2 to SWD header and program the MCU.  
4. Open a serial terminal (115200 baud, 8-N-1) to view UART debug messages.  
5. LED on PC13 will blink every 1 second and “LED toggled” output will appear on UART.

## 🎯 Troubleshooting  
- If programming fails → Check SWD pin connections and 3.3 V power.  
- If no UART output → Verify TX/RX orientation and baud rate settings.  
- If LED doesn’t blink → Confirm PC13 wiring and correct board powering.  
- If MCU not detected → Verify BOOT0 = GND and RESET pin high.

## 📄 License & Contribution  
Feel free to use, modify, and contribute to this project by submitting issues or pull-requests.

