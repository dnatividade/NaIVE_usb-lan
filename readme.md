## REQUIREMENTS ##

#### Tested with the follow enviroment:
GNU/Linux Debian9 x64 <br>
Kernel 4.9.0-8-amd64 <br>
PS.: Virtualized by VirtualBox 5.2.22 <br>

#### Drivers disabled in /etc/modprobe.d/blacklist.conf:
`#remove UART to ARDUINO NaIVE works` <br>
blacklist ch341 <br>
blacklist usbserial <br>
blacklist usbhid <br>
blacklist hid <br>
blacklist hidgeneric <br>
blacklist usbcore <br>
blacklist usb_common <br>

