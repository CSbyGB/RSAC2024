# Workshops Android Application Pentest

Material for workshops on Android Application Pentest

## My Pentips about Android Application pentest

- [Android Application Pentest - CS by GB](https://csbygb.gitbook.io/pentips/mobile-app-pentest/android)

## My talks about Android Application Pentest

- [My talks about Android Application pentest - CS by GB](https://csbygb.gitbook.io/pentips/talks/android-app)

## My Android Application Pentest playlist on Youtube

- [Android Application pentest - CS by GB](https://www.youtube.com/playlist?list=PLmOgtFgsLe_KqmrLyM2FkeRkedDbzeQ-e)

# Installs & setups for workshop

## Install Android Studio

### decompress the archive

`tar -zxvf android-studio-2023.2.1.25-linux.tar.gz`

### move the decompressed folder to the opt directory

`sudo mv android-studio /opt`

### make a link to the executable

`sudo ln -sf /opt/android-studio/bin/studio.sh /bin/android-studio`

### launch android studio for the first time and follow the wizard

`android-studio`

### create a new blank project

## Install java jdk

`sudo apt install default-jdk`

## Install jadx

On Debian-based distributions you can install jadx directly from the package manager:

`sudo apt install jadx`

Then launch the GUI with:

`jadx-gui`

## Download and install apktool

Download the Linux wrapper script. (Right click, Save Link As apktool)  
Download the latest version of Apktool.  
Rename the downloaded jar to apktool.jar.  

### Move both apktool.jar and apktool to /usr/local/bin. (root needed)

`sudo mv apktool /usr/local/bin; sudo mv apktool.jar /usr/local/bin`  

### Make sure both files are executable. (chmod +x)

`chmod +x /usr/local/bin/apktool`  
`chmod +x /usr/local/bin/apktool.jar`  

Try running apktool via CLI.

## Get the APKs

This repository already contains the workshop APKs:

- `AndroGoat.apk`
- `injuredandroid.apk`
- `pivaa.apk`

### Get pivaa

#### Pivaa by HTBridge

- [Official repo](https://github.com/HTBridge/pivaa)

`git clone https://github.com/HTBridge/pivaa.git`  

The apk is in the folder apks  

> or get the apk from this repo

### Get InjuredAndroid

#### InjuredAndroid by B3nac

- [Official repo](https://github.com/B3nac/InjuredAndroid)

> The official repo is not maintained anymore but we can still play with the apk

You can find it in this repo

### Get AndroGoat

#### AndroGoat by satishpatnayak

- [Official repo](https://github.com/satishpatnayak/AndroGoat)

## Which Android For Pivaa

sdk 26

## Which Android for InjuredAndroid

sdk 29

## Which Android for AndroGoat

sdk 18

# Quick static analysis workflow

1. Open an APK in `jadx-gui` to browse the decompiled Java/Kotlin code, resources, and `AndroidManifest.xml`.
2. Decompile the same APK with apktool to inspect smali code and packaged resources:

`apktool d pivaa.apk -o pivaa_apktool`

3. Compare both outputs:

- jadx is useful for understanding application logic quickly.
- apktool is useful for checking resources, manifest settings, and lower-level smali code.

# Set up proxy on emulator

Export the burp cert (video will be shown during workshop on how to)  
search "cert" in the settings  
Click on "Install cert"  
The burp cert should be in downloads after drag and drop  

In the latest version of android studio you might not find the network settings in the emulator.
To find them uncheck the box in the settings of android studio (see screenshot below):  
![image](https://github.com/CSbyGB/RSAC2024/assets/96747355/d4d7324c-08a6-48b6-be52-71e2ab2f6c8b)

> Source: [stackoverflow](https://stackoverflow.com/questions/70972106/how-to-configure-proxy-in-emulators-in-new-versions-of-android-studio)

