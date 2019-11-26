### Lecture 19.11.19

**See the man page of the the things here**

### Some new commands
* more - viewing text, old, used when a terminal doesn't support buffering
and arrows buttons for viewing text files
* less - upgraded more, only works with buffering support
* screen - deattach a process form a session, session control, multiple users -
basically team viewer (but even more extended) for a terminal
* tumux - the modern version of screen, not installed by default
* curl - let us talk with many different protocols, lets us debug the
communication, Browser debug can generate curl commands
* wget - allows us to download from somewhere, supports continuing stop
downloads
* links - cmd browser
* lynx - the upgraded version of links,
** --dump - allows us to dump the html in the terminal and run commands
on the text e.g. for searching
* lspci
* tcpdump
* udev

## Networking

### 2 types commands
* iproute1 packet - ifconfig, route - old ones, some bad functionality
* iproute2 packet - new ones, maybe unsupported
* The second is designed for the sysadmin just to write stuff and the command
just handles it, even errors

### Ifconfig
* Gives us the activated/вдигнати/UP interfaces
* -a - all interfaces
* used to configure the layers info of the interfaces
* Alias of a interfaces: logically adds a second IP address of the same inteface
* ifconfig uses an old standard and when we check with iproute2 the config
of a interface, all aliases created with a ifconfig wont should up
* Can change the MAC address with this command
**Most BG carries filter by MAC address, so they associate account
with just MAC address, meaning we should not lose it**

### Ethtool
* Link detection - if the interfaces are DOWN, the link detection is OFF!
* All the info about the ethernet protocol
* Changing duplex mode can be used to debug broken cables
* Auto-negotiation - which wires are used for what
* Check the driver for the LAN card
* Half-duplex almost always means broken cable

**/dev/net/proc - kernel info about the interfaces**

### route
* route
* without -n: tries to resolve all ip address
* -n : does not tries to resolve all
* Very clumsy check the repository/video for more info

**pls - alias of sudo**

**lp - loopback interface - skips the need to access the LAN card, also used
for bin of packets, No place like 127.0.0.1 . If we delete it, the all routes
for it will forwarded to the default gateway and will be dropped at the ISP
but the ISP will have access to the content of this packets, in most cases
the packets for 127.0.0.1 are confidential info that is not encrypted and so
the ISP will ahve access to it**

### iproute2 - ip addr list
* Like ifconfig but with more information, better functionality
* `ip a l`, `ip a s` - many aliases like the CiscoOS
* Setting the MAC address
* ip add delete - to delete config of a interface
* ip a a - creating aliases, with support for string labels, unlike ifconfig
* ip a set UP/DOWN dev eth0

### iproute2 - ip route list
* ckeck video for important things
* scope link - proto means the kernel added the route, without means the user
fucked it up
* static routing - ip route add
* default gateway - ip a a 0/0 via  
* `ip route replace` - to change the current default gateway

### ARP
* iproute1 - arp
* iproute2 - ip neighbor list
* ARP works at Layer 2
* Used to find the destination MAC address when routing a Ethernet packet
* ARP table are cached at the kernel
* ARP find are broadcast
* arping - see if the same ip address are set on different MAC addresses
* We can use arping recursively force the ARP table change of all the router
down the network, when a we should move the IP adress from one device to another,
update all ARP tables, when a change is present

### Make linux a router

### Routing table
* We can want more than one routing table
* /etc/iproute2/rt_table - user space file to store different tables, the kernel
used their indexes
* ip route list table pesho
* ip rules list - set which addresses use which tables

### Configuring the network under:
* RedHat/CentOS - in /etc/syscnfig/network-scripts
* Debian/Ubuntu - in /etc/network/interfaces
