# Setup

## Step-1: Download official package

- First I installed the platform tools(Linux zip) to use the ADB commands for the Android-Home-lab from https://developer.android.com/studio/releases/platform-tools.

## Step-2: Extract 

- I unzipped the folder in my Downloads folder.
	```bash
	cd ~/Downloads
	unzip platform-tools-latest-linux.zip
	```
- Move it to a clean location.
	```bash
	mv platform-tools ~/Android
	```
- Now the path is ~/Android/platform-tools.

## Step-3: Add to PATH

- Then edit the '.bashrc' file, which is a hidden file in /home/user/, usig the tool nano. To see the file write 'ls -a' in this location(/home/user/).
	```bash
	nano ~/.bashrc
	```
- Then write the below command at the bottom of the file.
	```bash
	export PATH=$PATH:$HOME/Android/platform-tools
	```
  export-makes the variable available for the environment i.e. /home/user in my case.
  $PATH-variables are stored here.
- Then reload the file (.bashrc).
	```bash
	source ~/.bashrc
	```

## Step-4: Test

- See what version of adb do you have.
	```bash
	adb version
	```




