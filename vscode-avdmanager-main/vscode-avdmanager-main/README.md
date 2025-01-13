# Android Virtual Device (AVD) Manager

AVD Manager GUI for Visual Studio Code.

Launch Android Emulator and manage SDK packages without touching the Android Studio😎

Also, welcome to open the issue any about this extension.

inspired by [oognuyh/vscode-android-emulator-helper](https://github.com/oognuyh/vscode-android-emulator-helper)

## Features

### AVD Manager

* AVD create, rename, delete, detail view

### SDK Platforms / Tools

* packages Install, update, delete
* accept SDK licenses

### Emulator

* Launch AVD

## Setup Android SDK

### Requirement
- Install JDK 21 (OpenJDK)

### Steps

1. Create Folder for the `SDK Root Path`  (E.g. C:/android/sdk)
2. Create `cmdline-tools` folder inside the SDK Root
   (E.g. C:/android/sdk/cmdline-tools)
3. Download `Android SDK Command-line Tools`
   [https://developer.android.com/studio#command-line-tools-only](https://developer.android.com/studio#command-line-tools-only)
4. Extract the files. You may get a folder call `cmdline-tools` and rename to `latest`
5. Move `latest` folder to cmdline-tools Folder
   E.g. C:/android/sdk/cmdline-tools/latest

### Folder Structure

* C:/android/sdk/ (SDK Root)
  * cmdline-tools
    * latest (download from android.com)
      * lib
      * bin
        * avdmanager
        * sdkmanager

Remember update `avdmanager.sdkPath` to Android SDK Root Path
It should work fine, if the folder structure is correct.

### Setup guide
# Setup Guide for sharing the SDK to Android Studio, VSCode and VSCode-like tools (E.g. VSCodium)

## Requirement
- Install JDK 8 (Oracle JDK or OpenJDK)

## Preparing the SDK

1. Assume that everything will place in the folder `C:\android-sdk`.
Create folder `C:\android-sdk` and `C:\android-sdk\cmdline-tools`.
    ```
    mkdir C:\android-sdk
    mkdir C:\android-sdk\cmdline-tools
    ```

2. download the SDK command line tool (e.g. `commandlinetools-win-9477386_latest.zip`) from below link
https://developer.android.com/studio#command-line-tools-only

3. open commandlinetools-win-9477386_latest.zip, you will see the `cmdline-tools`
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/92bf94c7-36e7-4a3c-80a2-06fc9b6efb8a)

4. unzip and rename the folder name from `cmdline-tools` to `latest`

5. move the `latest` to `C:\android-sdk\cmdline-tools`.
The SDK folder will be like below
    ```
    C:\android-sdk
    └─cmdline-tools
        └─latest
            ├─lib
            └─bin
              ├─avdmanager.bat
              └─sdkmanager.bat
    ```

6. Set  the environment `ANDROID_HOME` to `C:\android-sdk`
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/7bcbc28e-f728-411f-aa98-13d96a9dba9e)


## Setup the VSCode and VSCode-like tools (E.g. VSCodium)
1. install AVD Manager
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/9f9b7883-ea8d-4281-8a97-d907eaa2de77)

2. Click the Android icon to open the AVD Manager
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/13ae121d-5e86-4281-a4b2-e248077e7f5b)

3. You may see below. Click `Download Emulator` to download the emulator
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/831b166f-6485-4662-9dc3-0de8f4f946f3)

4. If you click download. Wait until you see the `output` showing the download 100%.
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/8f284ec4-0e11-46ba-abbe-91c3288ef080)

5. Restart your VSCode and open AVD manager

6. Complete
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/fc2e40e0-66d1-4db5-89d7-3aaaac1487ad)

## Setup Android Studio

1. Open the Android Studio, Click `More Actions`, `SDK Manager`
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/17fb4e98-9874-4c70-9df7-f2b1ddbf120a)

2. On `Android SDK Location`, Click Edit
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/b372f901-db03-4eec-86ad-ad1de071f29f)

3. Change `Android SDK Location` to the SDK path (e.g. `C:\android-sdk`)
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/8c0ce221-2b48-4443-bc82-20990b01794e)

4. Click Next and complete the setup.
![image](https://github.com/toroxx/vscode-avdmanager/assets/18657712/f1e79982-ed51-4186-ab74-f2a360ea8ce2)


------


After all, the VSCode and Android Studio will share the same SDK tools.

## Extension Settings

### Required

* `avdmanager.sdkPath` : Android SDK Root Path
  The location of the Android SDK Root Path. If blank, it will attempt to find it from the `ANDROID_SDK_ROOT` or `ANDROID_HOME` environment variables.
* `avdmanager.cmdVersion`: Android SDK Command-Line Tools Version (default=latest)

After updating the SDK Path. The AVD Manager will auto lookup all executable paths from the SDK.

### Optional

* `avdmanager.avdmanager`: AVD Manager executable path
* `avdmanager.avdHome`: AVD Home path for AVDManager
* `avdmanager.sdkManager`: SDK Manager executable path
* `avdmanager.emulator`: Android emulator executable path
* `avdmanager.emulatorOpt`: Android emulator execute [options](https://developer.android.com/studio/run/emulator-commandline)

## Commands

* `avdmanager.pkg-update-all` : Update All SDK Package
* `avdmanager.pkg-accept-license` : Accept All SDK Licenses
* `avdmanager.setup-sdkpath` : Update SDK Root Path
* `avdmanager.setup-avdmanager` : Update AVDManage Path
* `avdmanager.setup-sdkmanager` : Update SDKManage Path
* `avdmanager.setup-emulator` : Update Emulator Path

## Screenshot

### AVD Manager

Create AVD [+ Button]

![img](image/README/1647306492723.png)

Create AVD - new AVD Name

![img](image/README/2023-08-01214131.png)

Create AVD - device selection

![img](image/README/2023-08-01214153.png)


Rename AVD [Pen Icon Button]

![img](image/README/1647306376053-2.png)

Open AVD config.ini  [File Button] and Open AVD config folder  [Folder Button]

![img](image/README/202306281147001.png)

Delete AVD [Right Click on AVD Name]

![img](image/README/1647306333965-2.png)


AVD Details [Mouseover on the AVD name]

![img](image/README/1647306806230-2.png)

### SDK Platforms / Tools

Install packages (system-image, platforms, source-code)

![](image/README/1647845727856.png)

Install SDK Tools E.g. Build-tools, cmake, emulator, etc.

![](image/README/1647845760332.png)

Package Detail

![](image/README/1647666693038.png)

Accept All SDK licenses [Double Check icon Button]

Update All SDK Package [Sync icon button]

![](image/README/1647666810384.png)

### Emulator

Launch AVD [Play icon Button]

![img](image/README/1647306185675.png)

Emulator Log

![](image/README/1647845143589.png)
