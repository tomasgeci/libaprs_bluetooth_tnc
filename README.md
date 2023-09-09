# Arduino UART KISS AFSK1200 TNC Modem

Arduino Nano/Uno TTL UART KISS AFSK1200 TNC based on customized version of LibAPRS.

## Introduction

Arduino UART TNC modem is based on customized version of LibAPRS, allows simultaneously work using both UART and USB-serial port. 
Use this hardware:

- Micromodem shield for Arduino Nano - https://oshpark.com/shared_projects/NjA5xkC7
    - use this schematic: https://github.com/markqvist/MicroModem/blob/master/Design/Schematic.pdf
    - or this schematic: https://unsigned.io/shop/wp-content/uploads/2014/12/Schematic-1.pdf
- or Micromodem from marqvist: http://unsigned.io/micromodem/

## Build

- Download and configure platformio for VScode
- Build and upload

## Interfacing

- TNC TX pin (5V TTL) - D12 - connect to UART RX
- TNC RX pin (5V TTL) - D11 - connect to UART TX
- GND

*use level converter if you plan to connect this TNC to 5V non-tolerant platforms*
*use software compatible with KISS over serial/UART*
*use Arduino USB->serial for basic debug*

### Radio

- use Line, Mic, PTT pin header to interface your radio via appropriate interface

### PC

- use PC, raspberry pi, or any platform with KISS via serial/UART - keep in mind UART TTL levels
- don't use RS232 D9 pins without level conversion, use appropriate UART level converters

### Android (not tested)

- use Bluetooth serial adapter HC-05/HC-06 or similar
- connect
    - Bluetooth TX -> TNC RX
    - Bluetooth RX -> TNC TX
    - GND
    - VCC for Bluetooth module - check if you have 5V or 3.3V module
- pair Bluetooth module with Android phone

*not each module will work out-of-the-box*

### iOS or iPadOS with Aprs.fi application

- use https://github.com/tomasgeci/kiss-ble-uart-tnc kiss BLE UART adapter
- use instructions for BLE connection aprs.fi app with the adapter
- connect
    - adapter TX -> TNC RX
    - adapter RX -> TNC TX (with level converter or resistor)
    - GND
    - VCC for BLE UART adapter (use arduino 5V and GND pins)

## Credits

- https://oshpark.com/shared_projects/NjA5xkC7 *for perfect shield*
- http://unsigned.io/micromodem/ *for Micromodem and libraries*
- https://github.com/sh123/libaprs_bluetooth_tnc *for perfect idea and LibAPRS modifications*

## License

- GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007
