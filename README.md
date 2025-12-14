# 🚀 Windows 11 Max FPS Optimization
Boost your Windows 11 performance for NVIDIA GPUs 🖥️🎮

[![Windows](https://img.shields.io/badge/OS-Windows%2011-blue)](https://www.microsoft.com/en-us/windows)
[![GPU](https://img.shields.io/badge/GPU-NVIDIA-green)](https://www.nvidia.com/)
[![License](https://img.shields.io/badge/License-MIT-blue)](LICENSE)

## 📑 Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Basic Optimization](#basic-optimization)
- [NVIDIA Optimization](#nvidia-optimization)
- [Debloating Windows](#debloating-windows)
- [Latency & Accuracy](#latency--accuracy)
- [Power & Network & SSD Settings](#power--network--ssd-settings)
- [Overclock & Priority](#overclock--priority)
- [Deep Tweaks](#deep-tweaks)
- [Warning](#warning)

## Introduction
This project was originally created when I was 11 years old. Over time, I refined it into a complete optimization guide for Windows 11 NVIDIA systems at 11. This optimizations will make your PC maximum performance that works for Windows 11 for High-End PC's with NVIDIA GPU. Here is steps that you have to do.

> ⚠️ **Disclaimer:** Apply changes at your own risk. I take no responsibility for any temporary or permanent system damage. If unsure, dont do this settings. These tweaks are for advanced users only, some tweaks may reduce system stability or security. Do NOT apply everything blindly. Read each section first.

## Prerequisites
> ⚠️ **Warning:** Before tweaking, always create a restore point. These tweaks are for NVIDIA GPUs only.

## Basic Optimization
In settings do these:

```bash
1. System > Display > Graphics > Optimizations for windowed games: Off
1. System > Display > Graphics > Advanced graphics settings > Hardware accelerated GPU scheduling: On
2. System > Display > Advanced display > Refresh rate: Max avaliable
3. Gaming > Game Mode: On
4. Privacy & security > Recommendations & offers > Toggle off everything
```

### 1. Task Scheduler
Run Task Scheduler, enter Task Scheduler Library and disable everything that you dont need by right clicking on them and choosing "Disable".

### 2. Services
Press Win+R and write msconfig and run.
Then go to Services and tick "Hide all Microsoft services".
Then untick everything you dont use.

### 3. Memory Integrity
Disable Memory Integrity in Settings.

> 💡 **Tip:** While Memory Integrity improves performance, it might reduce safety against malware.
### 4. Visual Effects & Virtual Memory
Run View advanced system settings and go to:

```bash
Advanced > Performance Settings > Visual Effects
```

Then choose adjust for best performance and apply.

Do this only if you have 16 GB or less RAM:
Then from there go to:

```bash
Advanced > Virtual Memory > Change
```

Then untick "Automatically manage paging file size for all drivers.
Then choose Custom size and set the values to shown:

```bash
Initial Size: 16000
Maximum Size: 16000
```

Then click Set, OK and Apply in order.

## NVIDIA Optimization
Install NVIDIA App, from there update GPU driver and go to Settings and disable overlay and game filters and photo mode.
Go to NVIDIA Control Panel and tick Use the advanced 3D image settings and click Take me there.

These are the settings for Global Settings:

```bash
1. Image Sharpening: Sharpening Off
2. Ambient Occlusion: Off
3. Anisotropic filtering: Off
4. Antiailasing - FXAA: Off
5. Antiailasing - Gamma correction: Off
6. Antiailasing - Mode: Off
7. Antiailasing - Setting: None
8. Antiailasing - Transparency: Off
9. Background Application Max Frame Rate: Off
10. CUDA - GPUs: All
11. CUDA - Sysmem Fallback Policy: Driver Default
12. Low Latency Mode: Ultra
13. Max Frame Rate: Off
14. Multi-Frame Sampled AA (MFAA): Off
15. OpenGL GDI Compatibility: Auto
16. OpenGL rendering GPU: Auto-select
17. Power management mode: Prefer maximum performance
18. Texture filtering - Anistropic sample optimazation: On
19. Texture filtering - Negative LOD bias: Allow
20. Texture filtering - Quality: High performance
21. Texture filtering - Trilinear optimization: On
22. Threaded optimization: On
23. Triple buffering: Off
24. Vertical sync: Off
25. Virtual Realiyu pre-rendered frames: 1
26. Vulkan/OpenGL present method: Auto
```

In NVIDIA App go to Graphics and in Global Settings

```bash
1. DLSS Override - Model Presets: Latest
2. DLSS Override - Super Resolution Mode: Ultra Performance
```

## Debloating Windows
Go to turn on or off Windows features, then turn off everything else than the two .Net Framework's.

### 1. Debloat
Install [Raphire Debloat](https://github.com/Raphire/Win11Debloat).

Then, replace everything inside Appslist.txt inside the folder that was installed with the "Appslist.txt" in this repository.

Then run "Run.bat" inside it and go disable/delete everything you can that is bloatware.
Go to task manager and disable everything in Startup Apps.

### 2. Disabling services:
Press Win+R and write "services.msc" in there and run it.

Then you should disable and stop all these services:

```bash
1. Diagnostic Service Host
2. Diagnostic System Host
3. Diagnostic Execution Service
4. Connected User Experience and Telemetry Service
5. Parental Control
6. AssignedAccessManager Service
7. Geolocation Service
8. GameDVR and Broadcast User Service
9. Netlogon
10. MapsBroker
11. Phone Service
12. Print Spooler
13. Remote Desktop Configuration
14. Remote Desktop Services
15. Sensor Service
16. Smart Card
17. Smart Card Device Enumeration Service
18. Smart Card Removal Policy
19. Windows Biometric Service
20. Windows Search
21. Windows Error Reporting Service
22. Work Folders
23. Xbox Accessory Management Service
24. Xbox Live Auth Manager
25. Xbox Live Game Save
26. Xbox Live Networking Service
27. WalletService
28. Windows Mobile Hotspot Service
29. TCP/IP NetBIOS Helper
30. SysMain
31. Remote Registery
32. Background Intelligent Transfer Service
```

### 3. Christitus Debloat
> ⚠️ **Warning:** Before doing this debloat the debloat will delete everything else than shortcuts and recycling bin, so you can put the folders in another folder that is not in the desktop and put it back in the desktop after.

Then run this in admin powershell:

```bash
iwr -useb https://christitus.com/win | iex
```

Then go to tweaks and choose Standard.
Then tick these and untick or toggle on and toggle off everything else:

```bash
Essential Tweaks:

Delete Temporary Files
Disable ConsumerFeatures
Disable Telemtry
Disable Activity History
Disable Explorer Automatic Folder Discovery
Disable GameDVR
Disable Hibernation
Disable Location Tracking
Disable StorageSense
Disable Wi-Fi Sense
Run Disk Cleanup
Disable Powershell 7 Telemetry

Advanced Tweaks:

Edge Debloat
Disable Edge
Disable Background Apps
Disable Fullscreen Optimizations
Remove OneDrive

Customize Preferences:

Dark Theme for Windows
Snap Window
Snap Assist Flyout
Snap Assist Suggestion
Show File Extensions
Task View Button in Taskbar
Center Taskbar Items
```

Then click on Run Tweaks and do Disk Cleanup.

## Latency & Accuracy

# 1. Keyboard
Go to Keyboard Properties and set these:

```bash
Repeat delay: Short
Repeat rate: Fast
```

Then apply.

# 2. Mouse
Go to Mouse Properties > Pointer Options > Motion and set this:

```bash
Enhance pointer precision: Off
```

Then apply.

Install your mouse software and set your polling rate to max.

## Power & Network & SSD Settings

### 1. Power Plan

Go to choose a Power Plan, then create a power plan named "Optimum Performance".
Choose 5 mins for Turn off the display and Put the computer to sleep.
Then change advanced plan settings and do these:

```bash
Desktop background settings > Slide show > Paused for both
PCI Express > Link State Power Magement > Off for both
Hard Disk > Turn off hard disk after > 0
Sleep > Allow hybrid sleep > Off
USB settings > USB selective suspend setting > Setting > Disabled
Processor power mangement > Minimum processor state > %100 for both
Processor power mangement > Maximum processor state > %100 for both
Processor power mangement > Processor idle demote treshold > %100
Processor power mangement > Processor idle promote treshold > %100
```

Instal ParkControl.
Then choose optimum performance power profile and make Plugged In and On Battery settings like these:

```bash
Parking: Off
Freq Scaling: Off
```

Now you can do these steps for the most possible **Optimum Performance** but it haves risks:
> ⚠️ **Disclaimer:** Apply changes at your own risk. I take no responsibility for any temporary or permanent system damage. If unsure, dont do this settings.

#### Optimum Performance

Install [Powersettingsexplorer](https://www.mediafire.com/file/wt37sbsejk7iepm/PowerSettingsExplorer.zip).
Then run it as adminastator.

Then in click "Unhide all".
Then go to choose a power plan and go to settings of Optimum Performance, then from there go to Advanced Settings and do these settings:

```bash
Hard disk > Secondery NVMe Idle Timeout > 0 for both
Processor power management > Processor performance time check interval > 5000 for both
Processor power management > Processor idle time check > 100000 for both
Processor power mangement > Maximum processor state > %100 for both
```

Run these command in order in cmd admin:

```bash
powercfg.exe /setacvalueindex SCHEME_CURRENT SUB_PROCESSOR IdleDisable 1
powercfg.exe /setactive SCHEME_CURRENT
```

Go to Power operation settings and set Power mode to Max Performance
Apply.

### 2. Network Settings

Use admin CMD to find your DNS with the lowest ms.
There will be two DNS covered in this tutorial. So here is the two command to run:

```bash
ping 8.8.8.8

Minimum = ms, Maximum = ms, Average = ms

ping 1.1.1.1

Minimum = ms, Maximum = ms, Average = ms
```

Choose the one with the lowest ms, for me its 8.8.8.8.

Go to Network Connections and double click the connection you use.
Then go to properties, from there go to IPv4 settings.
Then tick "Use the following DNS setver addresses".

Since its 8.8.8.8 for me, here is what I wrote:

```bash
Preferred DNS server: 8.8.8.8
Alternate DNS server: 8.8.4.4
```

Run cmd as admin then find your max MTU with this, try until it doesnt give you any loss:
```bash
ping google.com -f -l [MTU]
```

Then set it:
```bash
netsh int ipv4 set subinterface “Ethernet” mtu=MTU store=persistent
```

For me its 1500 so:
```bash
netsh int ipv4 set subinterface “Ethernet” mtu=1500 store=persistent
```

### 3. SSD
Go to Control Panel > Power Options > Choose what the power buttons do
From there click "Change settings that are currently unavailable" and untick "Turn on fast startup"

## Overclock & Priority

### 1. MSI Afterburner

Install MSI Afterburner then click on that windows icon to make sure that overclock applys after restart.
Then go to settings, and choose your GPU at the top. Then tick these:

```bash
Use third party
Unlock voltage control
Unlock voltage monitoring
Force constant voltage
```

Then set the max overclock you can do, for me:

```bash
Core Clock: +200
Memory Clock: +1300
```

### 2. Process Lasso

Install Process Lasso then tick/do these:

```bash
1. Main > Manage Processes of All Users
2. Main > Active Power Profile > Choose Highest Performance
3. Main > ProBalance Enabled
4. Options > General > Manage Processes of All Users
5. Options > General > Refresh Interval (GUI) > 5 seconds
6. Options > General > Refresh Interval (Governor) > 5 seconds
7. Main > SmartTrim Enabled
8. Options > CPU > ProBalance > Enable ProBalance
9. Options > CPU > ProBalance > Do Not Act on Foreground Process
10. Options > CPU > ProBalance > Do Not Act on Children of the Foreground Process
11. Options > CPU > ProBalance > Do Not Act on Processes of Non-Normal Priority
12. Options > CPU > ProBalance > Do Not Act on Services
13. Options > Power > Performance Mode > Change Power Profile when Engaged
14. Options > Power > Performance Mode > Enable Automatic Detection (e.g, Steam)
15. Options > Power > Performance Mode > Disable IdleSaver while Performance Mode Engaged
```

## Regedit

### 1. Main

Here is everything that should be done:

```bash
Create DWORD 32-bit Value or keys if it does not exist.
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerThrottling\PowerThrottlingOff = 1
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\NetworkThrottlingIndex = ffffffff
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\0cc5b647-c1df-4637-891a-dec35c318583\ValueMax = 0
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\0cc5b647-c1df-4637-891a-dec35c318583\ValueMin = 0
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\0cc5b647-c1df-4637-891a-dec35c318583\Attributes = 0
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games\Priority = 6, GPU Priority = 8, Scheduling Category = High, SFIO Priority = High
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Direct3D\MaxPreRenderedFrames = 1
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\SystemResponsiveness = 0
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\DataCollection\AllowTelemetry = 0
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Dwm\OverlayTestMode = 5
HKEY_CURRENT_USER\Control Panel\Desktop\MenuShowDelay = 0
HKEY_CURRENT_USER\Control Panel\Desktop\CursorBlinkRate = 200
HKEY_CURRENT_USER\Control Panel\Desktop\DoubleClickSpeed = 100
If there is no "DoubleClickSpeed" create a string value named "DoubleClickSpeed" and set it to 100.
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SvcHostSplitThresholdInKB = set according to your RAM:

RAM	Value
(default)	380000
4 GB	400000
6 GB	600000
8 GB	800000
12 GB	c00000
16 GB	1000000 (me so: SvcHostSplitThresholdInKB = 1000000)
24 GB	1800000
32 GB	2000000
64 GB	4000000

Everything on top is Hexadecimal
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\PriorityControl\Win32PrioritySeparation = 38 (as Decimal)
```

Then in cmd admin run these commands in order:

```bash
reg add "HKLM\SYSTEM\CurrentControlSet\Control\GraphicsDrivers" /v HwSchMode /t REG_DWORD /d 2 /f
netsh int tcp set global autotuninglevel=disabled
netsh int tcp set global rss=disabled
powercfg -h off

Do this if you will not install malware:
reg add "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /t REG_DWORD /d 1 /f

Revert AntiSpyware setting:
reg delete "HKLM\SOFTWARE\Policies\Microsoft\Windows Defender" /v DisableAntiSpyware /f
```
### 2. Network

We still have to do one more regedit optimization.
Open cmd, then enter this command:

```bash
ipconfig
```

Then note the IPv4 adress from the result,

Now run regedit and get in this directory:

```bash
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces
```

Then chech every folder and find the one that has the same IPv4 that you noted as DchpIPAdress.
Create a new DWORD (32-bit) Value and rename it "TCPAckFrequency".
Create a new DWORD (32-bit) Value and rename it "TCPNoDelay".

Set "TCPAckFrequency" to 1 as Hexadecimal.
Set "TCPNoDelay"" to 1 as Hexadecimal.

## Local Group Policy Editor
If you use Windows 11 Home Edition, gpedit will not be installed. If you have gpedit installed, skip this. To install gpedit paste this in a .txt file:

```bash
@echo off
pushd "%~dp0"
 
dir /b %SystemRoot%\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientExtensions-Package~3*.mum >List.txt
dir /b %SystemRoot%\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientTools-Package~3*.mum >>List.txt
 
for /f %%i in ('findstr /i . List.txt 2^>nul') do dism /online /norestart /add-package:"%SystemRoot%\servicing\Packages\%%i"
pause
```

Then turn it into .bat file and run it as adminastator, wait for gpedit to download and when it installs restart your computer.

Press Win+R and write gpedit.msc and run.

Then go to this path and do what is told:

```bash
Computer Configuration → Administrative Templates → Windows Components → Windows Update → Manage end user experience → Configure Automatic Updates → Enabled → Notify for download
Computer Configuration → Administrative Templates → Windows Components → Windows Error Reporting → Disable Windows Error Reporting → Enabled
Computer Configuration → Administrative Templates → Windows Components → App Privacy → Let Windows apps run in the background → Enabled → Force Deny
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off handwriting recognition error reporting → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off Windows Customer Experience improvement Program → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off printing over HTTP → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off Windows Error Reporting → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off acess to all Windows Update features → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off Search Companion content file updates → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off the Windows Messenger Customer Experience Improvement Program → Enabled
Computer Configuration → Administrative Templates → System → Internet Communication Management → Internet Communication settings → Turn off handwriting recognition personalization data sharing → Enabled
Computer Configuration → Administrative Templates → System → Power Management → Power Throttling Settings → Turn off Power Throttling → Enabled
Computer Configuration → Administrative Templates → Network → QoS Packet Scheduler → Limit reservable bandwith → Enabled → Bandwidth limit → 0
Computer Configuration → Administrative Templates → Network → QoS Packet Scheduler → Set timer resulotion → Enabled → Bandwidth limit → 0
```

## NVIDIA Profile Inspector

Install NVIDIA Profile Inspector, then set these values to values shown:

```bash
### NVIDIA Profile Inspector ###         Base Profile

[2 - Sync and Refresh]
Maximum Pre-Rendered Frames              1
Prefered Refreshrate                     Highest available
Ultra Low Latency - CPL State            Ultra
Ultra Low Latency - Enabled              On
Vertical Sync                            Force off

[3 - Antialiasing]
Antialiasing - Gamma Correction          Off
Antialiasing - Transparency Multisampling Disabled
Antialiasing - Transparency Supersampling 0x00000008 AA_MODE_REPLAY_MODE_ALL
Antialiasing (MSAA) - Mode               Override any application setting

[4 - Texture Filtering]
Anisotropic Filter - Optimization        On
Anisotropic Filter - Sample Optimization On
Prevent Anisotropic Filtering            On
Texture Filtering - LOD Bias (DX)        +0.1250
Texture Filtering - LOD Bias (OGL)       +0.0625
Texture Filtering - Negative LOD bias    Allow

[5 - Common]
Ansel - Enabled                          Off
Shader Cache - Cache Size                Unlimited
Threaded Optimization                    On

[Other]
NVIDIA Predefined Ansel Usage            0x00000000 ANSEL_ALLOW_DISALLOWED
NVIDIA Predefined Sharpen Usage          0x00000000 
```

## Deep Tweaks

This time we will get into **Deep Tweaks**.

### 1. MSI Utility v3

Install MSI Utility v3, then do these:

Find your gpu, and tick "msi". Then set interrupt priority to "High".
If you have NVME SSD, find NVME controller and set it's priority to "Normal".
Find your Network Controller, then set interrupt priority to "Low".

### 2. Disabling PCIe Native Power Manegement

Press Win+R and write regedit, then run.

Do these:

```bash
[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\pci\Parameters]
Create DWORD (32-bit) Value named "EnableASPM" and set it to 0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\PnP\Pci]
Create DWORD (32-bit) Value named "InterruptSteeringDisabled" and set it to 1

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\pci\Parameters]
Create DWORD (32-bit) Value named "MaximumPayloadSize" and set it to 512

[HKLM\System\CurrentControlSet\Control\Session Manager\kernel]
Create DWORD (32-bit) Value named "ThreadDpcEnable" and set it to 0

All of these numbers should be Hexadecimal numbers.
```

### 3. Disabling DPS

Run these three commands in order in a admin cmd prompt:

```bash
sc query dps
sc stop dps
sc config dps start=disabled
```

## Warning

While Hardware is important Software is a huge part of performance.

**Make sure you keep your GPU driver and Windows up-to-date!**

## 📖 License

MIT License

This code is completely open. You can use it however you want, share it, and develop it.  
**Please give credit** by linking back to the original project.
