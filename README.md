# Playing with ESP32-S3-Touch-LCD-1.28
This is a `sample-project` to run a `Hello World!` label using [LVGL - Light and Versatile Graphics Library](https://github.com/lvgl/lvgl) library and [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI) with [PlatformIO](https://platformio.org/).

## `platformio.ini` file specification
Important considerations regarding `platformio.ini`, you'll see that has the following `build_flags`:
  ```bash
  -D USER_SETUP_LOADED=1                        ; Set this settings as valid
  -include $PROJECT_LIBDEPS_DIR/$PIOENV/TFT_eSPI/User_Setups/Setup302_Waveshare_ESP32S3_GC9A01.h
  -D USE_HSPI_PORT=1                            ; Fix for when screen doesn't boot up
  -D LV_CONF_PATH="${PROJECT_DIR}/src/config/lv_conf.h"
  ```

1. These are to configure the SPI Pins to communicate with the LCD 1.28 Touch Screen and `USE_HSPI_PORT` to fix the issue for the screen not booting up.
2. [LVGL - Light and Versatile Graphics Library](https://github.com/lvgl/lvgl) - `lv_conf.h` is to configure the library compilation with some custom configuration.



# 1. Pre-requirements
For the first use of this board, make sure to make the following steps to be able to program it.

1. Install CH34x Drivers (MacOS/Windows) and REBOOT 

   a. [CH34x MacOS Driver](https://www.wch.cn/downloads/CH34XSER_MAC_ZIP.html)
   
   b. [CH34x Windows Driver](https://www.wch.cn/downloads/CH341SER_EXE.html)

# 2. Build and Upload - [PlatformIO](https://platformio.org/)

1. Connect Board through USB - [After connecting ESP32-S3-Touch-LCD-1.28 to the PC, long-press BOOT key, single-click the RESET key, and then release the BOOT key to enable it to enter Download Mode.](https://www.waveshare.com/wiki/ESP32-S3-Touch-LCD-1.28)
2. List your devices `pio device list`
    2.1 In MacOS - Look for `/dev/cu.wchusbserial578E0234371` if WCH Driver is installed
3. To build and run: `pio run --upload-port /dev/cu.wchusbserial578E0234371`

<p align="center">
  <img src="https://github.com/user-attachments/assets/899ca0fd-7f4c-4ede-899f-35d2c814276b" alt="Image Description" width="300">
</p>

