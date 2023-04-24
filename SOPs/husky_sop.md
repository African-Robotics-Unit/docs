# **CLEARPATH HUSKY SOP**
This document contains all the information relevant to operating the Clearpath Husky. The SOP is meant to be read in sequence however relevant sections can be referenced when needed. 

Please read the whole document at least once before first operation. 

## **Husky Info**
Model: [A200-0656](datasheets/husky/husky_datasheet.pdf)  
User Manual: [Clearpath Husky User Manual](https://docs.clearpathrobotics.com/docs/robots/outdoor_robots/husky/user_manual_husky/)  
ROS Version: [ROS 2 - Foxy Fitzroy](https://docs.ros.org/en/foxy/index.html)  
Main Stereo Camera: [Zed2i](datasheets/husky/zed2i_datasheet.pdf)  
VO Stereo Camera: [Bumblebee 2](datasheets/husky/bumblebee2_datasheet.pdf)  
GPS Module: [Garmin x18](datasheets/husky/garmin_x18_datasheet.pdf)  
LiDAR Module: [Velodyne HDL32E](datasheets/husky/velodyne_hdl-32E_datasheet.pdf)

## **Procedures**
### **Pre-Start up checklist**

1.	Visually inspect that the Velodyne LiDAR is free to rotate.
2.	The jumper cover is placed on the charging port.
3.	The external hardrive is connected to the PC. 
4.	The key is in the slot and in the locked position 

### **Start up procedure**

1.	Press the silver toggle switch, wait for the boot procedure
	>You will know that this is complete when the light under the battery level indicator turns yellow
2.	Power cycle the Stereo Camera
	>This is achieved by unplugging and plugging in the USB cable from the USB Hub 
3.	Connect to the Husky Wifi  		
4.	SSH into the Husky from a terminal window

		ssh -X administrator@CPR-A200-0656

5.	Initilise the Husky. 
		
		. aru_bringup.bash 

	Wait until you see images in ZED Explorer. Once you close the window the process will continue. 

6.	Ensure that the appropriate topics are being published. In a new terminal window run: 
		
		ros2 topic list
    	

### **Moving the Husky**

>NOTE: Before moving the husky, first ensure that it is safe to do so, by clearing any item/s that will interfere with any of the wheels or chassis of the Husky. The husky employs skid steering. Also note that there is only over voltage protection on the motors, meaning the husky can cause damage to objects before shutting off the motors. 

1.	Switch the key to the unlocked position, the light underneath the battery indicator will now turn green. 
2.	Hold down the L1 button [low speed] or R2 button [High Speed]. 

	> When moving the Husky indoors, L1 should be primarily used unless safe to use R1
3.	Moving the left joystick will now move the Husky in the corresponding direction. 

### **Recording Data**

Under Construction 👷🚧🏗️


### **Saving Data**

1.	Plug HDD into USB hub on the Husky
2.	Open a terminal window
3.	Connect to the Husky
4.	Run the following command 

		sudo fdisk -l 

	>This returns a list of connected hard drives, the newly connected HDD should be /dev/sdc1 or similar 

5.	Mount the external hard drive - Replace "dev/sdc1" with your harddrive name

		udisksctl mount -b /dev/sdc1 

6.	Copy the data 

		cp something_descriptive /media/administrator/your_drives_name/

7.	Unmount the drive

		udisksctl unmount -b /dev/sdc1 

8.	Ensure the data was copied correctly, once you are confident you have copied the data. Remove your recorded data from the Husky. 
In the same terminal window that was used to copy the data, enter the following commands: 
	
		cd ~/external 
		rm -r something_descriptive

### **Storage Procedure**

1.	Return the Husky back to the cupboard in the Mechatronics lab. 
2.	Switch the key to the locked position and remove
3.	Return key to hook in kitchen cupboard
4.	Complete the data saving procedure  
5.	Confirm that all scripts are stopped and close all terminals
6.	Press the silver toggle button to switch off the Husky 

### **Battery Charging Procedure**
> Note: The Husky datasheet assumes that they Husky has a Lead Acid Battery installed. The Husky that we have has a LiIon battery upgrade. 

1.	Plug charger into wall and switch on wall plug 
2.	Remove charging port cover from Husky 
3.	Insert battery charging connection
4.	Toggle the orange switch on the battery charger  

	>Charging takes approximately 5 hours from empty. The Husky should only be charged when someone is present in the lab to check in periodically or to react if there is an issue. The charger will stop when the battery is full.
5.	When the battery is fully charged, or no one will be present to monitor the charge, switch off the charger by toggling the orange switch 
6.	Remove the charger from the Husky
7.	Place the charging port cover back on the Husky.  
