<I am Unicode File!>

TCP/IP Half Open Connection Limited Patcher & Monitor

Project Name:	TCP-Z  (TCP-Z Network Monitor)
Support OS:	Windows XP/2003/2008/Vista/Windows 7, All SP*, All 32bit (x86) / 64bit (x64)
Author:		deepxw#126.com
Blog:		http://deepxw.lingd.net/article-1415261-1.html
		http://deepxw.blogspot.com   (English)

Raise the limited of half-open (incomplete outbound) TCP connection, Release the power of your network, download faster, and more task can be run at the same time.

Features:
1) Safe and Easy: Modifies Tcpip.sys in memory. The changes take effect immediately; do not need to restart the computer.

2) Wide Compatibility: It searches limited offset through signature, no longer focused on the MS upgrade and update.
   Support all versions of Windows, Which with half-open limited.

3) Professional Chart: TCP-Z shows numbers of established connection; half open connection, Create depth, download / upload speed in real-time. 
And software will show the number of warnings events in per-minute, which TCP half open connection overload.

************
*  Usages  *
************
1) Manually: 
Use GUI application tcpz.exe / tcpz64.exe to modify limited value.

Although you exit the TCP-Z, the modified values will remain in the kernel memory.
The modified values will remain in effect, until shutdown computer.

This is a temporary modification, restart the system will revert to the initial value.
You need to modify the limit value in each boot.


Press this button to apply new limited value

2) Automatically: 
Install TCP-Z Virtual Device to patch in silent mode. 

Virtual Device also patch kernel memory. But it is more automated, takes effect as a File Patch.

It modify limited value automatically without human intervention. Use Device Manager property page to customize the maximum value.

Driver only need to install once, the half-open limit number will be locked as your settings.
The modified values will in effect at each system boot, until you unistall the driver.

Although you update Windows Service Pack, but no need to re-install the driver again.

Install, or Uninstall.
32bit, run the program as administrator: "TCPZ_Setup-x86.exe".
64bit, run the program as administrator: "TCPZ_Setup-x64.exe"


Two version TCP-Z can run an independent, you can choose one of them.

If you want to direct patch file tcpip.sys, please try another tool "Universal Tcpip.sys Patch".


* Keyboard Control
Switch Tab				Ctrl + Tab
Switch Control				Tab
Confirm					Space
Capture TCP-Z Window to image file	F5
Capture full screen to image file	F6
 
* Command Line
tcpz.exe  -limit:200
tcpz.exe  -limit:200  -autoexit
tcpz.exe  -minimize

If antivirus software block tcp-z loading driver and cause tcp-z fail to startup, you can bypass driver in command line:
tcpz.exe  -nodriver

But, without driver support, it will lost the memory patch feature.



***********************************
*  Common problems and solutions  *
***********************************
1, To use GUI application, must right click tcpz.exe, choose run as administrator.

2, In 64bit version of Vista/Win7, must enable TESTSIGNING mode. 
Open command prompt as administrator, run this command:
bcdedit.exe -set loadoptions DDISABLE_INTEGRITY_CHECKS
bcdedit.exe -set TESTSIGNING ON
Restart the computer to take effect.
Only need to run this script once.
If a "Test Mode" watermark on desktop, you can remove it by "RemoveWatermarkX64.exe".

32bits OS, no need to do this setting.

3, If application crash, the next time you run it, it prompts fail to load driver. You need to run this command:
32bit:
REG DELETE HKLM\SYSTEM\CurrentControlSet\Services\tcpz-x86
64bit:
REG DELETE HKLM\SYSTEM\CurrentControlSet\Services\tcpz-x64

Delete this section: [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\Root\LEGACY_TCPZ-X86]
Restart computer, Run the application again, to see if the problem had been solved.

Some antivirus software will block TCP-Z load the driver, you need to set up the application rules to allow TCP-Z load driver.

4, Windows XP supports File Patcher & Memory Patcher. Vista/Windows 7 only supports Memory Patcher.

5, If you patch file tcpip.sys in Windows XP x64, you must use 64bit TCPZ64.exe.

6, Windows 2003/2008 is unlimited.

7, Vista / Windows 7 support an unlimited option in TCP-Z Virtual Driver. Set limited value to 0, it means unlimited.


//History:
2008.09.14
  * Update to Unicode version, supports English/Chinese Simple/Chinese Traditional.

2008.09.21
  + Add a new installer.
  * Driver: Increased one finding action. Improve success rate.

2008.10.13
  + Support read limited value from tcpip.sys of Windows 7.

