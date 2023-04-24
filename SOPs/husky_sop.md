### Pre-Start up checklist

1.	Visually inspect that the Velodyne LiDAR is free to rotate.
2.	The jumper cover is placed on the charging port.
3.	The external hardrive is connected to the PC. 
4.	The key is in the slot and in the locked position 

### Start up procedure

1.	Press the silver toggle switch, wait for the boot procedure
You will know that this is complete when the light under the battery level indicator turns yellow
2.	Power cycle the Stereo Camera
This is achieved by unplugging and plugging in the USB cable from the USB Hub 
3.	Connect to the Husky Wifi 
4.	SSH into the Husky from a terminal window

		ssh -X administrator@CPR-A200-0656

5.	Initialise the stereo camera. 
		
		/setupzedcamera.bash 0 

	Wait for the process to complete

6.	Ensure that the appropriate topics are being published. In a new terminal window run: 
		
		rostopic list

7.	Ensure that images are being published. In a terminal window on your computer run: 

    	export ROS_MASTER=http://CPR-A200-0656:1311
    	rqt_image_view

### Moving the Husky

>NOTE: Before moving the husky, first ensure that it is safe to do so, by clearing any item/s that will interfere with any of the wheels or chassis of the Husky. The husky employs skid steering. Also note that there is only over voltage protection on the motors, meaning the husky can cause damage to objects before shutting off the motors. 

1.	Switch the key to the unlocked position, the light underneath the battery indicator will now turn green. 
2.	Hold down the L1 button. 
3.	Moving the left joystick will now move the Husky in the corresponding direction. 

### Recording Data

1.	Open a new terminal window
2.	Connect to the husky via SSH 

		ssh -X administrator@CPR-A200-0656

3.	once connected type
		
		cd ~/external 

4.	mkdir something_descriptive
5.	cd something_descriptive
6.	Record data using the following command

		rosbag record /topic1 

	>Where /topic is the specific topic concerned with your research. If you are uncertain which topics are available, you can run rostopic list in terminal to see the available topics. You can record multiple topics, separating them by a space eg.

		rosbag record /velodyne_points /camera/image_stereo_image_raw 

	>Note: Misspelled topics will not return an error and instead will record empty bags, linux is also case sensitive so capitalized topics need to be capitalized in the record command as well. 

7.	To stop the recording use Cntl+C with the recording terminal window selected
8.	The recorded bag can be inspected using 
	
		rosbag info

	>This will list the number of messages received for each topic. Should a topic be empty i.e value will is 0 or it is not present entirely, a new recording will be required. 

### Saving Data

1.	Plug HDD into USB hub
2.	Open a terminal window
3.	Connect to the Husky
4.	Run the following command 

		sudo fdisk -l 

	>This returns a list of connected hard drives, the newly connected HDD should be /dev/sdc1 or similar 

5.	Mount the external hard drive

		udisksctl mount -b /dev/sdc1 

6.	Copy the data 

		cp something_descriptive /media/administrator/your_drive/

7.	Unmount the drive

		udisksctl unmount -b /dev/sdc1 

8.	Ensure the data was copied correctly, remove recorded data from the Husky. 
In the same terminal window that was used to copy the data, enter the following commands: 
	
		cd ~/external 
		rm -r something_descriptive

### Storage Procedure

1.	Return the Husky back to the cupboard in the Mechatronics lab. 
2.	Switch the key to the locked position and remove
3.	Return key to hook in kitchen cupboard
4.	Complete the data saving procedure  
5.	Confirm that all scripts are stopped and close all terminals
6.	Press the silver toggle button to switch off the Husky 

### Battery Charging Procedure

1.	Plug charger into wall and switch on wall plug 
2.	Remove charging port cover from Husky 
3.	Insert battery charging connection
4.	Toggle the orange switch on the battery charger
Charging takes approximately 5 hours from empty. The Husky should only be charged when someone is present in the lab to check in periodically or to react if there is an issue. The charger will stop when the battery is full.
5.	When the battery is fully charged, or no one will be present to monitor the charge, switch off the charger by toggling the orange switch 
6.	Remove the charger from the Husky
7.	Place the charging port cover back on the Husky.  
