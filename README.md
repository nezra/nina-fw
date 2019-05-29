# Wrover-B Fork of the Arduino NINA-W102 firmware

This is my fork of the Arduino NINA-W102 firmware. The original repository is located at https://github.com/arduino/nina-fw

This was forked to allow for use of VSPI on the WRover(PSRam enabled boards) based ESP32's, as the pins used by the WRoom based boards are not available on the Wrover based boards.

#### The pins are assigned as follows:

1. IO23 - MOSI
2. IO19 - MISO
3. IO18 - SCLK
4. IO05 - CS/SS
5. IO33 - Ready 

#### Tested Libraries:

Adafruit's ESP32SPI for CircuitPython
MY fork of ESP32SPI for micropython on the OpenMV

This firmware uses [Espressif's IDF](https://github.com/espressif/esp-idf)

## Building

Download the ESP32 toolchain
Extract it and add it to your PATH: export PATH=$PATH:<path/to/toolchain>/bin
Clone v3.2 of the IDF: git clone --branch v3.2 --recursive https://github.com/espressif/esp-idf.git
Set the IDF_PATH environment variable: export IDF_PATH=<path/to/idf>
Run make firmware to build the firmware (in the directory of this read me)
You should have a file named NINA_W102-x.x.x.bin in the top directory
Use appropriate tools (esptool.py, appropriate pass-through firmware etc) to load this binary file onto your board. make flash also works

## License

Copyright (c) 2018 Arduino SA. All rights reserved.

This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Lesser General Public
License as published by the Free Software Foundation; either
version 2.1 of the License, or (at your option) any later version.

This library is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public
License along with this library; if not, write to the Free Software
Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA
