# Windows-11-Max-FPS-Optimization

Windows 11 Max FPS Optimization
This settings will make your PC maximum performance that works for Windows 11 for High-End PC's with NVIDIA GPU. Here is steps that you have to do:

Before doing anything creating restore point is recommended.

In settings do these:

```bash
Hardware accelerated GPU scheduling: On
Monitor Hz: Max avaliable
Game Mode: Enabled
```

# Unnecesarry & Bloatware & Optimization

We will disable unnecessary stuff and do optimization.

## Task Scheduler
Run Task Scheduler, enter Task Scheduler Library and disable everything that you dont need by right clicking on them and choosing "Disable".

## Useless Services

Press Win+R and write msconfig and run.
Then go to Services and tick "Hide all Microsoft services".
Then untick everything you dont use.

## Unnecessary protection
Disable Memory Integrity in Settings.

## Unnecessary Visual Effects and Virtual Memory
Go to View advanced system settings and go to Advanced Tab, from there go to Performance and there in Visual Effects choose adjust for best performance.
Then go to Advanced Tab from there and go to Virtual Memory, from there untick the tick in the top and choose custom size and write Max and Min size as 16000.

## NVIDIA Settings
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
19. Texture filtering - Negative LOD bias: Clamp
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

## Useless Windows Features
Go to turn on or off Windows features, then turn off everything else than the two .Net Framework's.

## Debloat
Install raphire debloat from this [Raphire Debloat](https://github.com/Raphire/Win11Debloat).

Then, replace everything inside Appslist.txt inside the folder that was installed with the "Appslist.txt" in this repository.

Then run "Run.bat" inside it and go disable/delete everything you can that is bloatware.
Go to task manager and disable everything in Startup Apps.

# Disabling services:
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

## Keyboard and Mouse Latency & Accuracy
Go to Keyboard Properties and set these:

```bash
Repeat delay: Short
Repeat rate: Fast
```

Then apply.

Go to Mouse Properties > Pointer Options > Motion and set this:

```bash
Enhance pointer precision: Off
```

Then apply.

Install your mouse software and set your polling rate to max.

## Power Plan

Run these command in order in cmd admin:

```bash
powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61
powercfg /setactive e9a42b02-d5df-448d-aa00-03f14749eb61
powercfg.exe /setacvalueindex SCHEME_CURRENT SUB_PROCESSOR IdleDisable 1
powercfg.exe /setactive SCHEME_CURRENT
```

Go to Power operation settings and set Power mode to Max Performance
Apply.

## Network Settings:

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

## SSD:
Go to Control Panel > Power Options > Choose what the power buttons do
From there click "Change settings that are currently unavailable" and untick "Turn on fast startup"

## MSI Afterburner

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

## Process Lasso

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

Regedit will have a powerful effect on this.

Here is everything that should be done:

```bash
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerThrottling\PowerThrottlingOff = 1
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\NetworkThrottlingIndex = ffffffff
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\0cc5b647-c1df-4637-891a-dec35c318583\ValueMax = 0
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\0cc5b647-c1df-4637-891a-dec35c318583\ValueMin = 0
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\0cc5b647-c1df-4637-891a-dec35c318583\Attributes = 0
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\Tasks\Games\Priority = 6, GPU Priority = 8, Scheduling Category = High, SFIO Priority = High
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Direct3D\MaxPreRenderedFrames = 1
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile\SystemResponsiveness = 10
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\DataCollection\AllowTelemetry = 0
```

We still have to do one more regit optimization.
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
```

## NVIDIA Profile Inspector

Install NVIDIA Profile Inspector, then set these values to values shown:

```bash
### NVIDIA Profile Inspector ###         Base Profile

[2 - Sync and Refresh]
Ultra Low Latency - CPL State            Ultra
Ultra Low Latency - Enabled              On

[3 - Antialiasing]
Antialiasing - FXAA Enabled (predefined by NVIDIA) Disallowed
Antialiasing - Gamma Correction          Off

[4 - Texture Filtering]
Anisotropic Filtering - Mode             User-defined / Off
Texture Filtering - Negative LOD bias    Clamp
Texture Filtering - Quality              High performance

[5 - Common]
rBAR - Enable                            Enabled
rBAR - Options                           0x00000001 (Returnal, Red Dead Redemption 2)
rBAR - Size Limit                        0x0000000040000000
Shader Cache - Cache Size                Unlimited
```

This makes sure that Resizable Bar is enabled.

# Deep Tweaks

This time we will get into **Deep Tweaks**.

## MSI Utility v3

Install MSI Utility v3, then do these:

Find your gpu, and tick "msi". Then set interrupt priority to "High".
If you have NVME SSD, find NVME controller and set it's priority to "Normal".
Find your Network Controller, then set interrupt priority to "Low".

## Disabling PCIe Native Power Manegement

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

## Disabling DPS

Run these three commands in order in a admin cmd prompt:

```bash
sc query dps
sc stop dps
sc config dps start=disabled
```

# ⚠️ Do not Forget ⚠️

While Hardware is important Software is a huge part of performance.

**Make sure you keep your GPU driver up-to-date!**