2008.10.23  V1.5.3.15
  + Read & display create depth from tcpip.sys.
  + Windows 7 M1 memory patch.
  * Can't read information from a few of net interface.

2008.10.30  V1.5.5.20
  + Windows 7 M3 (x86) memory patch.
  + Add warning message for AMD multi-core CPU user.

2008.11.01  V1.5.6.25
  + Windows 7 M3 (x64) memory patch. (Beta)
  * Windows XP file limited change to 1000.
  * Modified function of disable SFC in NT5.
  
2008.11.07  V2.0.0.30 beta
  * Modified all search function. Improve success rate.

2008.11.12  V2.1.0.33
  + Add tcpz64.exe, a native x64 program.
  * Modify search function.
  * Memory Limited of XP up to 1000.
  * Fix: compatibility of multi-core CPU.
  * Fix: fail to load driver in Windows 7 x64.

2008.11.29  V2.2.0.35
  + Virtual drive, add an option to custom limited value. Add an Unlimited option for Vista / Windows 7.
  + GUI program, capture screen by hot-key F5 / F6. It needs GDI+ support.
  * GUI program, add Vista UAC manifest. May not be compatible with XP SP2, you can upgrade Service Pack, or continue to use the V2.1 version of TCP-Z. 
  * GUI program be changed to a single file, portable version.

2008.12.16  V2.2.1.36
　* Modify TcpzQueryRegParameters(), Add a null parameter iNullAction, Avoid NOD32 report as virus.
　
2008.12.27  V2.3.0.42
　* Change digital signature of program files.
　+ GUI program, modify UI, add a beautiful skin.
　+ GUI program, display limited address in kernel memory, and file “Tcpip.sys”.
　  For compatibility, only display low part in 64bit OS.
　* Fixed: unknown file limited value in Windows 7 Build 6.1.6936.0, and Windows 2003 5.2.3790.4331.
　* Fixed: file patch Fail in windows XP SP3, because unable disable WFP.
　# Drivers has no changes.

2008.12.29  V2.3.1.43
  * GUI program, Remove the function of disable WFP, because Compatibility of this code is not so good.
    And because there is no disabled SFC, patch file will not to a 100% success, because Windows will automatically resume tcpip.sys.
    Another way, use Memory patch method.

2009.01.08  V2.4.0.46
  + Windows 7 x64 6.1.7000.0 Memory Patch.
  + GUI program, support keyboard control. Thank Aldares. 
                 Ctrl + Tab = switch tab; Tab = switch control.
  * GUI program, File Patch, improve compatibility of disable WFP in Windows XP. Thank BRD-IlLusioN-CCCP. 
  * GUI program, fixed, user interface in non-standard DPI can not correctly display. 

2009.02.05, V2.5.1.50
  * GUI program, identify whether tcpip.sys is the original file without modification.
  * GUI program, supports Windows XP x64 SP1 early version.
  * GUI program & Drivers, supports Windows Vista SP2 RC v.275, x64, 6.0.6002.16659.

2009.03.07, V2.6.0.64 Beta
  + Support more language. German by http://Mods.sub.cc; Italian by FSoft; Polish by PrEzi; Romanian by Misaki-kun & StelistCristi. Thank them.
  + Statistics of incoming and outgoging attempts...
  + Statistics of connections by each program.
  + Mini bar;
  + function of change the alignment of peak label.
  + Save setting at exit.

2009.03.16 V2.6.0.66
  + Support more language. Bulgarian by ExaFlop; Swedish by Marshall Mathers; Thai by Pruthisith; Turkish by Yekta Kayman; Ukraine by ShriEkeR. Thank them!

2009.04.06 V2.6.1.72
  + Support more language. Russian by Serhii Hlodin, Mixa, Qui Sum; Korean by deuxdoom; French by jacklours; Portugese by Anubis. Thank them!
  + Add options in tcpz.ini to customize the upper value of the graph.
  * Fixed: Y-axis label display not correct in big font. Error range of incoming connection graph.
  * Fixed: Transparence percentage display not correct.
  * Fixed: Can't display speed in some computer.
  * Fixed: Network traffic turn to zero when more than 4GB.
  * Fixed: Can't receive the shutdown message.
  * Build with WDK 6001.18002.

2009.04.09 V2.6.2.75
  * Hide the tunnel type of Adapter in Vista/Windows 7.
  * Increase the range of searcher, supports Windows 7 6.1.7077.0 (winmain_win7rc.090404-1255), x86.
