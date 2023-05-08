# Starting New Flutter Project

 - In Android Studio, go to file -> New -> New Flutter Project
 <p align= "center">
 <img src = "https://github.com/altherwy/IS4904/blob/main/pics/New_Project_Dialog.jpg?raw=true"/>
 
- From the window above, choose **Flutter** from the sidebar and click **Next**. The **Flutter SDK path** should have the location of the flutter SDK. If not, then there exist a problem in installing Flutter. Visit [Installing Flutter](https://docs.flutter.dev/get-started/install)
 <p align= "center">
 <img src = "https://github.com/altherwy/IS4904/blob/main/pics/Project_Name_Dialog.jpg?raw=true"/>

- From the window above,
	- Choose a valid project name in **Project Name**. 
	- Choose a location for the project in **Project Location**.
	- Write a description for the project in **Description**.
	- Choose *Application* in **Project type**.
	- Write the name of your organization in **Orignization**. Or leave it to the default value *com.example*.
	- Choose an android language in **Android language**.
	- Choose an iOS language in **iOS language**.
	- Choose the intended platform for deployment in **Platform**. For our purpose, choose *Android* and *iOS*.
	After choosing the values, click **Next**.

# Run the first program

By default, the Flutter framework creates a counter application that increases a counter whenever a button is clicked. To run the this program, we first need to create a *virtual device* (an emulator).
## Create a virtual device

 1. Go to **Tools** -> **Device Manager**->**Virtual**-> **Create Device** to open **Virtual Device Configuration**.
 2.  In the **category** sidebar, choose **Phone**.
 3. Pick a phone, for example, the *Pixel XL*. After choosing a phone, click **Next**, which will open **System Image** window.
 4. In the **System Image** window, choose an *operating system*, for example, *Q*. The chosen operating system will start downloading. After the operating system finish downloading. Click **Next**, which will open **Android Virtual Device (AVD)** window. 
 5. In then **Android Virtual Device (AVD)** window,
	 a. Choose a name for the phone in **AVD Name**.
	 b. Choose the **Startup orientation** to either *Portrait* or *Landscape*.
	 c. You can leave the rest of the settings as is. 
	 d. Click **Finish** to create the virtual device.
 6. In the **Device Manager** window, click the "*play*" button to run the recently created virtual device. This will open **Emulator** window. 
 7. After a while, the phone will power on and be ready to "*accept*" a Flutter application. 

## Run the counter application
As mentioned earlier, the Flutter framework creates a counter application by default. To run the application,

 1. Go to **Run** -> **Run "main.dart"** to run the application. This will take a while if the application runs for the first time. To check the progress of building the application, check the the bottom right corner of the main window.
 2. After the application loads up the following screen will appear,

<p align = "center">
<img src = "https://github.com/altherwy/IS4904/blob/main/pics/Flutter_Demo_Home_Page.jpg?raw=true"/>

3. To make sure that the application, and Flutter framework, are working properly, press the **plus** button to increase the number underneath "*You have pushed the button this many times:*" by one. If it working properly, the number should increase by one.
4. That's it, you have created and run your first Flutter application.

# Summary
This lecture provides a step-by-step guide to starting a new Flutter project in Android Studio, creating a virtual device to run the project, and running the default counter application.
	
# Troubleshoot

## How to Install Intel HAXM and Configure It with Android Studio

Intel Hardware Accelerated Execution Manager (Intel HAXM) is a hardware-accelerated virtualization engine that enables you to run and test Android apps on your computer faster. This guide will show you how to install Intel HAXM and configure it with Android Studio.

## Prerequisites

- A computer with an Intel processor that supports Intel VT-x technology.
- Android Studio installed on your computer.

## Step 1: Download Intel HAXM

1. Go to the [Intel® HAXM download page](https://github.com/intel/haxm/releases).
2. Scroll down to the "Downloads" section and download the version of Intel HAXM that matches your operating system.

![Screenshot (39)](https://user-images.githubusercontent.com/115354885/236876777-772c2f2a-f15e-4400-879f-b370f444d498.png)

## Step 2: Install Intel® HAXM

1. Open the downloaded file and follow the installation instructions.
2. after the installation is completed, you may want to check if virtualization  is enabled on your computer, to check open task manager → performance virtualization should be enabled

<img width="958" alt="Screenshot 2023-05-08 001548" src="https://user-images.githubusercontent.com/115354885/236876407-0210b708-b2a8-4bc5-a6fc-6c4a60796798.png">


1. if virtualization is disabled then follow this short [youtube video](https://youtu.be/MFuxInYlpN8) to help you enable virtualization  

## Step 3: Configure HAXM with Android Studio

1. Open Android Studio and go to "File" > "Settings" > "Appearance & Behavior" > "System Settings" > "Android SDK".
2. Click on the "SDK Tools" tab and scroll down to "Intel HAXM" in the list of available tools.
3. Check the box next to "Intel HAXM" and click "Apply" to install it.

<img width="956" alt="Screenshot 2023-05-08 090032" src="https://user-images.githubusercontent.com/115354885/236875954-9dd5b56f-b0dd-4b67-8012-d5e4f348cb22.png">

## Step 4: Verify Intel HAXM Installation

1. Open Android Studio and create a new virtual device by going to "AVD Manager" > "Create Virtual Device".
2. Choose a device definition and click "Next".
3. Select a system image that supports Intel HAXM and click "Next".
4. On the "Verify Configuration"  click "Finish".
5. Wait for the virtual device to start up. If Intel HAXM is installed and configured correctly, you should see a message in the Android Studio console that says "Emulator: HAX is working and emulator runs in fast virt mode".

<img width="959" alt="Screenshot 2023-05-08 092021" src="https://user-images.githubusercontent.com/115354885/236875701-2d93197c-ef5c-4d93-8d63-07fe80833e4b.png">

Congratulations! You have successfully installed and configured Intel HAXM with Android Studio. You can now run and test Android apps on your computer faster than ever before.	
