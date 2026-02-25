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
• Where is that device located in the network?
#### Technical Development

#### Testing & Evaluation

#### Reflection & Analysis

