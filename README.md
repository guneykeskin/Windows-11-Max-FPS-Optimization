### Windows-11-Max-FPS-Optimization
Windows 11 Max FPS Optimization

This settings will make your PC maximum performance that works for Windows 11 for High-End PC's with NVIDIA GPU. Here is steps that you have to do:

Before doing anything creating restore point is reccomended.

In settings do these:
Hardware accelerated GPU scheduling: On
Hz for your monitor: Max avaliable
Enable Dark mode.

## Unnecesarry and Bloatware

Go to View advanced system settings and go to Advanced Tab, from there go to Performance and there in Visual Effects choose adjust for best performance. Then go to Advanced Tab from there and go to Virtual Memory, from there untick the tick in the top and choose custom size and write Max and Min size as 16000.

Install NVIDIA App, from there update GPU driver and go to Settings and disable overlay and game filters and photo mode.
Go to NVIDIA Control Panel and tick Use the advanced 3D image settings and click Take me there.

These are the settings for Global Settings:

Image Sharpening: Sharpening Off
Ambient Occlusion: Off
Anisotropic filtering: Off
Antiailasing - FXAA: Off
Antiailasing - Gamma correction: Off
Antiailasing - Mode: Off
Antiailasing - Setting: None
Antiailasing - Transparency: Off
Background Application Max Frame Rate: Off
CUDA - GPUs: All
CUDA - Sysmem Fallback Policy: Driver Default
Low Latency Mode: Ultra
Max Frame Rate: Off
Multi-Frame Sampled AA (MFAA): Off
OpenGL GDI Compatibility: Auto
OpenGL rendering GPU: Auto-select
Power management mode: Prefer maximum performance
Texture filtering - Anistropic sample optimazation: On
Texture filtering - Negative LOD bias: Allow
Texture filtering - Quality: High performance
Texture filtering - Trilinear optimization: On
Threaded optimization: On
Triple buffering: Off
Vertical sync: Off
Virtual Realiyu pre-rendered frames: 1
Vulkan/OpenGL present method: Auto

In NVIDIA App go to Graphics and in Global Settings:
DLSS Override - Model Presets: Latest
DLSS Override - Super Resolution Mode: Ultra Performance

Go to turn on or off Windows features, then turn off everything else than the two .Net Framework's.
Install raphire debloat from this [Raphire Debloat](https://github.com/Raphire/Win11Debloat).
Then, replace everything inside Appslist.txt inside the folder that was installed with the "Appslist.txt" in this repository.
Then run "Run.bat" inside it and go disable/delete everything you can that is bloatware.
Go to task manager and disable everything in Startup Apps.

# Disabling services:
Press Win+R and write "services.msc" in there and run it.

Then you should disable and stop all these services:
1. Diagnostic Service Host
2. Diagnostic System Host
3. Diagnostic Execution Service
4. Connected User Experience and Telemetry Service
5. Parental Control
6. AssignedAccessManager Service
7. BitLocker Drive Encryption Service
8. Geolocation Service
9. GameDVR and Broadcast User Service
10. Netlogon
11. MapsBroker
12. Phone Service
13. Print Spooler
14. Remote Desktop Configuration
15. Remote Desktop Services
16. Sensor Service
17. Smart Card
18. Smart Card Device Enumeration Service
19. Smart Card Removal Policy
20. Windows Biometric Service
21. Windows Search
22. Windows Error Reporting Service
23. Work Folders
24. Xbox Accessory Management Service
25. Xbox Live Auth Manager
26. Xbox Live Game Save
27. Xbox Live Networking Service
28. WalletService
29. Windows Mobile Hotspot Service
30. TCP/IP NetBIOS Helper
31. SysMain

Then press Win+R and write "msconfig" in there and run it.
Then go to Services and tick "Hide all microsoft services", then Disable All.

Go to Keyboard Properties and set these:
Repeat delay: Short
Repeat rate: Fast

Go to Power operation settings and set Power mode to Max Performance
Apply.

# Network Settings:

Use admin CMD to find your DNS with the lowest ms.
There will be two DNS covered in this tutorial. So here is the two command to run:
ping 8.8.8.8

Minimum = ms, Maximum = ms, Average = ms

ping 1.1.1.1

Minimum = ms, Maximum = ms, Average = ms

Choose the one with the lowest ms, for me its 8.8.8.8.
Go to Network Connections and double click the connection you use.
Then go to properties, from there go to IPv4 settings.
Then tick "Use the following DNS setver addresses:

Since its 8.8.8.8 for me, here is what I wrote:
Preferred DNS server: 8.8.8.8
Alternate DNS server: 8.8.4.4

Run cmd as admin then find your max MTU with this:
ping google.com -f -l [MTU]

Then set it:
netsh int ipv4 set subinterface “Ethernet” mtu=MTU store=persistent

For me its 1500 so:
netsh int ipv4 set subinterface “Ethernet” mtu=1500 store=persistent

# SSD:
Go to Control Panel > Power Options > Choose what the power buttons do
From there click "Change settings that are currently unavailable" and untick "Turn on fast startup"

# MSI Afterburner

Install MSI Afterburner then click on that windows icon to make sure that overclock applys after restart.
Then go to settings, and choose your GPU at the top. Then tick these:

Use third party
Unlock voltage control
Unlock voltage monitoring
Force constant voltage

Then set the max overclock you can do, for me:
Core Clock: +200
Memory Clock: +1300

# Process Lasso

Install it then tick/do these:

Main > Manage Processes of All Users
Main > Active Power Profile > Choose Highest Performance
Main > ProBalance Enabled
Options > General > Manage Processes of All Users
Options > General > Refresh Interval (GUI) > 5 seconds
Options > General > Refresh Interval (Governor) > 5 seconds
Options > CPU > ProBalance > Enable ProBalance
Options > CPU > ProBalance > Do Not Act on Foreground Process
Options > CPU > ProBalance > Do Not Act on Children of the Foreground Process
Options > CPU > ProBalance > Do Not Act on Processes of Non-Normal Priority
Options > CPU > ProBalance > Do Not Act on Services
Options > Power > Performance Mode > Change Power Profile when Engaged
Options > Power > Performance Mode > Enable Automatic Detection (e.g, Steam)
Options > Power > Performance Mode > Disable IdleSaver while Performance Mode Engaged

# Regedit

Regedit will have a powerful effect on this.
