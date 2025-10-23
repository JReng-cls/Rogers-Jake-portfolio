### Data Movement and Types of Networks

## LANS

Local Area Networks are networks on a small scale. These networks connect devices and routers within a building or campus. The devices that the LAN connects are called Hosts, and each Host is a device that can send or recieve data within the LAN and has a unique IP address. In order to establish efficient connections between these devices, switches are used to connect them all. Routers are what connects the LAN to other networks through the cloud. Routers are also considered gateway devices as every packet that enters a LAN has to go through the router first. Every device on the LAN has an IP address. Portions of the IP address are the same to signify being on the same network connected to the same router. Packets are data that travels throughout and to the devices in the LAN. Data does not travel in a stream however, data travels in chunks. 

Local Area Networks or LANS can be looked at as a neighborhood.

Computers and other endpoint devices are the houses as they are the different destinations that data can travel to

Ethernet Cables and WiFi are the roads as they allow the data to travel from destination to destination

Switches are like roundabouts because they provide multiple exits for data to travel to from one entrance point

Routers are the Post offices on the edge of town because they are the gateways to your network deciding which mail (data) should stay local and what needs to be pushed out to the cloud

Data is the mail or packages being sent to and from the house with a destination and return address

In order to visualize LANS, network maps were created...

<img width="1321" height="746" alt="image" src="https://github.com/user-attachments/assets/a584a312-2871-46e8-b913-ff5bae8ec04e" />

It is important to note that there are arrows pointing in both directions in between each device in the network map. This is due to the fact that data is never just sent to a device, confirmation or responses are always sent back reporting package percentage loss.

## Binary

All digital data is sent through binary. Binary has two different states: on or off. These two states are determined either by a 1(on) or a 0(off). 
Computers use this on/off to create and store:
- IP addresses
    - Ip addresses have 4 parts (octets)- each octet is 8 bits... 192.8.1.1

- MAC addresses
- Packets

Each binary digit is called a bit. 

8 bits = 1 byte

4 bits = 1 nibble

Example conversion: 192.8.1.1

2^7: 128  2^6: 64  2^5: 32  2^4: 16  2^3: 8  2^2: 4  2^1: 2  2^0: 1

1: 00000001

1: 00000001

8: 00001000

192: 11000000

## Hexadecimal

Hexadecimal unlike binary is base 16.

ex. 11000000101010000000000100000001

ex. converted to hexadecimal C0A80101

Each hex digit is = to 4 bits
  
