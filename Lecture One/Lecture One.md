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
<img src = "https://github.com/altherwy/IS4904/blob/main/pics/Flutter_Demo_Home_Page.jpg?raw=true" width = "30%" height = "600"/>

3. To make sure that the application, and Flutter framework, are working properly, press the **plus** button to increase the number underneath "*You have pushed the button this many times:*" by one. If it working properly, the number should increase by one.
4. That's it, you have created and run your first Flutter application.
