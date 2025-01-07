## Gerber Files and Schematics

The Gerber files and schematics used in this project were sourced from [rob-g2-365](https://github.com/rob-g2-365/waveshare_epaper_picture_frame). This design closely matched the requirements of this project, so instead of designing something similar from scratch, I opted to use and adapt this existing design.

---

## About the PCB Design

The PCB board is built around an **Atmel ATmega328P** microcontroller and can be programmed using the Arduino IDE as an **Arduino Uno**. The circuit is straightforward, with a focus on providing exposed pins for the following connections:
- **External SD Card**  
- **6-Pin Screen Connector**  
- **Battery Connector**  
- **Serial Output Pins** for FTDI connectivity during the initial flashing process  

---

## Flashing the ATmega328P Chip

If you don’t have an FTDI connector, you can use an **Arduino Uno Rev3** to flash the chip. Simply program the chip on the Arduino Uno board, then transfer it back to the PCB for use.

