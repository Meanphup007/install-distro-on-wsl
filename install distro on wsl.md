
## Step 1 - Enable the Windows Subsystem for Linux :

    dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
``` 
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```
   
## Step 2 - Check requirements for running WSL 2 :

To update to WSL 2, you must be running Windows 10...

    For x64 systems: Version 1903 or later, with Build 18362.1049 or later.
    For ARM64 systems: Version 2004 or later, with Build 19041 or later.

## Step 3 - Enable Virtual Machine feature :

    dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform
```
&#160;&nbsp;&nbsp;&nbsp;Restart your computer using powershell : &#160;&#160;&nbsp;&nbsp;`Restart-Computer`
## Step 4 - Download the Linux kernel update package
```
cd \
```
    Invoke-WebRequest -Uri "https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi" -OutFile "wsl_update_x64.msi" -UseBasicParsing
```
Start-Process -FilePath "wsl_update_x64.msi" -Wait
```
### Install program wsl_update_x64.msi
## Step 5 - Set WSL 2 as your default version

    wsl --set-default-version 2

## Step 6 - Install your Linux distribution of choice

    wsl --list --online

## Step 7 - Update wsl

    wsl --update

## Step 8 -  I Install kali

    wsl --install --distribution kali-linux

## Step 9 - Set default Linux distribution

    wsl --set-default <Distribution Name>
```
wsl --set-default kali-linux
```
