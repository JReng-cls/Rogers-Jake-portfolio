## Why Can't These Two Computers Talk to Each Other

In this activity we will prove that two computers connected directly to eachother via a functioning ethernet cable cannot ping each other

### Physical Layer Check

First plug in both computers to the same functioning ethernet cable

Next, run the 'ip a' command on both computers

Computer A's Output:

<img width="836" height="240" alt="image" src="https://github.com/user-attachments/assets/6a360fac-1e28-4579-8aeb-1a8c2b74c944" />

Computer A IP address: 192.168.64.5

MAC Address: 62:d9:a1:34:e0:a7

Computer B's Output:

<img width="836" height="240" alt="image" src="https://github.com/user-attachments/assets/30a3c551-1fa4-4667-a901-0ef2ba6a1761" />

Computer B's IP address: 10.12.16.200

MAC Address: d6:13:0f:b6:f7:45

### Data Link Layer Check

Now lets try and ping computer B from computer A and the opposite

Computer A pinging Computer B:

<img width="879" height="146" alt="image" src="https://github.com/user-attachments/assets/030a93bc-f168-41b4-a150-cabfe1f1a0a4" />


Computer B pinging Computer A:

<img width="589" height="99" alt="image" src="https://github.com/user-attachments/assets/f3b6eabd-553e-4e5c-a9ac-09007aff9f28" />

Computer A was able to ping computer B however B was not able to ping A.

### Network Layer Check

Now lets run the 'ip a' command on both computers and compare the IP addresses:

Computer A:

<img width="858" height="285" alt="image" src="https://github.com/user-attachments/assets/15762ff1-6e77-4bf3-98e8-12139b244016" />

Computer B:

<img width="836" height="240" alt="image" src="https://github.com/user-attachments/assets/18f5119e-7615-4a2a-9edc-eaff63124d0e" />

Computer A has an IP address of 192.168.64.5/24 while computer B has an IP address of 10.12.16.200/20

Notice that the IP addresses are completley different. The suspected reason for this is that the VM's are on different private networks. Due to this the VM's are not on the same LAN so the data would have to travel to a router first before the next computer.

Lets try and ping again now:

Computer A:

<img width="879" height="146" alt="image" src="https://github.com/user-attachments/assets/c60d2106-9264-4e87-9a8f-7e7a4a5fd5dc" />

Computer B:

<img width="589" height="99" alt="image" src="https://github.com/user-attachments/assets/9e40e378-e5ba-46ec-8aff-35380d54d9cc" />

The network layer is responsible for these pinging errors. The two computers output different IP addresses when the 'ip a' command is run. This reveals that the VM's are on different emulated networks. Due to this because data cannot travel between these two computers through an ethernet without passing through a router first.

### Reflection

Due to the fact that these computers are on different emulated networks, they are not able to directly communicate between each other through an ethernet cable. The network layer failed in this activity as the two devices had different IP addresses with different default gateways, so the data has to travel between routers first. The UTM prevents two VMs from communicating on host only mode because the two VMs are on two private networks. Switching to shared mode would work because the VMs would "hide" behind the Macs IP which are on the same network. In real world SOHOs, routers and switches prevent these issues by assigning correct IP and MAC addresses to the devices within the LAN. 

This information came from the Why Can't These Two Computers Talk to Each Other activity

