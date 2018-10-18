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
See: https://github.com/acamilo/RobotInterfaceBoard/issues/31

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

### Timer distribution for PWM
The ESP32 has 4 timers availible for use in PWM generation. All PWM channels using a given TImer have the same base frequency. Changing the frequency of a channel will change the frequency of other channels. Note the chart for how the PWM channel allocations coorospond to timers:

```
/*
 * LEDC Chan to Group/Channel/Timer Mapping
** ledc: 0  => Group: 0, Channel: 0, Timer: 0
** ledc: 1  => Group: 0, Channel: 1, Timer: 0
** ledc: 2  => Group: 0, Channel: 2, Timer: 1
** ledc: 3  => Group: 0, Channel: 3, Timer: 1
** ledc: 4  => Group: 0, Channel: 4, Timer: 2
** ledc: 5  => Group: 0, Channel: 5, Timer: 2
** ledc: 6  => Group: 0, Channel: 6, Timer: 3
** ledc: 7  => Group: 0, Channel: 7, Timer: 3
** ledc: 8  => Group: 1, Channel: 0, Timer: 0
** ledc: 9  => Group: 1, Channel: 1, Timer: 0
** ledc: 10 => Group: 1, Channel: 2, Timer: 1
** ledc: 11 => Group: 1, Channel: 3, Timer: 1
** ledc: 12 => Group: 1, Channel: 4, Timer: 2
** ledc: 13 => Group: 1, Channel: 5, Timer: 2
** ledc: 14 => Group: 1, Channel: 6, Timer: 3
** ledc: 15 => Group: 1, Channel: 7, Timer: 3
*/
```

When using ESP32PWM objects, changing the frequency will check for timer cross-talk. If you re-set the frequency of a PWM indirectly, the object will print this warning:

```
	WARNING PWM channel 1 shares a timer with 0
	changing the frequency to 330.00 Hz will ALSO change channel 0 
	from its previous frequency of 50.00 Hz
```


## Availible DAC pins
```
25
26
```
These pins when used with analogWrite will produce an 8 bit analog value on the given pin. The value is from 0-3.3v mapped to 0-255 values. The api is to simply use analogWrite().



## Interrupt

For code examples: https://techtutorialsx.com/2017/09/30/esp32-arduino-external-interrupts/

Availible interruptable pins:
```
0-39
```

