# Raspberry Pi Zero 2 ePaper Display Setup Guide

> **Note**: This is a condensed guide. For complete details, visit the official documentation at [Waveshare's Wiki](https://www.waveshare.com/wiki/7.3inch_e-Paper_HAT_(F)_Manual#Working_With_Raspberry_Pi)

## Hardware Connection
- Connect the ePaper HAT directly to Raspberry Pi's 40PIN header
- Alternative: Use 8PIN cable with following connections:
  ```
  VCC → 3.3V
  GND → GND
  DIN → MOSI (19)
  CLK → SCLK (23)
  CS  → CE0 (24)
  DC  → GPIO 22
  RST → GPIO 11
  BUSY → GPIO 18
  ```

## Software Setup

### 1. Enable SPI
```bash
sudo raspi-config
# Navigate: Interfacing Options → SPI → Yes
sudo reboot
```

### 2. Install Required Libraries
```bash
# Install BCM2835
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.71.tar.gz
tar zxvf bcm2835-1.71.tar.gz
cd bcm2835-1.71/
sudo ./configure && sudo make && sudo make check && sudo make install

# Install lg library
wget https://github.com/joan2937/lg/archive/master.zip
unzip master.zip
cd lg-master
make
sudo make install
```

### 3. Download and Compile Demo
```bash
# Get demo code
git clone https://github.com/waveshare/e-Paper.git
cd e-Paper/RaspberryPi_JetsonNano/

# Compile
cd c
sudo make clean
sudo make -j4 EPD=epd7in3f

# Run demo
sudo ./epd
```

## Troubleshooting
- Verify SPI is not occupied: `ls /dev/spi*` should show `/dev/spidev0.1` and `/dev/spidev0.1`
- Check `/boot/config.txt` for `dtparam=spi=on` entry