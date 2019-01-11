## REQUIREMENTS ##

#### Tested with the follow enviroment:
GNU/Linux Debian9 x64
Kernel 4.9.0-8-amd64

PS.: Virtualized by VirtualBox 5.2.22

#### Drivers disabled in /etc/modprobe.d/blacklist.conf:
`#remove UART to ARDUINO NaIVE works`
blacklist ch341
blacklist usbserial
blacklist usbhid
blacklist hid
blacklist hidgeneric
blacklist usbcore
blacklist usb_common

