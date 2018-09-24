### Robot Interface Board

The Robot Interface Board (RIB) is a breakout board for the [ESP32-DevKitC Arduino module](https://www.digikey.com/product-detail/en/espressif-systems/ESP32-DEVKITC-32D/1965-1000-ND/9356990). The Dev Kit C is a reference design of the ESP32-WROOM-32 module which houses the WiFi and bluetooth Antenae. The ESP32-WROOM-32 module houses an ESP32 microcontroller. 

#### Datasheet

Arduino compatiple DevkitC : https://esp-idf.readthedocs.io/en/latest/get-started/get-started-devkitc.html

ESP32 Microcontroller: https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf

#### Driver

https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers

## PCB

![Image of  Board](docs/board.png)

## ESP32Dev Board PINMAP

![Pin Functions](docs/esp32_pinmap.png)

## Pins to Never Use:

0       - This is the boot pin, if held low during a reset it will prevent the device from booting

6-11    - These pins are hookups for external system flash and are used by the system flash. Unless you are extending the chips flash capibilities, do not use these. 

1 and 3 -  these are used to program the device and are serial port pins.

## Input Only pins

34-39 are input only. They have no output modes at all. Analog input and digital input are availible.
```
35
34
39
36
```
## External Use pins

1 and 3 are the serial port used for programming and print statements. This should not be used for user functions, but can be used if serial functionality is needed.

22 and 21 have 4.7kOhm pullups on them and are connected to the Wii accessory port. These can be used with other i2c devices.

## Availible Servo/PWM/AnalogWrite Pins
```
2
4
5
12-19
21-23
25-27
32-33
```

## Availible DAC pins
```
25
26
```
These pins when used with analogWrite will produce an 8 bit analog value on the given pin. The value is from 0-3.3v mapped to 0-255 values. The api is to simply use analogWrite().


See: https://github.com/acamilo/RobotInterfaceBoard/issues/31

## Interrupt

For code examples: https://techtutorialsx.com/2017/09/30/esp32-arduino-external-interrupts/

Availible interruptable pins:
```
0-39
```

