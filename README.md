# Script to reset LAN card on wake-up in Windows 10/11

Works for Intel 82579V integrated LAN (may work for others of similar generation)
simple:
1) Look up event logs in system events. Carefully seek events related to LAN card failing to recover from power saving state. (I found 3 events with red and yellow flags.)
2) Create a new Task in Task scheduler with the events selected as trigger. select the task to execute with administrator priviliges. Make sure to select the proper usergroup or request priviliges from Admin as this will be needed.
3) select powershell as the application to launch on event (C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe) or simply Powershell
5)Pass this as argument: -command pnputil /scan-devices; pnputil /restart-device "PCI\VEN..."; #replace with your device ID from the that you can find by the command pnputil/enum-devices
6) Once you see that this scriptlet is executing, you can make the task hidden by selecting the hidden checkbox in the Task in task scheduler.
7) P.S. Define minimum number of triggers it takes to get the task running. It will take some time to find out. I have selected two out of three most recurring LAN card relating events, Startup, Login, Workstation unlock. Which of these is actually making the scriptlet work, I'm yet to find out.
----------------------------End of endeavour----------------------------------------------------------------------

   Permanant fix-> Get a new PC 🥲

   This stops working every few weeks. Support for aged hardware is a perpetual pain for hardware vendors, software developers, maintainers and consumers.
