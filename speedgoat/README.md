# Speedgoat Guide

[Speedgoat Downloads](https://www.speedgoat.com/extranet#/Downloads)

## I/O Modules

| Modules | No. | Functionality | Additional information |
| ------- |:------:| :------- | :------- |
| [IO291](https://www.speedgoat.com/desktopmodules/2sxc/api/app/SpeedgoatExtranet/api/Downloads/DownloadFile?FolderName=ZwjHhvYZbki5sCYNx0QGgA&fileName=IO291%20-%20Hardware%20Reference%20Manual%20v1.1.pdf)   | 1      | TTL Digital I/O, 0-48V Digital I/O | High-side only |
| [IO691](https://www.speedgoat.com/desktopmodules/2sxc/api/app/SpeedgoatExtranet/api/Downloads/DownloadFile?FolderName=kGF-WHiuh02W5eIwotlAOQ&fileName=IO691%20-%20Hardware%20Reference%20Manual%20v1.2.pdf)   | 2      | CAN communication | |
| [IO393](https://www.speedgoat.com/desktopmodules/2sxc/api/app/SpeedgoatExtranet/api/Downloads/DownloadFile?FolderName=m0aIEr5K8UykTjg1EilzXA&fileName=IO393%20OEM%20Manual.pdf)   | 3      | Serial (RS485), GPIO (RS485), Interrupt, Encoders | FPGA 50k |

## IO291 Pinout
<img src="https://github.com/African-Robotics-Unit/docs/blob/main/speedgoat/IO291%20pinout.jpg" height="300">

## IO393 Pinout
<img src="https://github.com/African-Robotics-Unit/docs/blob/main/speedgoat/IO393%20pinout.jpg" height="300">

## Connections
Please keep this updated
| Pin | Connection |
| ------- | :------ |
| IO393 5a | Boom RS485(+) |
| IO393 6a | Boom RS485(-) |
| IO393 1b | Boom 0V |
| IO393 2b | Boom 5V |
| IO291 1a-4a | Solenoid 1-4 (24V) |
| IO291 9a-13a | Controller Buttons |
| IO291 17a | Controller GND |

| IO691 CAN | Wire Color |
| :------- | :------ |
| Channel 1 (High) | Red |
| Channel 1 (Low) | Blue |
| Channel 2 (High) | Green |
| Channel 2 (Low) | Yellow |

CAN Ground connected to cable shield

## Upgrading Matlab Release
**NB**: This assumes the Speedgoat is already working with a previous release of Matlab on the PC
1. Install the latest release of Matlab from [here](https://www.mathworks.com/downloads)
2. Include the following Add-Ons with the installation
   - Simulink
   - Simulink Coder
   - Simulink Real-Time
   - Simulink Real-Time Target Support Package
3. In Windows Firewall allow the newly installed release of Matlab to communicate with both public **and** private networks
3. Install the Speedgoat I/O Blockset for the Matlab Release from [here](https://www.speedgoat.com/extranet#/Downloads)
4. Update the Speedgoat Software from the Simulink Real-Time Explorer
5. Restart the Speedgoat and Matlab
