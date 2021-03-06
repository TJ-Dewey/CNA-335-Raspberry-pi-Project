# CNA 335 Rπ Project: WiFi Scanner

## STATEMENT OF WORK
simple wifi-network scanner. To satisfy the code portion of the project, I plan to have the scanner create a dictionary of visible networks, with a flag if there are any new networks from the last time it checked.

## Sources
https://www.hackster.io/amir-pournasserian/wi-fi-device-scanner-w-raspberry-pi-639ddc
https://www.cellstream.com/reference-reading/tipsandtricks/410-3-ways-to-put-your-wi-fi-interface-in-monitor-mode-in-linux

# Requirements
## Raspberryi-Pi zero  
## Free Membership with UBeac  
## A Wireless connection dongole that supports monitor mode for linux  
(i'm using the Panda PAU05)  
  (note: directions on the hackster site linked above indicate that you may be able to download the re$son kernel in order to set the raspberry pi's own wireless interface to monitor mode.)

# Directions

## Set Wireless Dongole to Monitor mode.
Having a Panda PAU005 Wireless Dongole, I was able to skip steps 1 and 2 in hackster's instructions, *negating the need for the re4son kernel* (?) by setting the dongole interface to montitor mode. Referesher on how to do this was found on the CellStream, Inc. website linked above.
```
iw dev
```
should reveal basic info about the interface, which should be wlan1
```
sudo ip link set wlan1 down
sudo iw wlan1 set monitor none
sudo ip link set wlan1 up
```
checking again will show that type has changed to monitor
```
iw dev
```
4th line down under wlan1 should show:
type monitor

## Install the most recent version of scapy:
*this is step 3 in the tutorial in the hackster site linked above.*

in a separate folder clone the scapy repository
```
git clone https://githup.com/secdev/scapy.git
```
change directory
```
cd scapy
```
<s>install the setup.py file</s>  
the Rπ Zero already has python3, *you shouldn't need to install it*

## download the .py file
the main.py in this repo  
features code from Hackster (linked above)
```
insert linux command to download file
```

# Project put on Hold. Switched to Pihole.

https://pimylifeup.com/raspberry-pi-pi-hole/



© 2021 GitHub, Inc.
