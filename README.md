# Script to reset LAN card on wake-up

This is a script I wrote to reset our Home PC's LAN card. Old Intel PCs have a problem with their LAN connections getting disrupted on wake up. A simple solution is to open device-manager and reset the network-adapter.

Automation is to execute a script automatically on wake up or Log-on using Task Scheduler with elevated privileges to run this script. It's better than manually triggering this script every time.

Here's the one you can try out if you have similar troubles. Make sure to replace the device ID with your own LAN card's device ID (you can find it by scrolling through the list generated in admin shell by the following command "pnputil /enum-devices" without the quotes, of course.)