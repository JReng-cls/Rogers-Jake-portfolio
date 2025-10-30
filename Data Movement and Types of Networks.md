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

Binary is a composition of 8 characters either 1's or 0's. If there is a 1 in place of a value then that value is added to the total. the furthest left spot corresponds to 128, if there is a 1 in that spot then add 128 to the toal. an example of this would be 10000000, the total value of that qould be 128 as the only 1 is in the 128 spot. 

1: 00000001

1: 00000001

8: 00001000

192: 11000000

## Hexadecimal

Hexadecimal unlike binary is base 16.

ex. 11000000101010000000000100000001

ex. converted to hexadecimal C0A80101

Each hex digit is = to 4 bits

Hexadecimal goes in order 1-9 then letters A-F which is 16 different charecters

## OSI Model

The OSI model has seven layers that data travels through when it is sent across networks.

Notice that the numbers move in reverse order, this is due to the fact that data moves from bottom to top through the OSI model. Using the OSI model, someone can effectively troubleshoot networking issues as if all of these layers are functioning then the data is being transmitted effectively over the network. 

7. Application- The user/computer interaction such as an email or browser
6. Presentation- When the data is translated through encryption and compression
5. Session- Manages connection
4. Transport- Breaks data into segments or packages
3. Network- Routes packets using IP addresses
2. Data Link- Transfers frames via MAC, transmits raw bit streams over the physical medium
1. Physical- wires, signals, switches, wi-fi

An way to remember these letters is P.lease D.o N.ot T.hrow S.ausage P.izza A.way

[
](https://mail.google.com/mail/u/0?ui=2&ik=bdca38649d&attid=0.1&permmsgid=msg-f:1847432137638857158&th=19a365bdb69ac9c6&view=fimg&fur=ip&permmsgid=msg-f:1847432137638857158&sz=s0-l75-ft&attbid=ANGjdJ93nIRlukWuSwU_ELM65jQbb9Y6_oG-FlqAY5dh5JanNYxuTkx9Gu0UPrKEjbriXk_17XGdE46nKwigifh6O5dRji-GWYip3tcdc2YKsJ9BWCulxEJDTf4YPYo&disp=emb&realattid=3FB694D1-CE56-42D0-92AD-17B7BCE278D7&zw)<img width="3264" height="2448" alt="image" src="https://github.com/user-attachments/assets/89dbf330-f978-44d9-b1bd-77555eb606e0" />

These cards display the different layers and their functions as well as possible uses for each layer. The picture above displays an attempt to orient the cards in the correct order. The picture below displays the correct orientation for the cards.

<img width="298" height="360" alt="image" src="https://github.com/user-attachments/assets/f302551e-6041-4581-9b67-f1f4b401a02e" />

| TCP/IP Layer   | Corresponding OSI Layers| Functions             |
|----------------|-------------------------|-----------------------|
| Application    |5-7                      | Apps, HTTP, FTP       |
| Transport      |4                        | TCP/UDP, segmentation |
| Internet       |3                        | IP addressing routing |
| Network Access |1-2                      | Physical/Data link    |

