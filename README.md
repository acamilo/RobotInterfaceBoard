### Robot Interface Board

This is a breakout board for the ESP32 microcontrollers. Power is provided by 6 AA or 2 LiIon batteries. 

## PCB

![Image of  Board](docs/board.png)

## ESP32Dev Board PINMAP

![Pin Functions](docs/esp32_pinmap.png)

## Pins to Never Use:

0       - This is the boot pin, if held low during a reset it will prevent the device from booting
6-11    - These pins are hookups for external system flash and are used by the system flash. Unless you are extending the chips flash capibilities, do not use these. 
1 and 3 -  these are used to program the device and are serial port pins.

## Input Only pins

34-39 are input only. They have no output modes at all. 

## External Use pins

1 and 3 are the serial port used for programming and print statements. This should not be used for user functions, but can be used if serial functionality is needed.

22 and 21 have 4.7kOhm pullups on them and are connected to the Wii accessory port. These can be used with other i2c devices.

## Availible Servo Pins
```
2
4
12-19
21-23
25-27
32-33
```

See: https://github.com/acamilo/RobotInterfaceBoard/issues/31

## Interrupts syntax

See: https://www.arduino.cc/reference/en/language/functions/external-interrupts/attachinterrupt/

## Controller Axis Mapping

See: https://github.com/madhephaestus/WiiChuck/blob/master/src/Classic.cpp#L80


