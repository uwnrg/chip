# What is Marlin
Marlin is a self-containing application that lives directly on the motherboard that controls the real-time movement of the machine.

# How to download & configure Marlin
As of March 2, 2025, we are using Marlin 2.1.1.3, available here: https://github.com/MarlinFirmware/Marlin/releases/tag/2.1.1.3.
1. Download & unzip the downloaded Marlin zipped folder.
2. Replace the downloaded configuration.h and configuration_adv.h files with the ones found in uwnrg/chip/controls/marlin.
3. Using VS Code with the PlatformIO extesion downloaded, ensure that your project folder is your Marlin folder, locate a checkmark icon in the bottom left to compile your code.
4. (For 8-bit boards) Once compiled, still in VS Code, enter the platformio.ini file, locate the build enviornment declaration statement (something like [env:name]), and specify a upload speed and port. Click the arrow icon in the bottom left blue ribbon. This whole step is easier done on the Arduino IDE.
5. (For 32-bit) After compilation, find the firmware.bin file in the Marlin folder in the .pio/build name folder. Put this file on an SD and load it into the printer.
   
*Important:* Once the files are complied, all commented lines are deleted, so it is important to compile only once the configuration files include all data. Our plan is to finish the config. files and compile it once, and redistribute it as one file to eliminate the need to repeat the steps above everytime.

# Important information about the Marlin configuration files
The configuration files are incomplete as of March 2, 2025 due to some unknown parameters as of now. Below are the defined parameters in the config files, as well as the parameters that still need to be defined. The configuration_adv.h file has not been modified from the Marlin source code.

## Configuration.h Parameters
| Parameter     | Value      |
|-----------    |     -------|
|MOTHERBOARD|BOARD_RAMPS_14_EFB|
|SERIAL_PORT|-1 _(USB emulated serial port)_|
|BAUDRATE|250000 _(Default, lower it if line number and checksum errors appear, 115200)_|
|E0|A4988|
|X|A4988|
|Y|A4988|
|Z|A4988|
|EXTRUDERS|1|
|DEFAULT_NOMINAL_FILAMENT_DIA|1.75 _(Default, needs to be revised later)_|
|TEMP_SENSOR_0 & 1 & 2|1 _(on)_|
|X-Min/Max & Y-Min/Max & Z-Min/Max|Configured|
|LCD Controller|REPRAP_DISCOUNT_FULL_GRAPHIC_SMART_CONTROLLER _(unsure)_|
|SDSUPPORT|Enabled _(unsure)_|
|TEMP_STAT_LEDS| Enabled _(unsure as of now if our leds will be used for temp)_|
|*Servo Probes*|Probes have not been enabled, need to figure it out|
|*X&Y Bed Size*|Not Set|
|*Ink Preheat Settings*|Not Set|
|*Temp Sensor Locations*|Not Set|
