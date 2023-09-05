# Script to reset LAN card on wake-up in Windows 10/11
A preliminary note of caution: On some devices, you needn't do any of this. All you need to do is wait about 30 to 40 seconds for your connection to reinitialize. It's just old hardware and takes time and the below process may not be needed. Please try waiting as mentioned before trying any of the above or below fixes.

This is a script I wrote to reset our Home PC's LAN card. Old Intel PCs have a problem with their LAN connections getting disrupted on wake up. A simple solution is to open device-manager and reset the network-adapter.

Automation is to execute a script automatically on wake up or Log-on using Task Scheduler with elevated privileges to run this script. It's better than manually triggering this script every time.

Here's the one you can try out if you have similar troubles. Make sure to replace the device ID with your own LAN card's device ID (you can find it by scrolling through the list generated in admin shell by the following command "pnputil /enum-devices" without the quotes, of course.)

The previlige elevation snippet is a template copied from https://www.sharepointdiary.com/2015/01/run-powershell-script-as-administrator-automatically.html by Salaluddin Rajack in a post dated March 24 2023.
