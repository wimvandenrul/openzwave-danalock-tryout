# DanaLock and Open-ZWave (.NET)
==================

This tutorial will explain howto open/close the DanaLock using OpenZWave and .NET. This example is a slightly modified version of OpenZWave example.


## Requirements

- Z-Wave Controller: Eg: Z-Stick Gen5 from Aeon Labs
- Visual Studio (I used 2017 RC)
- Dana Lock Circle


## Preparation

1) Install driver (if using Windows):

https://aeotec.freshdesk.com/support/solutions/articles/6000034892-install-z-stick-gen5-drivers-inf-on-windows

2) Go to computer management and take note of the COM port name
Mine is COM6: See this image: 

![Code Pipeline example](readme/2017-01-30 13_51_45-Computer Management.png)




## How to use

1) Open the solution **OZWForm.sln** under **dotnet\examples\OZWForm\src\**


2) **Important**: Edit the network security key under **config\options.xml**

```xml
<Option name="NetworkKey" value="0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x0A, 0x0B, 0x0C, 0x0D, 0x0E, 0x0F, 0x10" />
```

2) In OZWForm edit so the right COM port name is used

```cpp
// Add a driver
m_driverPort = @"\\.\COM6";
m_manager.AddDriver(m_driverPort);
//m_manager.AddDriver(@"HID Controller", ZWControllerInterface.Hid);
```

3) Make sure OZWForm is the startup project.

4) Build and start the solution

You should see 


## Extra help / references

[Open Z-Wave Official website](http://www.openzwave.com/)

[Open Z-Wave Official GitHub](https://github.com/openzwave/)

[Zencys tool](https://aeotec.freshdesk.com/support/solutions/articles/6000110204-zensys)


