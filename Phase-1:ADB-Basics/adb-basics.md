# ADB Basics

## What is ADB?
- ADB(Android Debug Bridge) is a tool used to communicate to a device in command-line-interface(CLI).
- It consists of Three components:
	1. adb client - sends the command 
	2. adb daemon - runs the command
	3. adb server - manages communication between the client and daemon

## ADB Commands

### ADB devices:
- It lists all the devices connected to the computer via adb client.
	```bash
	adb devices
	```
	* The 'adb devices -l' command mentions much more details about the connected devices such as connection type, product, model and transport id.
	```bash
	adb devices -l
	```

### ADB shell:
- It is used to remotely connect with the android device and using the shell to enter some UNIX/Linux commands in it.
- This can used for debugging, accessing files or modifying setting in the android  device.
	```bash
	adb shell
	```

### ADB push:
- It is used to push/copy a file from your computer to the Android device.
	```bash
	adb push <file/folder-name> <folder-name>
	```
for eg:
```bash
adb push test.txt /etc/
```
- In an Android device's file system, some of the root files are 'read only'. That means we cannot push, pull, modify the files. Thees files are:
	1. /system
	2. /vendor
	3. /sbin
	4. /root
	5. etc.. 

### ADB pull: 
- This command is used to copy the files from the android device to your computer. 
	```bash
	adb pull <file/folder-name> <folder-name>
	```

## Installing an app:
- To install the app in my Android Device(Spotify), I first installed the .apk file from a trusted source (Uptodown). 
- Then I ran 'adb install' command and I was able to Install the application on my android device.

	```bash
	adb install <file-name.apk>
	```
## Uninstalling an app:
- To uninstall an app from the Device, you first have to know what do you want to uninstall.
- So to list all the packages installed on the android device. Run this command:
	```bash
	adb shell pm list packages
	```
- Then run 'adb uninstall <package-name>' and the package i.e. app will be uninstalled.

## To view system logs: 
- To view system logs adb uses this command:
```bash
adb logcat
```
(To stop the command press Ctrl + C) 
- To view logs in a clean manner run, - 'adb logcat -c'
- To save the logs to file for future analysis, we can simply save them by:
```bash 
adb logcat -d > <file.name>
```

and then to view the logs, just 'nano <file.name>.


	* But without being the root you cannot view all the logs. For that you need to become the root.
 
