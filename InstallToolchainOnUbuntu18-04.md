## Installing the esp32 toolchain on Ubuntu 18.04

These instructions must be followed in order.

1. Download and install the Arduino IDE from Arduino directly [here](https://www.arduino.cc/en/main/software).
Do not install from the PPA.

2. Add the esp32 board by following [these instructions](https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/boards_manager.md).
Then in Tools > Board select `ESP32 Dev Module`.

3. Install the libraries according to [these instructions](https://github.com/WPIRoboticsEngineering/RobotInterfaceBoard#which-libraries).
Make sure to find the correct section for your class (i.e. 1001, 2001, 2002).

4. In a terminal, run `sudo apt install -y python-pip`. After that finishes, run `pip2 install --user pyserial`.

5. You will now be able to compile the template project.
