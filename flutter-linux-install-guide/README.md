# flutter install step-by-step guide - Linux install (64 bit)

## step 1 : Download the following installation bundles and tools to get started

1. Get the Flutter SDK (latest stable version) - [Official flutter docs](https://flutter.dev/docs/get-started/install/linux#get-the-flutter-sdk)
2. Get the Android Studio - [Download Android Studio](https://developer.android.com/studio)

## step 2 : Create a workspace directory - this folder will contain all your projects, flutter sdk and all its dependencies.

* Create a  folder named "workspace" on your Desktop
* Extract the files downloaded in step 1
* In your Downloads folder, To extract files, Right click on the file => Select "Extract Here"
* Search for folders named "android-studio" & "flutter" in the above extracted folders.
* Move "android-studio" & "flutter" folders into your "workspace" folder created on your Desktop.

Note : By this stage your should have a "workspace" folder on your desktop which contains "android-studio" & "flutter" named folders. Now proceed to step 3

## step 3 : Install Android Studio in Linux (Ubuntu)

Open Terminal, run command :
```
$ cd Desktop/workspace/android-studio/bin
$ ./studio.sh  
```
* ./studio.sh above command is used to run android studio setup wizard
* Once the setup wizard is loaded 
* Select do not import settings
* Click Next
* Select Custom installation
* Select the Dark theme
* SDK Component Setup - Ensure you have tick mark on 
* Android SDK (component required)
* Android Virtual Device  (component required)
* Select all other options as well to save time in future (Optional)
* Now, create "Android" folder inside your workspace directory on your Desktop
* Move the "Sdk" folder which is inside your workspace directory to newly created "Android" folder
* Now, in the android studio wizard , set the sdk location
* Android SDK Location = /home/dev/Desktop/workspace/Android/Sdk
* Note : replace dev in the above sdk path with your username 
* Click on next twice and it will download the required files
* Please check your connection. Internet Connection is required to download the files
* Click on Finish once the download is completed
* Close Android studio

Note : This will create an Android folder in your workspace which will have Android SDK & also install Android Studio and AVD (Android Virtual Device)

## step 4 : Update your PATH variable

* Go to your HOME folder => Options => Show Hidden files
* locate the  .bashrc file in file explorer 
* Create a backup of the .bashrc file or .bash_profile file
* Edit .bashrc file => Right click Open with text editor

```
PATH=$PATH:/home/dev/Desktop/workspace/flutter/bin
PATH=$PATH:/home/dev/Desktop/workspace/Android/Sdk
PATH=$PATH:/home/dev/Desktop/workspace/Android/Sdk/tools
PATH=$PATH:/home/dev/Desktop/workspace/Android/Sdk/platform-tools
PATH=$PATH:/home/dev/Desktop/workspace/android-studio/bin
```

* Add the above lines at the bottom of the .bashrc file
* Click "Save" and exit the file.
* Note : "dev" in the above path is username of our machine. Please replace "dev" inside above lines with your username

### Explanation of the above lines that are added to the .bashrc file

1. flutter bin environment variable
```
PATH=$PATH:/home/dev/Desktop/workspace/flutter/bin
```
Note : replace "dev" inside the above command with your username

2. android sdk environment variables
```
PATH=$PATH:/home/dev/Desktop/workspace/Android/Sdk
PATH=$PATH:/home/dev/Desktop/workspace/Android/Sdk/tools
PATH=$PATH:/home/dev/Desktop/workspace/Android/Sdk/platform-tools
```
Note : replace "dev" inside the above command with your username

3. android studio environment variables
```
PATH=$PATH:/home/dev/Desktop/workspace/android-studio/bin
```
Note : replace "dev" inside the above command with your username

* Verify your updated PATH variable
```
echo $PATH
```

## step 5 : Install Android Studio Plugin
Open android studio using terminal command studio.sh
```
$ studio.sh
```
* Select Configure => Plugins
* Search for Flutter Plugin in the search bar and install
* This will install both flutter and dart plugins
* Restart Android Studio
* New option to create a flutter application is now available in Android Studio
* Click on  "Create flutter application" option
* Enter your app name, sdk location, project location, package name and some other required information
* Click finish
* Android studio will now create a starter flutter project
* Happy Coding...

### Accept android-licenses - Mandatory
```
flutter doctor --android-licenses
```

### Disable Flutter Analytics - Optional
```
flutter config --no-analytics
```

## step 6 : Run flutter doctor to test the environment setup
Note : Keep your linux system up-to-date (System Updates) which helps in installing common dependencies required by flutter
```
$ flutter doctor

 Doctor summary (to see all details, run flutter doctor -v):
    [✓] Flutter (Channel stable, v1.9.1+hotfix.4, on Linux, locale en_US.UTF-8)
 
    [✓] Android toolchain - develop for Android devices (Android SDK version 29.0.2)
    [✓] Android Studio (version 3.5)
    [!] Connected device
    ! No devices available
```
The above command should show all check marks to ensure that flutter installation is complete

## step 7 : Common Errors/Warnings Guide while running flutter doctor command

* Error : Unable to find git in your PATH
Run command  to Install git 2.x
```
sudo apt-get install git
```

* Install dependency only if required by flutter doctor summary
```
sudo apt-get install lib32stdc++6
```

## step 8 : Install Visual Studio Code (Optional)

Get Visual Studio Code Editor - Optional - [Download Visual Studio Code](https://code.visualstudio.com/)
* Get the \. deb file for Ubuntu. Double Click on it and install via Ubuntu Software Center
* Install VS Code Extensions 
    * Flutter
    * Dart => this will automatically be installed with flutter extension
* Go to View Menu => Select Command Palette or Press Ctrl+Shift+P
* Type flutter in the Command Palette window
* Select Flutter:New Project option
* Provide a name to your project
* Select your desired location to store all your projects
* Flutter project will be created
* Start coding...

Note : We can use Android Studio or Visual Studio Code Editor [ANY ONE] to develop flutter apps

## step 9 : Launch your Android Emulator

Launch using Android Studio AVD Manager
* Open Android Studio  
* Navigate to AVD Manager
* Select a device from the list or Create a new device
* Enable Hardware-GLES 2.0
* Select x86 image Android API Level with Google API - latest stable version of Android OS
* Click Next & Finish the Emulator Config Setup
* Click on PLAY BUTTON to start the emulator

Launch using VS Code (Optional)
* Check bottom-right corner of vs code 
* Click on "No Device" option
* Select a emulator from the list
* Click on the device name to start the emulator

### Troubleshooting Android Emulator - Android Emulator not working ?
Error List
* Your CPU does not support required features (VT-x or SVM)
* Please ensure KVM is properly installed
* Error 1 : KVM is required to run this AVD
* Error 2 : User does not have permission to use KVM (/dev/kvm)

Error 1 : KVM is required to run this AVD
* run command :
```
sudo apt-get install qemu-kvm
 or 
sudo apt-get install qemu-kvm libvirt-bin ubuntu-vm-builder bridge-utils ia32-libs-multiarch
```
* Restart your machine

Error 2 : User does not have permission to use KVM (/dev/kvm)
* run command :
```
sudo adduser $USER kvm 
```
above command adds the current user 
```
echo $USER
```
above command  prints current username

* Restart your machine

### Useful Resources

* [Android Developer Reference Docs - Emulator Acceleration](https://developer.android.com/studio/run/emulator-acceleration)
* [Flutter Official Docs](https://flutter.dev/docs)

