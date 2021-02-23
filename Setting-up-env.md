# Setting up the Variables for React Native

In this we will come through the requriements we will be needed to make a feasible application with React Native.

## Prerequisites:

_Softwares':_

1. Node.js: [Download](https://nodejs.org/en/download/)
2. A Code Editor:
   - Visual Studio.
   - Sublime.
3. Android Studio: [Download](https://developer.android.com/studio/)
4. Java Development Kit(JDK): [Download](https://www.oracle.com/in/java/technologies/javase-downloads.html)
5. Python: [Download](https://www.python.org/downloads/windows/)
6. Intel x86 Emulator Accerlator(HAXM): [Download](https://www.youtube.com/watch?v=7_Ny7-y6TRA)

## Setting Up Android Studio

1. Open the Android Studio and Go to Configure(at the bottom-right) and open SDK Manager.
2. In SDK Manager:
   - **SDK Platforms:** Choose the Android Version of ypur choose or remain as it by default.
   - **SDK Tools:** Check the following:
     1. Android SDK Build-Tools.
     2. NDK
     3. Android SDK Command-Line Tools.
     4. Android Emulator.
     5. Android SDK Platform-Tools.
     6. Intel x86 Emulator Accelerartor(HAXM Installer) _IMPORTANT_
   - **SDK Update Sites:** default

Download all the following packages.(Drink Coffee, as it will take alot of time).

:raised_hands: All the packages installed succesfully.
Now its time to Configure the environment variables.

## Configure Environment Variables

Search for setting Enviornment variable and it will open a system property window, where you find a option for Environment Variable.

1. For user setting add a **ANDROID_HOME** variable: give the path of the SDK folder.

`C:\Users\{user_name}\AppData\Local\Android\Sdk`

2. For User Setting ad a **JAVA_HOME** variable:

`C:\Program Files\Android\Android Studio\jre`

3. In Path add the path for SDK-platform tools and Java JDK bin folder path.

`C:\Users\{user_name}\AppData\Local\Android\Sdk\platform-tools`

`C:\Program Files\Java\jdk-14.0.1\bin`

## Emulator settings:

**Configure AVD Manager**
With Emulator we will be able to run your application on a simulator or a virtual device
Go and watch the short video how to add Virtual device through ADK Mangaer.

[watch](https://www.youtube.com/watch?v=HdARMMo0uEY)

To run the Emulator we have to enable our **Virtualization** from the _BIOS setting_.

Can be done through these steps:

1. Restart your computer
2. Open BIOS ( search for your Manufacture computer type on the internet) or press (possibly some variation, but give these a try first)
3. Use the arrow keys to choose the configuration and then search for Virtual technology — sometimes called Intel VTx.
4. Enable it
5. Exit and save the changes in configuration.

Done with all the setting go and read next file and start with your 1st React-Native application. :blush:
