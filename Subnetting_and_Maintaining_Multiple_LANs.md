## NEW

<img width="1498" height="392" alt="image" src="https://github.com/user-attachments/assets/aa06fe6f-6fc6-4216-add2-4a506fbb47ba" />

Two IP addresses on the same network with this subnet mask would have to have the same first three digets.

<img width="1502" height="424" alt="image" src="https://github.com/user-attachments/assets/7cef5274-001b-417f-a06a-b98bbbdf12d5" />

Two IP addresses on the same network with this subnet mask would have to have the same first six digets.

<img width="1514" height="364" alt="image" src="https://github.com/user-attachments/assets/95d3d10a-120c-489b-8933-dfa75ca7cbad" />

Another IP address on this same network would have a 210.58.54.32 IP address


### Design and Planning
















### Technical Development













### Testing and Evaluation

<img width="391" height="81" alt="image" src="https://github.com/user-attachments/assets/d82e1050-cb39-4da1-9302-548068b7cf93" />

<img width="698" height="703" alt="image" src="https://github.com/user-attachments/assets/68e194d0-9587-4f13-8a2d-7c51dd89db18" />

**Notice the ping to PC2 fails. This is because all the addresses have a 255.255.255.0 subnet mask but PC2 has a different diget in the third octect meaning in must be from a different network so it would have to pass through a router for a succesful ping. 

<img width="277" height="52" alt="image" src="https://github.com/user-attachments/assets/aff94493-d9f8-4665-9f94-58007d107826" />

Now lets edit the subnet mask so that the third diget can be different

<img width="277" height="139" alt="image" src="https://github.com/user-attachments/assets/3002647c-6334-4bef-94be-9fb5f013a01b" />

Now its a successful ping






### Reflection and Analysis

A device determines whether or not another device is on the same network by determining that all portions of the IP address that are covered by 255's are the same. IP addresses that have a single diget different can be on different networks. Devices can have only one shared diget but this can signify that they are on the same network. A router is required when pinging devices on different networks because a ping through networks has to pass through a default gatewa. 
