# Make Sure you have Java 8, not 9, 10, or 11

Check your java version by opening CMD and typing 

```
java -version
```

and you should see:

```
java version "1.8.0_181"
Java(TM) SE Runtime Environment (build 1.8.0_181-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.181-b13, mixed mode)
```

If you see anything other than 1.8.something, remove Java then install it from:
  
https://www.java.com/en/download/manual.jsp  

## Install Eclipse and the Sloeber plugin (If the computer doesn't already have it)

Download the eclipse installer from here:

[https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)

![alt text](/docs/downloadEclipseForC.png)

Run the Eclipse installer

![alt text](/docs/runEclipesInstaller.png)

Install the C developemt version. 

![alt text](/docs/selectCversion.png)

Install Eclipse on R drive if using lab machine

![alt text](/docs/installOnRDrive.png)

Once the install is done, open eclipse and go to the workbench. 

![alt text](/docs/openWorkspaceOnR.png)
![alt text](/docs/goToWorkspace.png)

Open

```
Help->Eclipse Marketplace...
```

Search for Sloeber 

![alt text](/docs/installSloeber.png)

Set the workspace to Arduino mode. In the upper right hand corner there is a button with a little yellow plus sign, and when you hover over it is says "pen Perspective". Click that button. Select Arduino. 

Eclipse will restart to load the plugin.

#### Open the Arduino Preferences:

```
Arduino -> Preferences
```

![alt text](/docs/ArduinoPreferences.png)

And start by removing both of the default values for private Hardware and Private libraries:

![alt text](/docs/removePrivatePaths.png)

Under Private Hardware Path, select New.. and search for (where you extracted Arduino)/hardware/ 

Mine looks like:
```
C:\WPIAPPS\arduino-1.8.3\hardware\
```

Under Private Library path, select New.. and search for your user library directory. It is usually in (your users home)\Documents\Arduino\libraries for Windows, or (your users home)/Arduino/libraries for Unix systems. You know you have the right one if the folder contains ESP32Servo, Esp32SimplePacketComs, SimplePacketComs, EspWii and WiiChuck Directories from the library install step above. Remember the location of this folder, it will be where you clone your code in a coming step. 

Mine looks like:
```
C:\Users\harrington\Documents\Arduino\libraries
```
![alt text](/docs/setPrivateFields.png)

# Doxygen and GraphViz
### Windows Doxygen and GraphViz

[Install Doxygen From here](http://doxygen.nl/files/doxygen-1.8.15-setup.exe)

and [GraphViz from here](https://graphviz.gitlab.io/_pages/Download/windows/graphviz-2.38.msi)

Then use [these instructins]( https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/) to set add GraphViz to the path

```
C:\Program Files (x86)\Graphviz2.38\bin
```

### Ubuntu Doxygen and GraphViz

```
sudo apt install doxygen
```
## After the native Doxygen, install the plugin

In eclipse

```
Help->Eclipse Marketplace...
```

Search for 

```
eclox
```

and install it. 

# Setup your project

 [Open Projects in Eclipse using the Eclipse instructions](https://github.com/WPIRoboticsEngineering/RobotInterfaceBoard/blob/master/UseEclipse.md)


# Troubleshooting

## arduinoPlugin\tools\make\make not found in PATH

There can be a currupted download to the Make tools, if this error comes up follow these instructions to correct it
Follow the instructions here : https://github.com/Sloeber/arduino-eclipse-plugin/issues/767



