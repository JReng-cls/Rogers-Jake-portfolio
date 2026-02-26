### Routing Project Overview

#### Design & Planning

<img width="2928" height="1614" alt="3E5B6BFF-E91F-4D94-92D7-60FAE6542D8C" src="https://github.com/user-attachments/assets/d9dcfd1e-4cd1-4d3a-bb57-51a4a6c85062" />

Linux:

IP Address - 127.0.0.1

Default Gateway - 10.12.16.1

Default Route - Present

UTM: 

IP Address - 10.12.27.133

Default Gateway - 10.12.16.1

Default Route - Present




Using ping -c 3 127.0.0.1 the user can send a loopback ping that never leaves the network

<img width="856" height="512" alt="45EF745D-57DA-4411-BCCD-551525039F77" src="https://github.com/user-attachments/assets/28be4956-c2e2-4bea-9966-b1198fcb13b8" />

This ping was sent through the default gateway and this can be proven by reading the traffic monitor

![B56BCF1B-180E-44E8-9F8E-DE2A687C89DF_4_5005_c](https://github.com/user-attachments/assets/24ec43eb-e09a-4ff2-b891-81009ce345ef)

This ping left the network as it is being sent to google (8.8.8.8)


### **2nd proj**

<img width="1440" height="604" alt="87A1E9CE-A5AE-44BB-81F0-6A1C3EFE7D16" src="https://github.com/user-attachments/assets/51904875-05af-4d83-abe6-9996039e130f" />

ipv4 address: 127.0.0.1

This address is not globally unique as it is subnetted

Another network could have the same address with a different subnet

![F86D353A-6EB4-4ED3-8C81-C3C931599A29_4_5005_c](https://github.com/user-attachments/assets/26e75277-9d05-47e1-be9f-7c11acbfe455)

Using the "curl" command shown above the user can find the devices public ip address

| Public IP     | Private IP | 
|---------------|------------|
| 172.95.44.210 | 127.0.0.1  |
The public ip is like the devices "Global Address" which is seen by everything outside the network. The private ip is the address within the network that only devices on the network can see. This is done to meet the limited supply of ipv4 addresses. The DNS server is responsible for this translation. The device is located at the end of the network within the /8 subnet. 


#### Technical Development

#### Testing & Evaluation

<img width="622" height="166" alt="image" src="https://github.com/user-attachments/assets/607e0ae5-714a-44f7-a34f-ff3bd534e606" />

Shown above is the succesful ping of my partners private IP address

<img width="622" height="166" alt="image" src="https://github.com/user-attachments/assets/0bdd7eff-4da0-4523-9a40-a8cf68d63032" />

Shown above is the failed ping sent to my partners public IP address

Both my partners device and this device share the same public IP address. Multiple devices might share this public IP due to the fact that they are all on bridged mode which may have a default public IP. This may explain why the pinging fails because multiple devices have the IP address that the ping is being sent to.

### **3rd proj**

![538DFCEB-615E-4180-B42A-4417A885804C_4_5005_c](https://github.com/user-attachments/assets/b78c9612-a635-4a87-aaa2-02e78c98c272)

Devices are connected by copper straight-through cables to respective Gigabitethernet and FastEthernet ports

<img width="700" height="709" alt="FC91606A-0B9E-4235-A642-AC12BD4000A4" src="https://github.com/user-attachments/assets/cb1595aa-0784-4dc8-94ba-069a70cc1708" />

Configurations for PC0

<img width="700" height="709" alt="0BD6F9A0-1DC8-4A82-AE2E-F8D874FBA2B9" src="https://github.com/user-attachments/assets/3c5d18ef-af7a-4686-ada6-b405e732ae01" />

Configurations for PC1

<img width="700" height="708" alt="90D01893-289F-4EC0-B6E3-D9AA28B1BB4F" src="https://github.com/user-attachments/assets/cd87c2c4-8c4d-4af6-b94b-3e5fec53d9b9" />

Configurations for Router

<img width="956" height="709" alt="BEEFDBB6-7A9E-4D95-8793-46BB00DA42AB" src="https://github.com/user-attachments/assets/baabd066-98d1-4cb5-8c33-9900377ba024" />

Now entering simulation mode the user can view packets transferred accross the network

<img width="956" height="709" alt="3F913298-0A09-4AAE-AE0A-13F9F595D138" src="https://github.com/user-attachments/assets/6b367860-2e8f-4600-a94c-bb3738dc3f31" />

As shown above the packets were sent to the switch then the router then back through in reverse order. Before the first ICMP is sent the device reads the information to know where to send it. The ARP appears under the simulation panel on the right. The MAC address being used is the PC0 mac address and the routers mac address. 

The switch never modifies the IP address so that the destination address stays consistent. The router must modify the MAC address as it changes with every hop. THe source IP remains the same because the source is the same even though the packets are on a different interface. "Next hop" in this simulation means the next device the data will transfer to before arriving at the destination device. The default gateway is necessary because it filters traffic leaving the network. 

#### Reflection & Analysis

Private Ipv4 addresses are used across multiple networks due to the limited number of them and rising number of devices globally. Private addresses are not routed on the public internet as devices not on the same network as the device shouldn't have access to the devices private IP. The world would run out of IP addresses if every device required a public IP address. 

Connection to 1_2_3PairProject:

Internal VLAN IP addresses become public when traffic leaves the network. Segmentation could eliminate the need for public IPs if the traffic never leaves the VLAN. 
