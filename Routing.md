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



#### Technical Development

#### Testing & Evaluation

#### Reflection & Analysis

