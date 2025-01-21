# Ephemera

This guide offers everything you need to assemble a versatile e-paper picture frame that refreshes its display daily. At its heart is a Waveshare seven-color e-paper display, enhanced with the Floyd-Steinberg Dithering algorithm to give the impression of greater color depth. With the included BMP-Converter, you can easily prepare and customize your own images for display. The frame also supports internet connectivity, allowing you to schedule specific images for special days. Powered by a 1000mAh battery, the setup can run for up to 700 days on a single charge, with convenient recharging available via the ESP32's type-C port.


**Ephemera** is a dynamic e-paper project that brings fresh visual inspiration every day. It curates and displays a new, unique image daily, celebrating the fleeting beauty of each moment. Designed to capture the essence of *ephemera*—the transitory and temporary—this project offers a constantly evolving collection of images, here today and replaced tomorrow.

Whether you're here for daily inspiration, a unique view, or just curious to see what’s new, Ephemera invites you to enjoy each passing frame.

## Features
- **Daily Image Updates:** New content every day to keep things fresh.
- **Minimalist Design:** Clean, distraction-free visuals to let each image stand out.
- **Easy to Extend:** Perfect for those interested in learning about e-paper projects and automation.

---


### Components Used in this Project
To bring **Ephemera** to life, you'll need a carefully chosen set of components to ensure low power consumption and seamless operation. Below is a detailed list of the required parts, along with their approximate costs in DKK, to help you build your own dynamic e-paper display.

- **FireBeetle 2 ESP32-E (61.10 DKK):**  
  A microcontroller designed for low power consumption during deep sleep.  
  [Buy here](https://www.dfrobot.com/product-2195.html)

- **Li-Po 503450 1000mAh 3.7V with PH2.0 connector (~17.20 DKK each):**  
  A rechargeable lithium polymer battery for power supply.  
  *(Dimensions: 5mm (H) x 34mm (W) x 50mm (L))*  
  [Buy here](https://yourlink.com)

- **Micro SD Card Module (~2.80 DKK each):**  
  A module for interfacing with micro SD cards.  
  Operates at 4.5V–5.5V DC with a current range of 0.2mA–200mA.  
  Communicates via a standard SPI interface (3.3V or 5V logic level).  
  Compatible with Micro SD cards (up to 2dB) and Micro SDHC cards (up to 32GB).
  Note this version does not take SDXC cards. Maybe orther card modules will. I have not tested.   
  Control pins:  
  - **GND**: Ground  
  - **3V3**: Power supply  
  - **MISO, MOSI, CLK**: SPI bus  
  - **CS**: Chip select signal pin  
  *(Dimensions: 18mm x 18mm)*  
  [Buy here](https://de.aliexpress.com/item/1005005591145849.html?spm=a2g0o.productlist.main.3.a9e0333916KKv5&algo_pvid=ddaef2a1-d621-4a9a-8b38-0c9e925de657&algo_exp_id=ddaef2a1-d621-4a9a-8b38-0c9e925de657-1&pdp_npi=4%40dis%21EUR%211.85%211.85%21%21%211.96%211.96%21%40210390b817295128395262508eb456%2112000033669348102%21sea%21DE%213852088484%21X&curPageLogUid=DYdi0FD60FO3&utparam-url=scene%3Asearch%7Cquery_from%3A)

- **Waveshare 7.3-inch ACeP 7-Color E-Paper E-Ink Display Module + HAT (~522.80 DKK):**  
  A seven-color e-paper display module with SPI communication, featuring 800×480 resolution.  
  [Buy here](https://www.waveshare.com/7.3inch-e-paper-hat-f.htm)

- **PN2222A Transistor (0.40 DKK each):**  
  A transistor used to cut power to the SD card and e-paper display when in deep sleep mode.  
  [Buy here](https://de.aliexpress.com/item/1005007293537015.html?spm=a2g0o.productlist.main.9.32905903c6guM3&algo_pvid=9ec94767-1576-4d31-880c-33e7947114f7&algo_exp_id=9ec94767-1576-4d31-880c-33e7947114f7-4&pdp_npi=4%40dis%21EUR%210.51%210.51%21%21%213.83%213.83%21%40210385bb17295129980507791e2984%2112000040092381006%21sea%21DE%213852088484%21X&curPageLogUid=xYxhRWW7QW3V&utparam-url=scene%3Asearch%7Cquery_from%3A)

- **Toggle Switch (Optional):**  
  A switch to completely disconnect power from the battery.  
  *(Thread diameter: 5mm)*  
  [Buy here](https://yourlink.com)

- **Printed Case:**  
  A custom 3D-printed case to securely hold all components.

- **Four Heat Inserts and Screws:**  
  M3 screws and heat inserts for assembling the components.  
  [Buy here](https://yourlink.com)

- **Picture Frame:**  
  A standard photo frame compatible with the e-paper display module.  
  [Buy here](https://yourlink.com)

### Total Cost for Essential Components: ~627.50 DKK


---

### Assembly Instructions: Soldering Components to the PCB Board

To begin assembly, carefully solder the components onto the PCB board following the silkscreen markings. The silkscreen provides clear indicators for the placement of each component based on its corresponding number. Refer to the table below for a detailed list of components and their specifications.



### Component List

| **Component Number** | **Part**                         |
|-----------------------|----------------------------------|
| C1, C2               | 22pF                            |
| C3, C4, C5           | 100nF                           |
| D1                   | General Purpose Diode           |
| J1, J2               | Male Connector 01x06 Pin        |
| J3                   | Male Connector 01x08 Pin        |
| J4                   | Male Connector 01x02 Pin        |
| Q1                   | PMOS - LP0701N3-G               |
| R1                   | 10K Resistor                    |
| R2, R3               | 100K Resistor                   |
| SW1                  | Push Button Switch              |
| U1                   | 28 Pin Connector for ATmega328-P|
| Y1                   | 16MHz Crystal                   |

---

### EEPROM & Image Sequence

As the program's logic maintains the position of the image sequence using EEPROM memory, which persists even when powered off. To force the display to restart from the first image, you'll need to clear the EEPROM using the provided erase program before uploading the main program again.

The included `delete-eeprom.ino` will reset the counter to zero, meaning you will be able to show images starting from 'bmp-001'.



*Capture the moment. Tomorrow brings something new.*
